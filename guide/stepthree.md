# 步骤三 创建迁移任务

## 操作步骤

进入资源迁移（IDC模式下进入迁移计划详情即可）

![](http://usmc-doc.cn-bj.ufileos.com/stepthree001.png)

下载agent至源端服务器

![](http://usmc-doc.cn-bj.ufileos.com/stepthree002.png)

agent地址：http://usmc.cn-bj.ufileos.com/UCloud_Server_Migration_Agent.zip

解压压缩包
```
unzip UCloud_Server_Migration_Agent.zip
unzip usmc_client_linux_x86_64.zip
```

配置参数

在agent_config.conf中输入用户的迁移计划 ID（set_id的部分）。如果选择通过内网（专线）方式迁移， 需要同时配置region变量。 

```
# USMC agent 配置文件
# 迁移计划ID，请修改下面值
setID=usmc-xxxx

# 如果是通过内网（专线）迁移，请填写正确的地域(cn-bj2, cn-sh2, cn-gd). 通过外网迁移不需要填写。
#region=cn-bj2
```

./start_usmc_agent.sh 

> 注意：启动脚本的账号需要有访问所有迁移文件的权限， 建议使用有root权限的账号。

![](http://usmc-doc.cn-bj.ufileos.com/stepthree003.png)

启动后观察到任务状态为 agent在线

![](http://usmc-doc.cn-bj.ufileos.com/stepthree004.png)

点击 创建迁移任务

![](http://usmc-doc.cn-bj.ufileos.com/stepThree005.new.png)

CPU平台：默认为Intel/Cascadelake, 用户可根据需要调整为AMD平台。 

传输限速：1-300Mbps 根据用户源端网络情况，用户可使用限速保证自身网络不会因为usmc的使用而被影响，不填默认100Mbps按流量计费。

预约执行：可定时启动USMC 任务

是否开启增量：按一定频率进行增量文件传输

![](http://usmc-doc.cn-bj.ufileos.com/stepthree006.png)

并点击启动（预约执行无需点击）


