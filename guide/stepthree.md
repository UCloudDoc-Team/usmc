# 步骤三 创建迁移任务

## 操作步骤

进入资源迁移（IDC模式下进入迁移计划详情即可）

![](http://usmc-doc.cn-bj.ufileos.com/stepthree001.png)

下载agent至源端服务器

> 注意：每个迁移计划的下载地址都不相同， 请勿混用。

![](http://usmc-doc.cn-bj.ufileos.com/downloadAgent20210126.png)

- 点击右上角的“复制”按钮复制完整下载及解压命令
- 在待迁移主机上执行（如果待迁移主机无法访问下载源， 请通过可访问的机器中转）完成下载与解压
- 执行以下命令启动agent

```
cd usmc-XXXXX
./start_usmc_agent.sh 
```

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


