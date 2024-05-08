# 约束限制

- 系统盘应<=1000G，数据盘应<=8000G，并保留500M以上可用空间
- USMC不迁移内存数据，所以无法迁移Redis等内存数据库产品
- 含有MySQL/PostgreSQL/MongoDB/TiDB服务时，建议使用UDTS先迁移数据库，或终止服务/业务后迁移
- USMC不迁移主机名，如果机器含有RabbitMQ/K8S等依赖hostname的服务，请自行处理
- 不支持迁移包含磁盘阵列RAID、LVM卷的Linux机器
- 如果机器包含共享文件系统，如NFS、NAS，建议先卸载后再启动迁移
- Linux迁移请保证目录有足够的读权限，尽量使用root用户执行agent
- 迁移后，服务器的MAC/IP/SID可能发生改变，造成应用license失效，请自行解决