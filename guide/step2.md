# step2 启动agent

## agent下载地址

进入计划详情页后，可在上部看到agent下载地址，如下图所示

![](/images/agent_url.png)

## Linux启动方式

使用ssh登陆源机器，以CentOS为例，按如下命令操作

```
# 1. 安装必要工具
[root@10-9-149-196 ~]# yum install wget unzip -y
# 2. 点击蓝框按钮，复制命令
[root@10-9-149-196 ~]# wget http://usmc-pre-file.cn-bj.ufileos.com/b6fa9c7b-48fd-4880-a3eb-938774889d6a/UCloud_Server_Migration_Agent_usmc-vtlwsdv6qa7_ff895ecd8216.zip && unzip UCloud_Server_Migration_Agent_usmc-vtlwsdv6qa7_ff895ecd8216.zip
# 3. 进入agent目录
[root@10-9-149-196 ~]# cd usmc-vtlwsdv6qa7/
# 4. 执行启动脚本，见到如下字样即可
[root@10-9-149-196 usmc-vtlwsdv6qa7]# ./go2ucloud.sh
usmc agent started
# 5. 查看log
[root@10-9-149-196 usmc-vtlwsdv6qa7]# cat usmc_agent_log.txt
{"level":"info","msg":"Start agent...","session":"","source":"/go/src/git.ucloudadmin.com/prj_smc/smc/src/agent/main.go:39","time":"2024-04-03T14:56:25.919862383+08:00"}
{"level":"info","msg":"stats","session":"","source":"/go/src/git.ucloudadmin.com/prj_smc/smc/src/agent/agent/agent.go:192","sshPublic":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCWB+hVmCBvoY+DYswkp6tSE3LA6UjonX/fxV7smGeRB27uMqpzs2J/vqxzcGmaGybapiZFYz8YvJoqbnMW2WzR2vffw4jYDei1TSErSESzrfqYU83yDRX0lI85vvHCbLXCuxRU1wbc3Qz0ILaSn7kUjanXgK0H5bPi1WAyHXUEyJ2AyOOIqQ/ZTr8M7pxItUs0kUixuE5gSRYxLsJ6eleR7QMldHGUc6wUpgm3BpheCblnHVcrwrBckJf1Uz0e8wReeijBHFsPo7kS72nT4JHqFp60xCguJzF4EPbQgDTefdCoHo21WzFdYD/0qXD051LNuXolpKV6h65Pb4+LlpB7\n","stats":{"OSType":"linux","Platform":"x86_64","Arch":"amd64","Cores":2,"Memory":1849,"MacAddress":"52:54:00:e3:4a:59","IP":"10.9.149.196","HostName":"10-9-149-196","VpcID":"","SubnetID":"","UserData":"","DiskMountList":[{"FsType":"xfs","Size":20470,"Avil":20296,"Device":"/dev/vdb","MountPoint":"/data","IsRootMountPath":false,"RemoteMountPath":"data1"},{"FsType":"xfs","Size":20469,"Avil":18792,"Device":"/dev/vda1","MountPoint":"/","IsRootMountPath":true,"RemoteMountPath":"data0"}],"ExcludeMountList":null},"time":"2024-04-03T14:56:26.095176541+08:00"}
```

## Windows启动方式

1. 使用微软远程桌面登陆源机器
2. 复制红框内的agent下载地址，使用浏览器下载至某个目录
3. 解压zip包，进入agent目录，双击go2ucloud.bat启动
4. 在打开的cmd界面中cat usmc_agent_log.txt可以看到收集的机器信息

> Windows下agent的启动界面如下所示，请保持该cmd窗口直到迁移任务完成

![](/images/agent_start_windows.png)

## agent上线

一般情况下，返回控制台，刷新一下，就可在未创建任务那一栏，看到有agent上线了

![](/images/agent_online.png)

> 如果没有看到任何在线的agent，可以通过agent log自行排查，或寻求技术支持

源端主机名，即对应于源机器的hostname，点击创建迁移任务开始下一步

