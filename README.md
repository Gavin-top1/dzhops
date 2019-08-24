# dzhops
+ 使用Django框架开发的Salt Stack Web UI
+ 开发语言: python;
+ 后端框架: Django;
+ 前端框架：bootstrap/jquery；

## 环境
+ RHEL 6.5 x86_64
+ salt-master 2015.5.3
+ salt-minion 2015.5.3
+ salt-api 2015.5.3
+ Django 1.6.8
+ python 2.6.6
+ MySQL 5.5

## dzhops更新记录
1. SaltStack相关功能（部署、更新、维护、远程）代码重构；
2. 视图文件拆分，新建立app：saltstack/record/managekeys；
3. 使用json格式通过接口传递数据，提高代码重用率；
4. 远程操作的jid及返回结果相关信息入库；
5. 对返回结果按IP进行排序；
6. 返回结果展示按钮增加上下距离；
7. 前端各选项左右对齐；
8. 远程命令执行返回结果显示优化；

## 功能介绍
1. **登陆页面**
![登陆](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/login.png)
2. **首页**，显示SaltMaster所在服务器及相关组件状态信息
目前监控数据，都是通过独立的信息采集脚本完成，需要做计划任务。
![仪表盘](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/index.png)
3. **主机列表**
进入主机列表界面，可以选择机房和维护人员；服务器相关的信息支持自动采集；
![主机列表](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/asset.png)
4. **SaltStack**
可完成如下功能：服务器初始化（如模块部署等）、程序、配置更新、日常维护操作、批量远程命令执行，当对Minion执行操作时，会记录本次目标Minion的数量，然后与返回结果的Minion数量进行对比，找出哪些没有返回结果；当接收到返回结果后，使用bootstrap的模态框显示结果，其中蓝色表示执行成功，红色表示有失败存在，可以点击标签查看详细情况；
![模块部署](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/deploy.png)
![模块部署-返回结果-模态框展开-失败情况](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/deploy_show.png)
![模块部署-返回结果-模态框展开-成功情况](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/deploy_show_success.png)
![远程命令执行](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/execute.png)
5. **MinionKeys管理**
可以分别选择已接受、待接受、已拒绝，并且可以选择机房及维护人员，进行对应的管理操作；
![MinionKeys管理](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/manage.png)
6. **操作记录**
可以记录每次操作执行人的账号、操作、目标、及jid，并可以通过jid查看该次操作的返回结果详细情况。
![操作记录](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/record.png)
![操作记录-详细](https://github.com/Hasal/dzhops_picture/blob/master/dzhops_pic/record_detail.png)

