# 迁移前准备

使用USMC进行服务器的迁移，需要提前进行一些准备工作。

-源端需要有外网出口

-有AliyunECSReadOnlyAccess 和 AliyunVPCReadOnlyAccess 权限的阿里云AKSK(如果是从阿里云往UCloud迁移场景)

-需要UCLOUD EIP流量计费权限位开启。

-不同批次迁移但是使用的是相同的VPC的话请使用同一个迁移计划

-IDC虚拟机暂时仅支持VMWare

-IDC物理机，系统盘数据量不能超过400GB，数据盘不能超过2TB



## 注意事项

请查看当前USMC所支持系统是否满足您的需求，具体请查询 [操作系统支持](/usmc/sys)
