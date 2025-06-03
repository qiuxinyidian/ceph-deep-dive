

## 📋 Common Tools (Summary - Incomplete Version)

| Function Category | Main Commands | Verification Status | Usage Frequency | Use Cases | Risk Level |
|-------------------|---------------|---------------------|-----------------|-----------|------------|
| **Cluster Monitoring** | `ceph -s`, `ceph health(detail)`, `ceph df`, `ceph -w` | ✅ Verified | ⭐⭐⭐⭐⭐ | Daily monitoring, fault diagnosis | 🟢 No risk |
| **I/O Monitoring** | `ceph iostat` (version-dependent, Nautilus+), `ceph -w`, `ceph status` | ✅ Verified | ⭐⭐⭐⭐ | Performance monitoring | 🟢 No risk |
| **OSD Management** | `ceph osd tree`, `ceph osd status`, `ceph osd out/in` | ✅ Verified | ⭐⭐⭐⭐ | OSD maintenance, capacity management | 🟡 Medium risk (queries are no risk) |
| **Monitor Management** | `ceph mon stat`, `ceph quorum_status`, `ceph mon add/remove` | ✅ Verified | ⭐⭐⭐ | Cluster management, high availability | 🔴 High risk (queries are no risk) |
| **Manager Management** | `ceph mgr module enable/disable`, `ceph mgr stat` | ✅ Verified | ⭐⭐⭐ | Feature management, dashboard | 🟡 Medium risk (queries are no risk) |
| **Storage Pool Management** | `ceph osd pool create/delete`, `ceph osd pool set` | ✅ Verified | ⭐⭐⭐⭐ | Storage planning, quota management | 🔴 High risk (queries are no risk) |
| **PG Management** | `ceph pg stat`, `ceph pg repair`, `ceph pg scrub` | ✅ Verified | ⭐⭐⭐⭐ | Data integrity, fault repair | 🟡 Medium risk (queries are no risk) |
| **Authentication Management** | `ceph auth list/create/del` | ✅ Verified | ⭐⭐⭐ | Security management, permission control | 🔴 High risk (queries are no risk) |
| **CRUSH Management** | `ceph osd crush tree`, `crushtool`, `ceph osd crush rule` | ✅ Verified | ⭐⭐ | Data distribution, fault domain | 🔴 High risk (queries are no risk) |
| **RBD Management** | `rbd create/rm`, `rbd snap create`, `rbd map/unmap` | ✅ Verified | ⭐⭐⭐⭐ | Block storage, snapshot management | 🟡 Medium risk |
| **CephFS Management** | `ceph fs status`, `ceph mds stat`, `ceph fs dump`, `ceph mds fail` | ✅ Verified | ⭐⭐⭐ | File system, metadata | 🟡 Medium risk (queries are no risk) |
| **RGW Management** | `radosgw-admin user create`, `radosgw-admin bucket` | ✅ Verified | ⭐⭐⭐ | Object storage, user management | 🟡 Medium risk (queries are no risk) |
| **Configuration Management** | `ceph config set/get`, `ceph tell` | Not verified | ⭐⭐⭐⭐ | Parameter tuning, troubleshooting | 🟡 Medium risk (queries are no risk) |
| **Performance Analysis** | `ceph osd perf`, `rbd perf image iostat`, `cephfs-top` | ✅ Verified | ⭐⭐⭐ | Performance testing, bottleneck analysis | 🟢 No risk |
| **Dedicated Tools** | `ceph-objectstore-tool`, `ceph-bluestore-tool` | ✅ Verified | ⭐⭐ | Data recovery, deep diagnostics | 🔴 High risk (queries are no risk) |
| **Troubleshooting** | `journalctl`, `ceph daemon dump`, log analysis | ✅ Verified | ⭐⭐⭐⭐ | Problem diagnosis, root cause analysis | 🟢 No risk |
| **Backup and Recovery** | `ceph mon getmap`, `ceph auth export`, data export | ✅ Verified | ⭐⭐ | Disaster recovery, migration | 🟡 Medium risk (queries are no risk) |



## 📋 常用工具(汇总简略不全版)

| 功能分类 | 主要命令 | 验证状态 | 使用频率 | 适用场景 | 风险级别 |
|---------|---------|---------|---------|---------|---------|
| **集群监控** | `ceph -s`, `ceph health(detail)`, `ceph df`, `ceph -w`| ✅ 已验证 | ⭐⭐⭐⭐⭐ | 日常监控、故障诊断 | 🟢 无风险 |
| **I/O监控** | `ceph iostat`(版本相关,N以上), `ceph -w`, `ceph status` | ✅ 已验证 | ⭐⭐⭐⭐ | 性能监控 | 🟢 无风险 |
| **OSD管理** | `ceph osd tree`, `ceph osd status`, `ceph osd out/in` | ✅ 已验证 | ⭐⭐⭐⭐ | OSD维护、容量管理 | 🟡 中等风险 (查询无风险) |
| **Monitor管理** | `ceph mon stat`, `ceph quorum_status`, `ceph mon add/remove` | ✅ 已验证 | ⭐⭐⭐ | 集群管理、高可用 | 🔴 高风险 (查询无风险)|
| **Manager管理** | `ceph mgr module enable/disable`, `ceph mgr stat` | ✅ 已验证 | ⭐⭐⭐ | 功能管理、仪表板 | 🟡 中等风险 (查询无风险) |
| **存储池管理** | `ceph osd pool create/delete`, `ceph osd pool set` | ✅ 已验证 | ⭐⭐⭐⭐ | 存储规划、配额管理 | 🔴 高风险 (查询无风险) |
| **PG管理** | `ceph pg stat`, `ceph pg repair`, `ceph pg scrub` | ✅ 已验证 | ⭐⭐⭐⭐ | 数据完整性、故障修复 | 🟡 中等风险 (查询无风险) |
| **认证管理** | `ceph auth list/create/del` | ✅ 已验证 | ⭐⭐⭐ | 安全管理、权限控制 | 🔴 高风险 (查询无风险) |
| **CRUSH管理** | `ceph osd crush tree`, `crushtool`, `ceph osd crush rule` | ✅ 已验证 | ⭐⭐ | 数据分布、故障域 | 🔴 高风险 (查询无风险) |
| **RBD管理** | `rbd create/rm`, `rbd snap create`, `rbd map/unmap` | ✅ 已验证 | ⭐⭐⭐⭐ | 块存储、快照管理 | 🟡 中等风险 |
| **CephFS管理** | `ceph fs status`, `ceph mds stat`, `ceph fs dump`, `ceph mds fail` | ✅ 已验证 | ⭐⭐⭐ | 文件系统、元数据 | 🟡 中等风险 (查询无风险) |
| **RGW管理** | `radosgw-admin user create`, `radosgw-admin bucket` | ✅ 已验证 | ⭐⭐⭐ | 对象存储、用户管理 | 🟡 中等风险  (查询无风险)|
| **配置管理** | `ceph config set/get`, `ceph tell` | 未验证 | ⭐⭐⭐⭐ | 参数调优、故障处理 | 🟡 中等风险 (查询无风险) |
| **性能分析** | `ceph osd perf`,`rbd perf image iostat`, cephfs-top | ✅ 已验证 | ⭐⭐⭐ | 性能测试、瓶颈分析 | 🟢 无风险 |
| **专用工具** | `ceph-objectstore-tool`, `ceph-bluestore-tool` | ✅ 已验证 | ⭐⭐ | 数据恢复、深度诊断 | 🔴 高风险 (查询无风险) |
| **故障排查** | `journalctl`, `ceph daemon dump`, 日志分析 | ✅ 已验证 | ⭐⭐⭐⭐ | 问题诊断、根因分析 | 🟢 无风险 |
| **备份恢复** | `ceph mon getmap`, `ceph auth export`, 数据导出 | ✅ 已验证 | ⭐⭐ | 灾难恢复、迁移 | 🟡 中等风险 (查询无风险) |
