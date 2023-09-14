# 支持的场景

| 源 | 目标 | 迁移源类型选择 |   
| :---: | :---: | :---: |
| 阿里云 | UCloud 公有云 | 阿里云 |
| IDC 物理机 | UCloud 公有云 | IDC |
| IDC VMware | UCloud 公有云 | IDC |
| AWS、腾讯云等其它云平台 | UCloud 公有云 | IDC |
| UCloud 物理云主机 | UCloud 公有云 |IDC | 
| UCloud 云主机 | UCloud 公有云 |IDC | 

# 支持的操作系统

USMC客户端适用于下列操作系统。

## Linux
| 源操作系统版本 | 源系统架构 | 目标UCloud快杰云主机操作系统版本 | 目标UCloud快杰云主机系统架构 |   
| :---: | :---: | :---: |
| CentOS 6.x | x86_64 | CentOS 6.10 | x86_64 |
| CentOS 7.x | x86_64 | CentOS 7.6 | x86_64 |
| CentOS 8.x | x86_64 | CentOS 8.0 | x86_64 |
| Ubuntu 12.04 | x86_64 | Ubuntu 12.04 | x86_64 |
| Ubuntu 14.04 | x86_64 | 高内核 Ubuntu 14.04 | x86_64 |
| Ubuntu 16.04 | x86_64 | 高内核 Ubuntu 16.04 | x86_64 |
| Ubuntu 18.04 | x86_64 | 高内核 Ubuntu 18.04 | x86_64 |
| Ubuntu 20.04 | x86_64 | Ubuntu 20.04 | x86_64 |
| Ubuntu 22.04 | x86_64 | Ubuntu 22.04 | x86_64 |

## Windows
| 源操作系统版本 | 源系统架构 | 目标UCloud快杰云主机操作系统版本 | 目标UCloud快杰云主机系统架构 |   
| :---: | :---: | :---: |
| windows 2003 | x86_64 | Windows 2003 | x86_64 |
| windows 2008 | x86_64 | Windows 2008 | x86_64 |
| windows 2012 | x86_64 | Windows 2012 | x86_64 |
| windows 2016 | x86_64 | Windows 2016 | x86_64 |
| windows 2019 | x86_64 | Windows 2019 | x86_64 |
| windows 2022 | x86_64 | Windows 2022 | x86_64 |

## 其他
| 源操作系统版本 | 源系统架构 | 目标UCloud快杰云主机操作系统版本 | 目标UCloud快杰云主机系统架构 |   
| :---: | :---: | :---: |
| debian7 | x86_64 | Debian 7.0 | x86_64 |
| debian9 | x86_64 | Debian 9.9 | x86_64 |
| debian11 | x86_64 | Debian 11.7 | x86_64 |
| OpenSUSE 12 | x86_64 | OpenSUSE 12 | x86_64 |

# 功能限制

- 目前仅支持迁移到UCloud公有云快杰云主机
- 系统盘数据量不能超过400GB，数据盘不能超过2TB
- USMC不迁移内存中的数据，所以不支持迁移Redis等内存数据库产品。
- USMC不迁移主机名，所以不支持迁移RabbitMQ等依赖hostname的产品。
- 如果源主机上部署有数据库(MySQL\PostgreSQL\MongoDB\TiDB等)， 建议使用UDTS先迁移数据库。
- 如有低版本迁移需求（如：CentOS 5 ），请联系技术支持确认。
- 通过USMC迁移的机器在主机列表页不展示镜像名，如若需要确认，可通过DescribeUHostInstance中OsName字段查看。
