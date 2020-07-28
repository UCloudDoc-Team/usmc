# 步骤三 创建迁移任务

## 操作步骤

进入资源迁移（IDC模式下进入迁移计划详情即可）

![](http://usmc-doc.cn-bj.ufileos.com/stepthree001.png)

下载agent至源端服务器

![](http://usmc-doc.cn-bj.ufileos.com/stepthree002.png)

agent地址：http://usmc.cn-bj.ufileos.com/UCloud_Server_Migration_Agent.zip

解压压缩包

unzip UCloud_Server_Migration_Agent.zip

unzip usmc_client_linux_x86_64.zip

配置启动脚本并启动

在usmc_agent.sh中输入用户的迁移计划 ID（set_id的部分），和 usmc_client_linux_x86_64 文件保存在同一个目录下

#!/bin/bash

# UCloud SMC 迁移计划ID

set_id=usmc-xxxxxx

# 运行前，先检查是否已经有 agent 已经在运行

COUNT=`ps -ef|grep usmc_client_linux_x86_64|grep setID|grep -v grep|wc -l`

if [[ "$COUNT" > 0 ]]; then

        echo "usmc agent is already running, you must stop it first"

  exit 1

fi

nohup ./usmc_client_linux_x86_64 \

    -setID=${set_id}  \

    >> usmc_agent_log.txt 2>&1 &

sleep 6s

COUNT=`ps -ef|grep usmc_client_linux_x86_64|grep setID|grep -v grep|wc -l`

if [[ "$COUNT" = 1 ]]; then

        echo "usmc agent started"

else

  echo "usmc agent start failed"

fi



./usmc_agent.sh 

![](http://usmc-doc.cn-bj.ufileos.com/stepthree003.png)

启动后观察到任务状态为 agent在线

![](http://usmc-doc.cn-bj.ufileos.com/stepthree004.png)
