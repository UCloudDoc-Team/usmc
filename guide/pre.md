# 迁移前准备

使用USMC进行服务器的迁移，需要提前进行一些准备工作。

- 源端需要有外网出口

- 需要开启 UCloud EIP 流量计费权限位

- 如果源是阿里云，则需要有AliyunECSReadOnlyAccess 和 AliyunVPCReadOnlyAccess 权限的阿里云AKSK

## 注意事项

- 如果多批次迁移到同一目标VPC，请使用同一个迁移计划

- IDC 虚拟机暂时仅支持 VMWare

- 如果源是 IDC 物理机，系统盘数据量不能超过400GB，数据盘不能超过2TB

- 如果源主机上部署有数据库(MySQL\PostGre\MongoDB\Redis等)， 建议使用UDTS先迁移数据库。

请查看当前USMC所支持系统是否满足您的需求，具体请查询 [操作系统支持](/usmc/sys)
