# 迁移前准备

使用USMC进行服务器的迁移，需要提前进行一些准备工作。

- 源端需要有外网出口
- 需要开启 UCloud EIP 流量计费权限位
- 如果源是阿里云，则需要有AliyunECSReadOnlyAccess 和 AliyunVPCReadOnlyAccess 权限的阿里云AKSK

## 注意事项

- 如果多批次迁移到同一目标VPC，请使用同一个迁移计划
