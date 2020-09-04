# 功能限制

- 目前仅支持迁移到UCloud公有云快杰云主机
- 如果源是 IDC 物理机，系统盘数据量不能超过400GB，数据盘不能超过2TB
- USMC不迁移内存中的数据，所以不能用来迁移Redis等内存数据库产品
- 如果源主机上部署有数据库(MySQL\PostGre\MongoDB\TiDB等)， 建议使用UDTS先迁移数据库
