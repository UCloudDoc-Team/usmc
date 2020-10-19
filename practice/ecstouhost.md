# 如何从阿里云ECS迁移至UCloud快杰云主机

## 迁移前准备

- 如果通过外网迁移，阿里云ECS需要有外网出口
- 如果要迁移网络，需要有AliyunECSReadOnlyAccess 和 AliyunVPCReadOnlyAccess 权限的阿里云AKSK
- 确认源端系统版本及磁盘大小在USMC支持范围中

## 操作步骤

![](http://usmc-doc.cn-bj.ufileos.com/practice001.png)

### 创建迁移计划

![](http://usmc-doc.cn-bj.ufileos.com/practice002.png)

### 进行网络迁移

点击 获取网络资源 输入 阿里云拥有ECS/VPC只读权限的账号AKSK

![](http://usmc-doc.cn-bj.ufileos.com/practice003.png)

选择想要迁移的服务器所在VPC

![](http://usmc-doc.cn-bj.ufileos.com/practice003.png)

如阿里云ECS所在网段与UCloud公共服务网段冲突，可进行更换后再迁移

### 进行Agent上报

登陆ECS

下载压缩包并解压 地址：http://usmc.cn-bj.ufileos.com/UCloud_Server_Migration_Agent.zip

```
unzip UCloud_Server_Migration_Agent.zip

unzip usmc_client_linux_x86_64.zip
```

配置启动脚本并启动

在usmc_agent.sh中输入用户的迁移计划 ID（set_id的部分），和 usmc_client_linux_x86_64 文件保存在同一个目录下

```
set_id=usmc-xxxxxx //修改为迁移计划ID
```

```
./usmc_agent.sh
```

启动后，状态变更为 agent在线

![](http://usmc-doc.cn-bj.ufileos.com/practice006.png)

### 创建迁移任务并启动

![](http://usmc-doc.cn-bj.ufileos.com/practice007.png)

费用为创建中转机及硬盘费用。

期间可查看迁移进度

![](http://usmc-doc.cn-bj.ufileos.com/practice008.png)

![](http://usmc-doc.cn-bj.ufileos.com/practice009.png)


### 创建云主机

![](http://usmc-doc.cn-bj.ufileos.com/practice010.png)

![](http://usmc-doc.cn-bj.ufileos.com/practice011.png)

