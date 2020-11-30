#### 1 问：是否支持AWS/腾讯云迁移到UCloud?

支持，创建迁移计划时源选择"IDC"方式。

#### 2 问：阿里云迁移方式和 IDC 迁移方式的区别是什么?

阿里云迁移方式支持网络迁移,包括VPC及子网等。迁移每台机器默认会保留原机器的信息， 如VPC，内网IP等。 而IDC的方式需要自建VPC及子网。

#### 3 问： IDC方式迁移,是否支持指定IP?

支持, 在创建子网后, 可以在该子网内指定内网IP创建目标云主机.

#### 4 问： 阿里账号AK如何申请?

控制台以阿里旧版本为例 https://ram.console.aliyun.com/users#/user/list， 分两种情况：

##### 如无用户情况
- 新建用户

![](http://usmc-doc.cn-bj.ufileos.com/faq/usmc-ali-key1.png)

- 生成AccessKey

![](http://usmc-doc.cn-bj.ufileos.com/faq/usmc-ali-key2.png)

- 用户“授权”

![](http://usmc-doc.cn-bj.ufileos.com/faq/usmc-ali-key4.png)

##### 如有用户情况

进入用户管理创建 AccessKey，再对用户进行“授权”操作。

![](http://usmc-doc.cn-bj.ufileos.com/faq/usmc-ali-key6.png)
