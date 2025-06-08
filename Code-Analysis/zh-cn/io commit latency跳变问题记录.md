Ceph 集群中 IO commit latency 统计跳变问题排查
最近遇到一个很有趣的问题，我的 ceph 集群有一个节点机器发生了重启，osd 重新启动后，io commit latency 的统计发生了跳变。从之前递增的数值，直接跳到了 4200000000 左右。
![1cbdc1281f3f34a96a1cf40b55d69e44.jpg|600](https://raw.githubusercontent.com/YLShiJustFly/picturebed/main/images/1cbdc1281f3f34a96a1cf40b55d69e44.jpg)
 
这个值很敏感，正好是 2 ^ 32 次方左右。这个值是对ceph_osd_op_w_latency prometheus 采集值做的rate。
初步排查
一开始怀疑 osd 重启后，这个值跌倒了 0，但是 prometheus 的rate函数对变小的情况处理有问题，算出了负数导致溢出。但网上查rate函数，对这种情况是做了处理的，它会保证没有负数。
开始排查 ceph 代码的问题，一开始的猜测是代码初始化的时候没有清 0，或者没有异常流程写入了负值。查阅 ceph 的代码实现，这部分初始化是写入了 0，并且这个值是atomic类型，在第一次使用的时候还会对 0 值进行assert，非 0 值会触发assert coredump，这个可能被排除了。
进一步分析
随后仔细看了一下跳变的曲线，发现在触发跳变之前，也就是 osd 起来之后，latency 的值实际是从 0 开始的，开机 3 分钟后，才发生跳变。只是跳变后的值达到了 2 ^ 32，导致机器挂掉前的 100 多万和启动后的 0 开始的值，都看起来是 0。
于是继续看 ceph latency 的计算方法，是记录 commit 的endtime和starttime，获取的函数实现使用的realtime，也就是机器本地时间，用过endtime - starttime，没有做类似rate那种保证大于等于 0 的逻辑。这就意味着如果机器上出现了时间回拨，并且一次 commit 跨回拨前后，而且整个 commit 时间小于回拨的时间，就会发生跳变。
![image.png|600](https://raw.githubusercontent.com/YLShiJustFly/picturebed/main/images/20250608172327.png)

验证与结论
检查了机器上的 ntp 回拨记录，确实在跳变的时候机器时间回拨了 4ms。
(https://raw.githubusercontent.com/YLShiJustFly/picturebed/main/images/20250608172359.png)
 
于是接着做了个试验，在测试集群 rbd 上跑fio，随后把时间回调了 1ms，统计 latency 果然发生了跳变。
![](https://popofp.vipfp.ps.netease.com/file/684162b6d5dbab9ee1d1d45251JL0trO01)
 
到这里就真相大白了。后面翻了一下官方的 pr 记录，有一个使用 mono 单调时钟替代 real time 时钟的 pr，但是没有把所有的地方都改掉。<https://github.com/ceph/ceph/pull/39273>
mono 单调时钟应该是比 real time 更耗 cpu 一些，不知道是不是因为性能的原因，在一些不重要的分支没做修改。也在官方 slack 提了一个 issue，问一下官方，目前还没得到回复。
