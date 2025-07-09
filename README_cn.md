<div align=center> <img src="./image/ceph.png" width = 45%>

#### 简体中文 | [English](README.md)

<div align=left>

<div class="column" align="middle">
  <a href="https://github.com/opencurve/curve/tree/master/docs">
    <img src="https://img.shields.io/badge/docs-latest-green.svg">
</div>

## 📖 主要内容

### 🔍 Ceph初学指南

[Beginner’s Guides](https://docs.ceph.com/en/latest/start/beginners-guide/)

[IBM Storage Ceph for Beginners](https://community.ibm.com/community/user/viewdocument/ibm-storage-ceph-for-beginners?CommunityKey=1142f81e-95e4-4381-95d0-7977f20d53fa&tab=librarydocuments)

### 🏗️ [架构分析](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Architecture-Analysis)
  
* [OSD架构解析](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Architecture-Analysis/zh-cn/OSD.md)

* [CephFS-MDS架构解析](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Architecture-Analysis/zh-cn/Ceph%20MDS%20(Metadata%20Server)%20%E6%9E%B6%E6%9E%84%E8%A7%A3%E6%9E%90.md)

* [CMon架构解析](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Architecture-Analysis/zh-cn/Ceph%20Mon%E6%9E%B6%E6%9E%84%E8%A7%A3%E6%9E%90.md)


* [Ceph-CSI](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Architecture-Analysis)
  
*  [MGR](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Architecture-Analysis)

### 🛠️ [实践 & 应用](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Application-Practice)

####  💡 谁在使用Ceph？

- [索尼](https://static.sched.com/hosted_files/ceph2024/9f/Cephalocon2024-Ceph_as_a_platform.pdf?_gl=1*4dvljn*_gcl_au*MTk4MTIxMDc0NS4xNzI5NTYzMDEw*FPAU*MTk4MTIxMDc0NS4xNzI5NTYzMDEw)
- [欧洲原子核能研究中心](https://indico.cern.ch/event/1457076/attachments/2934445/5156641/Ceph,%20Storage%20for%20CERN%20Cloud.pdf)
- [DigitalOcean](https://ceph.io/assets/pdfs/events/2024/ceph-days-nyc/2024%20Ceph%20Day%20NYC%20How%20we%20Operate%20Ceph%20at%20Scale.pdf)
- [45Drives](https://ceph.io/assets/pdfs/events/2024/ceph-days-nyc/45Drives%20-Ceph%20Days%202024%20-%20FINAL.pdf)
- [彭博社](https://static.sched.com/hosted_files/ceph2023/2e/Cephalocon%202023%20-%20multisite.pdf?_gl=1*4b8rzs*_gcl_au*MTk4MTIxMDc0NS4xNzI5NTYzMDEw*FPAU*MTk4MTIxMDc0NS4xNzI5NTYzMDEw)
- [walmart](https://ceph.io/assets/pdfs/events/2025/ceph-days-silicon-valley/05%20-%20Pavan%20Anton%20-%20Walmart%20Ceph%20Days%202025%20Presentation.pdf)
- [etraveli group](https://static.sched.com/hosted_files/ceph2024/0a/Etraveli%20Group%20Presentation%20_%20Cephalocon2024.pdf)
- [UKRI](https://ceph.io/assets/pdfs/events/2025/ceph-day-london/07%20LT%20Learning%20opportunities%20from%20a%20100PB%20Ceph.pdf)
- [proton](https://static.sched.com/hosted_files/ceph2024/10/proton_jan_luis.pdf)
- [Nordic AB: Ceph(FS) Operations Retrospective](https://static.sched.com/hosted_files/ceph2024/b4/Cephalocon2024_CephFS_Operations_Retrospective.pdf)
-  更多稍后更新，非常欢迎您的贡献

####  🛠️ 性能优化

* [Ceph Tentacle版本纠删码增强](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Distributed-Storage/zh-cn/Ceph%20Tentacle%E7%89%88%E6%9C%AC%E7%BA%A0%E5%88%A0%E7%A0%81%E5%A2%9E%E5%BC%BA.md)
* [1 TiB/s的Ceph性能之旅](https://ceph.io/en/news/blog/2024/ceph-a-journey-to-1tibps/)


* [ceph rbd tune](https://www.intel.com/content/www/us/en/developer/articles/technical/performance-tuning-of-ceph-rbd.html)

* [全闪存Ceph系统性能优化](https://ceph.io/assets/pdfs/events/2024/ceph-days-nyc/Ceph%20Days%20NYC%202024%20-%20Designing%20and%20Tuning%20for%20All-Flash%20Ceph%20RBD%20Storage.pdfl)

* [知乎专栏：Ceph性能瓶颈分析与优化系列N](https://zhuanlan.zhihu.com/p/375442336)
  
####  💡 Ceph 线上实践

- [Ceph集群灾难性恢复01 --- 我的osd,mds起不来啦](https://zhuanlan.zhihu.com/p/468220071)
- [Ceph集群灾难性恢复02 --- cephfs文件系统只读(MDS in read-only mode)](https://zhuanlan.zhihu.com/p/231164499)
- 更多稍后更新，非常欢迎您的贡献

#### 🛠️ [运维技巧](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Operation-Skills)

- [实用指南：Ceph常用工具汇总](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Operation-Skills/zh-cn/%E5%AE%9E%E7%94%A8%E6%8C%87%E5%8D%97%EF%BC%9ACeph%E5%B8%B8%E7%94%A8%E5%B7%A5%E5%85%B7%E6%B1%87%E6%80%BB.md)
- [实用指南：ceph集群巡检脚本](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Operation-Skills/zh-cn/ceph%E9%9B%86%E7%BE%A4%E5%B7%A1%E6%A3%80%E8%84%9A%E6%9C%AC.md)

  

### 🔍 [源码分析](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Code-Analysis)

- [BlueStore](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Code-Analysis)
-  更多稍后更新，非常欢迎您的贡献


### 📖 [Ceph研究(论文和演示文稿)](https://github.com/wuhongsong/ceph-deep-dive/issues/7)


- [File systems unfit as distributed storage backends: lessons from 10 years of Ceph evolution](https://dl.acm.org/doi/pdf/10.1145/3341301.3359656)
- [Ceph: A Journey to 1 TiB/s](https://ceph.io/en/news/blog/2024/ceph-a-journey-to-1tibps/)
- [IBM Storage Ceph](https://www.ibm.com/docs/en/storage-ceph/8.0.0)
- [ceph_study](https://github.com/lidaohang/ceph_study)


**更多请点击上面链接**


### 📖 [分布式存储研究](https://github.com/wuhongsong/ceph-deep-dive/tree/main/Distributed-Storage)


- [从deepseek-3FS聊到AI存储](https://github.com/wuhongsong/Ceph-Learn-Notes/blob/main/Distributed-Storage/zh-cn/%E4%BB%8Edeepseek-3FS%E8%81%8A%E5%88%B0AI%E5%AD%98%E5%82%A8.md)
- [linux内核文档大全](https://lwn.net/Kernel/Index/)
- [分布式存储DAOS：后Optane时代的转型之路](https://github.com/wuhongsong/ceph-deep-dive/blob/main/Distributed-Storage/zh-cn/DAOS%20File%20System:%20Phoenix%20Rising%20After%20Optane's%20End.md)

- 典型分布式存储系统对比：Ceph vs. JuiceFS vs. Alluxio vs. CubeFS vs Daos vs. ?


**更多稍后更新，非常欢迎您的贡献**

  

------

## 🤝 贡献指南

我们热烈欢迎社区贡献! 

[怎样贡献?](https://github.com/wuhongsong/ceph-deep-dive/blob/main/CONTRIBUTING.md)



## 📞 联系方式

- **问题讨论**：[GitHub Issues](https://github.com/wuhongsong/ceph-deep-dive/issues)
- **邮件**：wojiaowugen@163.com
- **微信**：wojiaowugen


------
<!-- Copy-paste in your Readme.md file -->

<a href="https://next.ossinsight.io/widgets/official/analyze-repo-stars-map?repo_id=991781952&activity=stars" target="_blank" style="display: block" align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://next.ossinsight.io/widgets/official/analyze-repo-stars-map/thumbnail.png?repo_id=991781952&activity=stars&image_size=auto&color_scheme=dark" width="721" height="auto">
    <img alt="Star Geographical Distribution of wuhongsong/ceph-deep-dive" src="https://next.ossinsight.io/widgets/official/analyze-repo-stars-map/thumbnail.png?repo_id=991781952&activity=stars&image_size=auto&color_scheme=light" width="721" height="auto">
  </picture>
</a>

<!-- Made with [OSS Insight](https://ossinsight.io/) -->

