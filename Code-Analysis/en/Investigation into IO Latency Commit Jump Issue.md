Investigation into the Jump of IO Commit Latency Statistics in Ceph Cluster
Recently, I encountered a very interesting problem. After a node machine in my Ceph cluster restarted, the statistics of io commit latency experienced a sudden jump after the OSD restarted. The value jumped directly from the previously increasing numbers to around 4,200,000,000.
![1cbdc1281f3f34a96a1cf40b55d69e44.jpg|600](https://raw.githubusercontent.com/YLShiJustFly/picturebed/main/images/1cbdc1281f3f34a96a1cf40b55d69e44.jpg)
This value is quite sensitive, as it is approximately equal to \(2^{32}\). This value is calculated as the rate of the ceph_osd_op_w_latency value collected by Prometheus.
Initial Investigation
At first, I suspected that after the OSD restarted, this value dropped to 0, and there might be a problem with how the Prometheus rate function handled the decreasing value, resulting in a negative number that caused an overflow. However, after checking information about the rate function online, I found that it is designed to handle such situations and ensures that no negative values are generated.
I then started to check the Ceph code. Initially, I guessed that there might be issues such as the value not being cleared to 0 during initialization, or negative values being written in abnormal processes. By looking into the Ceph code implementation, I found that this part is initialized with 0. Moreover, this value is of the atomic type, and an assert is performed on the 0 value when it is used for the first time. A non - 0 value would trigger an assert coredump, thus ruling out this possibility.
Further Analysis
Then, I took a closer look at the curve of the jump. I found that before the jump occurred, that is, after the OSD started, the latency value actually started from 0, and the jump happened three minutes after startup. Only after the jump, the value reached \(2^{32}\), making both the value of over 1 million before the machine crashed and the 0 value after startup appear as 0.
So, I continued to study how Ceph calculates latency. It records the endtime and starttime of the commit, and the functions used to obtain these timestamps are based on realtime, that is, the local machine time. The calculation is done by endtime - starttime, and there is no logic similar to that of the rate function to ensure that the result is greater than or equal to 0. This means that if the machine's time rolls back, and a commit spans before and after the rollback, and the entire commit time is less than the rollback time, a jump in latency will occur.
![image.png|600](https://raw.githubusercontent.com/YLShiJustFly/picturebed/main/images/20250608172327.png)

Verification and Conclusion
I checked the NTP rollback records on the machine, and indeed, the machine time rolled back by 4ms exactly when the jump occurred.
![image.png|600](https://raw.githubusercontent.com/YLShiJustFly/picturebed/main/images/20250608172359.png)
 
Then, I conducted an experiment. I ran fio on the RBD in the test cluster, and then rolled back the time by 1ms. As expected, the latency statistics jumped.
![](https://popofp.vipfp.ps.netease.com/file/684162b6d5dbab9ee1d1d45251JL0trO01)

Now, the truth is clear. Later, I checked the official PR records and found a PR that replaced the real time clock with the mono monotonic clock, but not all places were modified. <https://github.com/ceph/ceph/pull/39273>
The mono monotonic clock is presumably more CPU - consuming than the real time clock. I'm not sure if it's due to performance reasons that some less important code branches were not modified. I also raised an issue on the official Slack, but so far, I haven't received a response.
