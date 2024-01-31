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


#### 5 问：专线/内网迁移启动任务报错: exit status 255 , errorInfo: ssh: connect to host 10.10.23.114 port 22: Connection timed out

内网和专线迁移源机器和目标机器网络必须打通


#### 6 问: 启动任务报错 unetfe-internal.AllocateEIP user has no permission

错误详情:
```
StartSMCTask- Message:create transmit uhost failed [create uhost instance failed, code: 8433，errMsg: EIP.AllocateEIP: action error:  unetfe-internal.AllocateEIP user has no permission] 
```

原因：

新用户没有开启eip 流量计费的权限。联系客户经理找相关部门开通权限


#### 7 问: 启动任务报错 prepare check failed grub2 version is too old

错误详情:
```
server error [prepare check failed grub2 version is too old: grub2-2.02-0.44.el7.centos.x86_64, please execute 'yum update grub2', 'grub2-install /dev/vda'] 

```

原因:

源机器grub2版本过低，需要升级。 执行以下命令升级(系统盘根据实际情况替换，举例使用 /dev/vda)

```
yum update grub2

grub2-install /dev/vda
```

#### 8 问: 启动任务报错 resource not enough 资源不足


错误详情:
```
create uhost instance failed, code: 8357，errMsg: resource not enough (uhost-hic-apiServer.GetHosts)  resource not enough
```

原因:

选择的机型配置在当前可用区资源不足，尝试更换机型配置可用区等解决。


