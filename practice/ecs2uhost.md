# 如何从阿里云ECS迁移至UCloud快杰云主机

## 创建迁移计划

![](/images/ecs2uhost_create_set.png)

创建一个新的迁移计划，迁移源选择阿里云

## 下载agent并启动

![](/images/ecs2uhost_url.png)

点击详情，进入迁移计划，可以看到agent下载链接，点击红框内的按钮复制

ssh登陆阿里ecs，参考如下步骤操作

```
# 1. 安装wget和unzip
[root@10-9-125-252 ~]# yum install wget unzip -y
上次元数据过期检查：0:00:22 前，执行于 2024年04月10日 星期三 15时48分56秒。
软件包 wget-1.19.5-10.el8.x86_64 已安装。
软件包 unzip-6.0-45.el8_4.x86_64 已安装。
依赖关系解决。
无需任何处理。
完毕！

# 2. 拷贝控制台的agent下载链接执行
[root@10-9-125-252 ~]# wget http://usmc-pre-file.cn-bj.ufileos.com/9c1a1d6a-f145-41c9-a539-e65016aad7eb/UCloud_Server_Migration_Agent_usmc-w3vhned8sjv_99c6be8522a8.zip && unzip UCloud_Server_Migration_Agent_usmc-w3vhned8sjv_99c6be8522a8.zip
--2024-04-10 15:49:28--  http://usmc-pre-file.cn-bj.ufileos.com/9c1a1d6a-f145-41c9-a539-e65016aad7eb/UCloud_Server_Migration_Agent_usmc-w3vhned8sjv_99c6be8522a8.zip
正在解析主机 usmc-pre-file.cn-bj.ufileos.com (usmc-pre-file.cn-bj.ufileos.com)... 202.189.11.203
正在连接 usmc-pre-file.cn-bj.ufileos.com (usmc-pre-file.cn-bj.ufileos.com)|202.189.11.203|:80... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度：62293864 (59M) [application/zip]
正在保存至: “UCloud_Server_Migration_Agent_usmc-w3vhned8sjv_99c6be8522a8.zip”

UCloud_Server_Migra 100%[===================>]  59.41M  62.5MB/s  用时 1.0s

2024-04-10 15:49:29 (62.5 MB/s) - 已保存 “UCloud_Server_Migration_Agent_usmc-w3vhned8sjv_99c6be8522a8.zip” [62293864/62293864])

Archive:  UCloud_Server_Migration_Agent_usmc-w3vhned8sjv_99c6be8522a8.zip
   creating: usmc-w3vhned8sjv/
  inflating: usmc-w3vhned8sjv/usmc_client_linux_x86_64
  inflating: usmc-w3vhned8sjv/usmc_client_windows_x86_64
  inflating: usmc-w3vhned8sjv/go2ucloud.bat
  inflating: usmc-w3vhned8sjv/usmc_client_linux_x86_64_centos5
 extracting: usmc-w3vhned8sjv/agent_config.conf
  inflating: usmc-w3vhned8sjv/utils.exe
  inflating: usmc-w3vhned8sjv/go2ucloud.sh

# 3. 进入agent目录并执行启动脚本
[root@10-9-125-252 ~]# cd usmc-w3vhned8sjv/
[root@10-9-125-252 usmc-w3vhned8sjv]# ./go2ucloud.sh
usmc agent started
```

## 创建迁移任务

![](/images/ecs2uhost_agent_online.png)

回到控制台，刷新一下，可以发现agent已经上线，点击创建迁移任务

![](/images/ecs2uhost_create_task.png)

根据需要，填写合适的参数，点击立即购买，立即支付（此阶段并不会实际付费）

## 等待迁移完成

![](/images/ecs2uhost_start_task.png)

找到刚刚创建的迁移任务，点击启动，等待迁移完毕。