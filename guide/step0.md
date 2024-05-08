# step0 迁移须知

## 迁移前须知

**系统**

- 采用恰当的方式做好数据备份，如VMware的快照、Windows自带的还原点等
- 建议关闭杀毒软件，以免影响迁移agent启动

**网络**

源机器不需要开放任何入方向的端口，但需要能够访问USMC管理服务地址

采用外网迁移时，地址为117.50.112.32:5160，内网/专线迁移时参考[支持地域](/usmc/introduction/conditions)

```
# Linux测试命令
[root@10-9-81-59 ~]# yum install nc -y
[root@10-9-81-59 ~]# nc -w 3 -v 117.50.112.32 5160
Connection to 117.50.112.32 5160 port [tcp/*] succeeded!

# Windows测试命令
PS C:\Users\Administrator> Test-NetConnection -ComputerName 117.50.112.32 -Port 5160
ComputerName     : 117.50.112.32
RemoteAddress    : 117.50.112.32
RemotePort       : 5160
InterfaceAlias   : 以太网
SourceAddress    : 10.9.47.56
TcpTestSucceeded : True
```

## 迁移中须知

- 迁移过程agent会占用源机器一定的资源，如CPU/Memory/磁盘IO/带宽，请知悉
- 禁止对中转机usmc-stopover-do-not-delete做任何操作，如关机/重装/更改密码/解绑EIP等
- Windows系统迁移时，启动go2ucloud.bat后的cmd界面，请不要关闭，保持到迁移完毕
- USMC迁移支持断点续传，但无必要，请不要重启Linux或Windows端的agent，以防出现意外
- 迁移出错时，Linux进入usmc-xxx目录，Windows直接在打开的cmd界面内，cat usmc_agent_log.txt提供给技术支持

## 迁移后须知

- Linux迁移基于文件同步，Windows迁移基于块同步，请用户自行验证数据一致性
- USMC只负责目标端的系统/网络拉起，用户自身业务影响难以评估，请充分测试后再投入生产环境