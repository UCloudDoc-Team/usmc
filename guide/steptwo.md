# 步骤二 网络迁移（可选）

只有迁移源为“阿里云”时才有此步骤。 使用IDC类别迁移请直接转到步骤三， 但需要在UCloud控制台提前创建好需要使用的VPC及子网。

## 操作步骤

- 进入迁移计划详情

![](http://usmc-doc.cn-bj.ufileos.com/steptwo001.png)

- 点击 获取网络资源

![](http://usmc-doc.cn-bj.ufileos.com/steptwo002.png)

- 填写符合要求的阿里云Access Key /Secret Key并点击 获取VPC列表

![](http://usmc-doc.cn-bj.ufileos.com/steptwo003.png)

- 选择需要迁移的云主机所在VPC，并点击 迁移

![](http://usmc-doc.cn-bj.ufileos.com/steptwo004.png)

是否进行网络迁移：勾选将会在目标测创建所需迁移VPC同配置的VPC及其子网，且云主机会默认迁移至创建出的对应子网中。 不勾选则跳过网络迁移，如果用户之前未进行过网络迁移，需要自行在UCloud创建VPC及子网。 默认勾选。

- 查看是否有网段冲突

![](http://usmc-doc.cn-bj.ufileos.com/steptwo005.png)

注：如有网段冲突，会有提示，请用户更换网段。

![](http://usmc-doc.cn-bj.ufileos.com/steptwo006.png)

迁移进度中显示的是这子网下有多少台服务器。
