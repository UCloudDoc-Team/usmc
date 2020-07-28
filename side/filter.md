# 文件过滤

如用户想某些目录，文件，过大或对业务影响较小不想被迁移。可以是用文件过滤。

具体使用方式：

1 修改agent启动脚本，usmc_agent.sh

```
setId=usmc-yeryrs1z

excludeFile="/root/exclude/ruleFiles.txt"

nohup ./usmc_client_linux_x86_64 \
-setID=${set_id} -excludeRulesFile=${excludeFile} \
>> usmc_agent_log.txt 2>&1 &

```

ruleFiles.txt文件中存放过滤规则，规则如下：

| 规则         | 说明                                               |
| :----------- | :------------------------------------------------- |
| *.o          | 排除所有以.o结尾的文件                             |
| /data/*/test | 排除/data目录隔一级目录下的 test文件或者文件夹     |
| /foo         | 排除根目录下名称为foo的文件或者文件夹              |
| /foo/**/bar  | 排除/foo目录下以及所有子目录下的bar 文件或者文件夹 |
| foo/         | 排除所有名为foo的文件夹                            |
| test.txt     | 排除所有名为test.txt的文件                         |
| testdd       | 排除所有名为testdd的文件或者文件夹                 |

