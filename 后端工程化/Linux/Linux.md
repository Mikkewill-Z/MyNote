## 准备
下载安装vamware虚拟机管理器
创建虚拟机
## Linux目录
### 介绍
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695700670222-4f1eac41-50ad-4dcf-ba06-ba5601147403.png#averageHue=%23e9e9e6&clientId=ud084656f-8ad2-4&from=paste&height=448&id=ub5c598d9&originHeight=616&originWidth=684&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=307483&status=done&style=none&taskId=u9ca80ea4-a69c-40a7-8021-29300c82cb5&title=&width=497.45454545454544)
root用户的家目录存在于此(普通用户的家目录在home中)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695700807343-75163ff1-7b77-44da-af83-86ac4be45e2d.png#averageHue=%23f5f0e7&clientId=ud084656f-8ad2-4&from=paste&height=363&id=u7bfe903a&originHeight=499&originWidth=854&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=39486&status=done&style=none&taskId=u770367b2-f517-4912-846e-10b635dc51b&title=&width=621.0909090909091)
### 重点目录
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695699865930-a8fadb40-ba45-46ff-a9a5-355f8542ba06.png#averageHue=%23f2ede2&clientId=ud084656f-8ad2-4&from=paste&height=316&id=uc90b9f74&originHeight=434&originWidth=1023&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=186306&status=done&style=none&taskId=uf628eb27-59a3-476b-9933-467aa9085f1&title=&width=744)
**1.bin为命令目录**
**2.sbin为超级管理员命令目录**
**3.home为普通用户家目录 /home/xxx**
**4.root为超级管理员家目录 /root**
**5.etc放系统的配置文件**
配置jdk  jre都在此目录下
**6.mnt挂载文件**
**7.opt软件安装目录**
**8./user/local**
user是默认的安装位置
另外的给额外安装软件存放的目录,一般通过编译源码方式安装程序
## 编辑器
使用终端--->可视为windows的命令窗口
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695708939696-38c0274d-8d81-4274-b194-219a24f67673.png#averageHue=%239cc3c8&clientId=ud084656f-8ad2-4&from=paste&height=169&id=ud42be041&originHeight=233&originWidth=411&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=79415&status=done&style=none&taskId=uc4cab171-ca2a-4ce8-a29d-ae6a1f831cb&title=&width=298.90909090909093)
### 基础命令
ll--->查看目录下的所有文件
mkdir  文件名--->新建名为 文件名 的文件
cd 文件名--->进入名为 文件名 的文件
cd .. --->退出当前文件夹(回到上一级)(cd和..之间要有空格)
pwd--->查看当前位置
cd ~ --->回到家目录(cd后啥也不加或者只加个 ~ 符号)
cat 文件名加后缀  ----> 查看 文件名 之中的内容
:q----->退出
### 基础操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695709545199-1b373938-2899-41de-bb62-b7566fabedd8.png#averageHue=%23fefefb&clientId=ud084656f-8ad2-4&from=paste&height=119&id=u9a77bc6a&originHeight=164&originWidth=668&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=36082&status=done&style=none&taskId=ua4a909e6-02c9-4a4c-a11b-c752dadc3db&title=&width=485.8181818181818)
1.赋值路径下的smart.conf文件到root家目录之下
2.进入家目录
3.将家目录下的文件进行列表展示

### 编辑器模式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695714064455-4e6112c3-4c27-46ea-a05d-a361576cf403.png#averageHue=%23fdfdf9&clientId=ud084656f-8ad2-4&from=paste&height=297&id=u7737177c&originHeight=409&originWidth=846&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=247130&status=done&style=none&taskId=u485cfb57-3cd2-46f1-b889-d3ef3a63795&title=&width=615.2727272727273)
#### 一般模式
##### 进入方式:
[路径可以是绝对路径(/开头)也可以是相对路径(.开头或者../开头)]
vi 文件的路径
vim 文件的路径
##### 功能:
复制内容,粘贴内容,删除内容,移动光标位置
不能通过键盘进行编辑
##### 操作:
dd ----> 删除光标当前行
dnd ----> 删除n行
u ----> 撤销上一步
x/X ----> 删除一个字母 x往后删除 X往前删除
yy ----> 复制光标当前行
yny ----> 复制n行
p ----> 粘贴
dw ----> 删除一个词
yw ----> 删除一个词

^ 行首
$ 行尾
gg/1加G 首行
G 尾行
n加G 去到第n行
ZZ 保存并退出
隐藏文件显示--->ls - al
如果意外退出,则需要删除当前目录下的一个隐藏文件 --->.文件名.后最.swp
rm -rf .smart.conf.swp
rm -rf  删除其后写的文件
#### 编辑模式
##### 功能:
通过键盘编辑
##### 如何进入:
前提:从一般模式进去
命令: i a o I A O [最常用的是 i  ]
##### 操作:
想要在哪里插入就在哪里输入i
i是在当前光标前开始
a是在当前光标后开始
o是在下一行

I是最前面
A是在最后面
O是在上一行
##### 如何退出:
esc
#### 命令模式
##### 前提:
必须由一般模式进入
编辑模式和命令模式是不互通的
必须通过一般模式来进行切换
##### 功能:
:q  退出
:w  保存
:wq 保存并退出 <----> 也可以使用ZZ进行保存并退出
:!  强制
:q!  强制退出但不保存
:set nu  显示行号
:set nonu  隐藏行号
/某  搜索文件中的  某 并且高亮显示 
使用n和N来进行调整上下
::%s/old/new/g  替换内容  /g替换匹配到的所有内容	[不加g的情况是只替换每行第一个符合的]
## 网络设置
### ifconfig
使用 ifconfig 来查看ip地址
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695714286385-4c01ee74-a5b3-4c3a-991f-76668281eaed.png#averageHue=%23eeeeea&clientId=ud084656f-8ad2-4&from=paste&height=308&id=uc71428b4&originHeight=424&originWidth=820&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=251899&status=done&style=none&taskId=ub7779c8c-336e-40de-8bf9-da698e5fde8&title=&width=596.3636363636364)
ping外部网络即可查看是否互通
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695714355391-ab988733-49f3-4e08-8723-cf974dfa05da.png#averageHue=%23ecece8&clientId=ud084656f-8ad2-4&from=paste&height=248&id=u35071a91&originHeight=341&originWidth=661&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=216019&status=done&style=none&taskId=u34911786-90ec-41e7-96d1-147983cf300&title=&width=480.72727272727275)
### 配置虚拟机网络
相关:  配置虚拟机网络一般给运维人员进行处理,一般是使用远程服务器
#### 目标: 
静态ip[使ip地址不会轻易进行变动]

#### 介绍:
虚拟机设置--->网络适配器
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695714568599-e5ab2cda-d398-4ae7-beb3-f774b3b33d0c.png#averageHue=%23f6f6f2&clientId=ud084656f-8ad2-4&from=paste&height=305&id=u3b0b3905&originHeight=420&originWidth=705&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=191755&status=done&style=none&taskId=u107e11ea-ae76-4682-af48-83e11adac4c&title=&width=512.7272727272727)

##### 桥接模式:
相互连接的主机之间是互联的,互联的主机的虚拟机也是互联的,但虚拟机之间设置的  网段和端口号  不可以相同(虚拟机和自己主机之间网段得是相同的,端口号也不能相同)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695715069243-8c72d6f0-4a92-465b-84da-2bf82521ac1f.png#averageHue=%23f1f4f0&clientId=ud084656f-8ad2-4&from=paste&height=463&id=uea39c453&originHeight=636&originWidth=930&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=507680&status=done&style=none&taskId=ua2e3d880-ffc0-4e70-a866-1028ae77b0b&title=&width=676.3636363636364)

##### NAT模式:(要设置新的网段)
NAT模式 又称  _网络地址转换_
虚拟机的网段可以自己定义,虚拟机的端口号可以相同,但是互联的主机的虚拟机虽然端口号可以相同,相对的它们之间是不互联的
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695714933588-3f953322-e10b-4dbb-949c-8c1b5f3be55d.png#averageHue=%23f2f5f1&clientId=ud084656f-8ad2-4&from=paste&height=396&id=u2b586294&originHeight=544&originWidth=900&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=433838&status=done&style=none&taskId=ub51a8c2c-ec6a-48c4-925c-1059143d54d&title=&width=654.5454545454545)

#### 配置:
##### 配置虚拟机的网络
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695715704753-1742ea26-5e6a-41ec-a421-10d56ce5b573.png#averageHue=%23f3f3ee&clientId=ud084656f-8ad2-4&from=paste&height=158&id=u0b6ba19e&originHeight=217&originWidth=408&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=58261&status=done&style=none&taskId=u1993d31d-4afa-4810-b541-7c478da84d5&title=&width=296.72727272727275)
打开后配置管理员权限
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695715737990-60d6b093-e04c-430a-afa1-087c98fdee56.png#averageHue=%23f0f0ec&clientId=ud084656f-8ad2-4&from=paste&height=224&id=udd9748bf&originHeight=308&originWidth=536&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=102238&status=done&style=none&taskId=uf75c29dd-bc72-4b80-94c3-788d39424f7&title=&width=389.8181818181818)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695715832697-337abb34-a78d-4993-bb28-92676ffeb8c5.png#averageHue=%23f5f7f2&clientId=ud084656f-8ad2-4&from=paste&height=97&id=u9a4bb8b4&originHeight=134&originWidth=555&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=46723&status=done&style=none&taskId=ua271e7fe-8b88-4ae7-b0fc-7eb16d78e8f&title=&width=403.6363636363636)

下方的子网ip就是我们想设置的端口号
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695715860149-cb65f3f3-6e9c-4f5a-90d6-45f4911816a0.png#averageHue=%23e6e6e2&clientId=ud084656f-8ad2-4&from=paste&height=44&id=uc6fe879d&originHeight=60&originWidth=411&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=23031&status=done&style=none&taskId=udb3d7c13-27f0-4439-b193-fed88095d7c&title=&width=298.90909090909093)

设置完成点击nat设置,修改网关为 192.168.6.2
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695715957792-aa445959-79f6-406d-b502-6af3e1381698.png#averageHue=%23eff0eb&clientId=ud084656f-8ad2-4&from=paste&height=128&id=u92922bbe&originHeight=176&originWidth=370&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=35385&status=done&style=none&taskId=u3d6adf24-233c-4386-910c-471d059f4dc&title=&width=269.09090909090907)
##### 配置linux系统的ip
网络地址转换,有两块网盘(ens33连接外网)
###### 1.修改虚拟机ens33网卡的网络配置信息
vim /etc/sysconfig/network-scripts/ifcfg- ens33
###### 2.首先修改其内的自动配置信息为静态
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695717908967-c0cb598f-b3ae-4505-91cb-7b5e42255cbd.png#averageHue=%23f5f5f1&clientId=u7228f237-9494-4&from=paste&height=345&id=u8bc84b2d&originHeight=474&originWidth=531&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=148846&status=done&style=none&taskId=ue642dc02-da8e-461e-936c-59edcab3a0d&title=&width=386.1818181818182)
###### 3.对其内的属性的修改
BOOTPROTO="static" #静态网址(已有)
ONBOOT="yes" #开机启用(已有)
IPADDR="192.168.6.100" #ip地址(增加)
GATEWAY = "192.168.6.2" #网关(增加)
DNS1="192.168.6.2" #DNS域名解析 (增加) 114.114.114.114 / 8.8.8.8
###### 4.重启网络服务
systemctl restart network
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695718739219-50a62cde-e5c2-470e-a571-ccc3d5fb8a22.png#averageHue=%23f6f6f1&clientId=u7228f237-9494-4&from=paste&height=136&id=uc798bf45&originHeight=187&originWidth=751&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=154324&status=done&style=none&taskId=ub32d2a3a-ef17-4b13-8549-092c9c98726&title=&width=546.1818181818181)
###### 5.配置windows系统的vmnet8网卡的ip
在cmd内使用使用ipconfig进行查看
修改:
网络和internet---->高级网络设置--->网络适配器---->vmnet8右键属性--->进入ip4后进行如下修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695718625666-897c3d2e-c78b-4ad5-b919-504a767ff9b4.png#averageHue=%23f2f2ee&clientId=u7228f237-9494-4&from=paste&height=307&id=u526de30f&originHeight=422&originWidth=589&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=180932&status=done&style=none&taskId=ufc4e04c6-0173-4eb5-a103-e08d90224dc&title=&width=428.3636363636364)
###### 6.修改主机名
etc下有个hostname,在其内进行修改
vim/etc/hostname
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695718873240-ec997103-f0ff-413b-922e-73a59ad80024.png#averageHue=%23cfd1cf&clientId=u7228f237-9494-4&from=paste&height=72&id=u9aa6abdc&originHeight=99&originWidth=519&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=36719&status=done&style=none&taskId=u4f4163b3-bd53-454b-905a-69ea73dbd9c&title=&width=377.45454545454544)
###### 7.修改映射
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695722457774-ee0ca5ae-7449-4add-a479-356f724b0d20.png#averageHue=%23fdfdf9&clientId=u7228f237-9494-4&from=paste&height=106&id=uba4338be&originHeight=146&originWidth=369&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=18272&status=done&style=none&taskId=u48c32f06-2876-4573-8486-536f0331b25&title=&width=268.3636363636364)
此语句的意思是  使用linux100代替192.168.6.100这个ip
###### 8.重启进行刷新
重启命令为reboot
关机命令为poweroff


## 远程工具使用
WindTerm的安装与使用
1.下载安装
### 2.使用:
连接上后设置密码
进入后可以正常使用
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695728453030-9867addf-71b9-4533-a546-dd34c52cc7e0.png#averageHue=%23232221&clientId=u7228f237-9494-4&from=paste&height=393&id=uec983d67&originHeight=541&originWidth=838&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=66777&status=done&style=none&taskId=ufe8bab6a-b196-4c26-95a6-cf7ef85bf75&title=&width=609.4545454545455)
#### a.通过远程工具向linux传文件
传给linux安装包之类
可视化工具![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695728932196-8d03b89b-2305-468b-9be2-87195b0e8b74.png#averageHue=%232a2a28&clientId=ubf9e8161-73d3-4&from=paste&height=350&id=u10babbdc&originHeight=481&originWidth=695&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=368513&status=done&style=none&taskId=u4f1087b3-7f4c-44a2-ba73-066eeaeb335&title=&width=505.45454545454544)
完成文件上传![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695729123050-3c75a91f-25f6-473a-9669-289c8aab90fc.png#averageHue=%231f1d1d&clientId=ubf9e8161-73d3-4&from=paste&height=442&id=u87ea1faf&originHeight=608&originWidth=836&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=80622&status=done&style=none&taskId=uea1052dc-1afa-4a24-b046-9a97657582b&title=&width=608)
## 命令分类
### 服务管理类
#### _临时开关服务命令_
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695724901614-d7e40206-880f-493b-9bee-28bf2ae81881.png#averageHue=%23fbfbf7&clientId=u7228f237-9494-4&from=paste&height=168&id=u5ea0441f&originHeight=231&originWidth=458&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=75531&status=done&style=none&taskId=u4980562d-ea6a-4c6f-ab31-3fe2dee5f63&title=&width=333.09090909090907)
##### 使用:
1.ping baidu.com 查看网络是否能够正常连接
2.systemctl -- type service  查看所有的服务
3.停止与打开服务
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695725503845-5a981c43-578f-4c65-962e-c38cfb9477c5.png#averageHue=%23ebebe8&clientId=u7228f237-9494-4&from=paste&height=66&id=u33eb5855&originHeight=91&originWidth=499&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=35177&status=done&style=none&taskId=ued9c2ae9-86ad-455d-b28c-0382fa04c55&title=&width=362.90909090909093)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695725482098-ea35d7cb-163f-447c-abe6-94ff7e694d3b.png#averageHue=%23f1f1ee&clientId=u7228f237-9494-4&from=paste&height=54&id=u6d62a386&originHeight=74&originWidth=582&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=32089&status=done&style=none&taskId=uc216ac36-b9ef-4beb-856d-a1abdd29b20&title=&width=423.27272727272725)
systemctl --type service ----> 查看所有服务
systemctl status 服务名 ---->  查看指定服务
systemctl stop 服务名 ---->  关闭指定服务
systemctl start 服务名 ---> 打开指定服务
systemctl restart 服务名 ---> 重启指定服务
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695725872096-7b03bdcb-0572-408a-aa7c-ec46a2827e52.png#averageHue=%23f0f0ed&clientId=u7228f237-9494-4&from=paste&height=48&id=uef7f4024&originHeight=66&originWidth=483&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=27192&status=done&style=none&taskId=ub075b36e-9d83-41b5-ad30-350b403a6eb&title=&width=351.27272727272725)
在学习中防火墙服务一般要处于关闭状态
因此引入下一阶段的 _ 永久开关服务命令_
#### _永久开关服务命令_
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695726029040-ec4a4d36-4356-40c0-8462-e388b9093475.png#averageHue=%23d3d8d3&clientId=u7228f237-9494-4&from=paste&height=108&id=ue0ac6f0d&originHeight=148&originWidth=485&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=90898&status=done&style=none&taskId=u77078504-ecf6-4869-ab05-1c75de17b8f&title=&width=352.72727272727275)
永久关闭防火墙的自启动
systemctl disable firewalld

#### 注意
检查网络与端口是否正确畅通
1.使用linux 去ping 一个外网网址
2.使用windows命令行窗口去ping linux
3.使用linux去ping windows
4.如果都能ping通则连接无误

### 文件目录类
**pwd打印当前目录的绝对路径**
#### ls(list)列出目录内容
ls-l 列出目录的内容并展示出详细信息
ls-a 列出当前目录下的隐藏文件
ls-al 列出当前目录下的隐藏文件的详细信息
#### cd(change directory)切换路径
cd 绝对路径
cd 相对路径
cd ~ 或者 cd  回到自己的家目录
_注意这里的上一次和上一级_
cd - 回到上一次所在目录
cd .. 回到当前目录的上一级目录

cd -P 跳转到实际物理路径,而 _非快捷方式(软连接硬连接) _路径
cd /  回到系统根目录

#### mkdir(make directory)建立目录
创建一个目录
mkdir zhuzhu
mkdir zhuzhu/zhuzhuzi
创建多级目录
mkdir -p  zhuzhu/zhuzhuzi/chidiao
#### rmdir(remove directory)删除目录
rmdir要删除的是_空目录,也只能删除空目录_
#### touch 创建空文件
touch 文件名称
然后就可以进入(通过vim)此文件之中进行编写
vim本身也具有创建文件的功能
vim hello.txt,进入后会提示是个新的文件,可以进行编辑保存
之后使用cat进行查看文件具体内容
#### cp 复制内容
cp[选项] source dest   复制source文件到dest目录中
复制hello.java到aa目录中![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695731866822-8f14d7ff-973a-48c7-bb6e-6f6b9fc295f3.png#averageHue=%2331332d&clientId=ubf9e8161-73d3-4&from=paste&height=58&id=u4d5a8df4&originHeight=80&originWidth=476&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=53921&status=done&style=none&taskId=uff399c3b-07dd-495d-a343-62ce3db41aa&title=&width=346.1818181818182)
添加 -r 属性可以递归复制整个文件夹
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695732266771-266c6e65-d34d-4fd8-835a-2fd40aee8812.png#averageHue=%232b2c29&clientId=ubf9e8161-73d3-4&from=paste&height=118&id=uc7b771c6&originHeight=162&originWidth=678&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=136098&status=done&style=none&taskId=u56b34d2c-a310-42ca-a14d-20aecf6327a&title=&width=493.09090909090907)
将cd递归拷贝到aa中
#### rm移除文件或者目录
基本使用:
rm[选项] deleteFile
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695732319042-2415a122-f800-403d-bdcd-51c44338afdb.png#averageHue=%23fcfbf8&clientId=ubf9e8161-73d3-4&from=paste&height=180&id=ue088c3b3&originHeight=247&originWidth=649&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=67364&status=done&style=none&taskId=uce4d8c89-9f4b-4517-8224-81b6078a901&title=&width=472)
**_rm -rf 是不带提醒的 可以删目录也可以删文件_**
**_超好用_**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695732648416-b788f4a9-897b-4761-889f-bff036b116d4.png#averageHue=%2331392d&clientId=ubf9e8161-73d3-4&from=paste&height=76&id=uc9084e41&originHeight=104&originWidth=590&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=60035&status=done&style=none&taskId=u592a090f-cb18-4ee3-b148-40f753d067a&title=&width=429.09090909090907)
#### mv移动文件与目录或重命名
可以将其理解为剪切功能(路径相同就是重命名,路径不同就是剪切)
重命名
mv oldnamefile newnamefile
移动文件
mv /temp/movefile /targetfolder
#### cat查看文件内容
#### more文件分屏查看器
用于查看内容较多的文件
回车:往下翻
空格:往下一屏幕
q:立刻退出more
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695733136326-20f1e80e-488a-4ff7-8944-623198c60564.png#averageHue=%23fbfbf7&clientId=ubf9e8161-73d3-4&from=paste&height=249&id=u2a1b6d11&originHeight=343&originWidth=776&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=121372&status=done&style=none&taskId=u03f89c46-05ba-4e14-a80f-50d14b231b1&title=&width=564.3636363636364)
#### less分屏显示文件内容
注意它的搜索功能分为向上和向下
/字串  向下搜寻  n向下查找  N向上查找
?字串 想上搜寻   n向上查找  N向下查找
q 离开less
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695733480706-901430ce-e3dc-499b-8803-7492b1c07fed.png#averageHue=%23fafaf6&clientId=ubf9e8161-73d3-4&from=paste&height=219&id=ud6ee4ef3&originHeight=301&originWidth=742&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=134639&status=done&style=none&taskId=u9313c0dd-4e47-4474-adb2-9613dc81092&title=&width=539.6363636363636)

#### head显示文件头部内容
head 文件  查看文件头10行内容
head -n 5  文件   查看文件头5行内容,5可以是任意行数
#### tail显示文件尾部内容
tail 文件  查看文件尾10行内容
tail -n 8    查看文件尾8行内容,8可以是任意行数
#### echo 打印信息(打印环境变量常用)
如下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734114393-37df58f0-cc25-411a-8212-adc9373ca528.png#averageHue=%232c2c28&clientId=ubf9e8161-73d3-4&from=paste&height=159&id=u2c5d0d0a&originHeight=219&originWidth=605&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=158094&status=done&style=none&taskId=u19832c5a-5923-4bf4-882c-546a7c3f718&title=&width=440)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734088798-b7563693-f1a7-4010-a258-8fa6afe4ca33.png#averageHue=%23fcfcf8&clientId=ubf9e8161-73d3-4&from=paste&height=304&id=uff79bbbd&originHeight=418&originWidth=664&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=106217&status=done&style=none&taskId=u8bddf956-4041-414a-a65b-b89db4151a0&title=&width=482.90909090909093)
##### 常用:
**_打印环境变量_**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734147570-92be07f9-ecf4-427f-99d1-2c2d87c80b98.png#averageHue=%23414840&clientId=ubf9e8161-73d3-4&from=paste&height=92&id=u53ec7364&originHeight=126&originWidth=818&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=98632&status=done&style=none&taskId=ud52ab148-2d86-47ce-a92a-8828b85f54f&title=&width=594.9090909090909)
#### >>追加与 >覆盖
注意:这里的内容可以是任意命令,覆盖或者追加的是命令执行的结果
echo"内容" > 文件 -----> 对文件内容进行覆盖
echo"内容" >> 文件 ------>对文件内容进行追加
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734347519-edd1a2ea-3eef-4ca5-a4fb-536e469d40a0.png#averageHue=%23454a40&clientId=ubf9e8161-73d3-4&from=paste&height=174&id=u583eb35f&originHeight=239&originWidth=776&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=213721&status=done&style=none&taskId=u437a59e7-3bd6-4650-9d73-38dcfd8d737&title=&width=564.3636363636364)
#### In创建链接和软连接
主要使用的是软连接(相当于是windows的快捷方式)![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734640908-38891466-67a7-466a-a2fd-b10456ccd218.png#averageHue=%23fbfbf7&clientId=ubf9e8161-73d3-4&from=paste&height=161&id=u13a29f7b&originHeight=222&originWidth=861&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=120954&status=done&style=none&taskId=u949d38c0-a524-424c-9ed1-d87ff347d5f&title=&width=626.1818181818181)

操作aaln相当于是操作aa.java
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734815980-797e9641-514f-421f-9e36-cd6d872fe3f6.png#averageHue=%23272826&clientId=ubf9e8161-73d3-4&from=paste&height=252&id=u6b2fc133&originHeight=346&originWidth=779&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=293556&status=done&style=none&taskId=ud6e1e836-1373-4ed0-aba1-19a6182f0b4&title=&width=566.5454545454545)

主要是给目录建立软连接
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695734978279-01d81b84-50b4-4ffb-a3a2-2e3f26a4c662.png#averageHue=%23252623&clientId=ubf9e8161-73d3-4&from=paste&height=177&id=u535cf77e&originHeight=243&originWidth=782&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=193672&status=done&style=none&taskId=ue0882b7f-f4fc-4501-9e2e-59b76405dea&title=&width=568.7272727272727)
cd -p 跳转到实际的物理录井,而非快捷方式的路径 

![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742398546-5ecb7bec-745e-4740-ba9d-452b628b07e3.png#averageHue=%23262724&clientId=ubf9e8161-73d3-4&from=paste&height=268&id=u24ce2981&originHeight=368&originWidth=824&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=318493&status=done&style=none&taskId=u321c1146-6e3d-42e7-839e-53769cc0dd2&title=&width=599.2727272727273)
#### history 查看历史命令
### 快照和克隆
#### 快照
保持此刻电脑的状态,后期可以恢复
拍摄快照,保持某一个状态
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742664612-d44daf1c-8346-4de5-af5b-4b51f2cf9b60.png#averageHue=%23e1e4db&clientId=ubf9e8161-73d3-4&from=paste&height=543&id=u9bfd5b6e&originHeight=746&originWidth=1219&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=543504&status=done&style=none&taskId=u11e49029-72d1-4687-bc76-5dc413f1b51&title=&width=886.5454545454545)
当需要的时候可以恢复快找,恢复到快照的位置
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742703723-07695b52-5ec6-4102-8266-56b14192063c.png#averageHue=%23f4f4f0&clientId=ubf9e8161-73d3-4&from=paste&height=336&id=ub6fa9df6&originHeight=462&originWidth=644&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=171269&status=done&style=none&taskId=uf8bce385-ff59-470f-9590-6e5af14d93c&title=&width=468.3636363636364)
各种操作之后,如果想回到刚开始没有做的状态,就可以使用快照进行恢复,可以在做不确定的操作之间对代码进行备份
#### 克隆
将此刻的电脑完完整整的复制一份
相当于完完全全的多出一台电脑
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742907137-68894214-af0d-429c-a217-961c94c3d1bf.png#averageHue=%23e9e8e5&clientId=ubf9e8161-73d3-4&from=paste&height=385&id=u3bd8c39c&originHeight=530&originWidth=689&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=165797&status=done&style=none&taskId=u41752afa-8daf-4705-81a9-78aedfd8646&title=&width=501.09090909090907)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742927262-31bc602b-1f2d-4b58-8893-bc7a6f22b711.png#averageHue=%23cacac7&clientId=ubf9e8161-73d3-4&from=paste&height=292&id=u9e9db74a&originHeight=402&originWidth=607&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=69984&status=done&style=none&taskId=u0d1684c1-c28e-49c7-97b6-85731b51030&title=&width=441.45454545454544)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742962280-296579d9-b9c7-487a-a651-c7d0b562d0ff.png#averageHue=%23d4d5d1&clientId=ubf9e8161-73d3-4&from=paste&height=197&id=u82372c80&originHeight=271&originWidth=701&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=48555&status=done&style=none&taskId=u0dd5dc61-f747-4d21-9001-6ea4833e246&title=&width=509.8181818181818)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695742989306-0653e1aa-4bdb-4db5-b102-c13b4340e656.png#averageHue=%23f8f8f4&clientId=ubf9e8161-73d3-4&from=paste&height=167&id=u2b193d9e&originHeight=229&originWidth=246&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=55133&status=done&style=none&taskId=u9738ef53-0f97-405d-9917-04632b75ed7&title=&width=178.9090909090909)
最好将另一台的ip进行修改,主机名修改,映射关系进行修改
修改ip地址
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695743117117-145f4386-2dff-48fb-958e-7c56a42a81cf.png#averageHue=%23eaeae7&clientId=ubf9e8161-73d3-4&from=paste&height=39&id=u91e40e12&originHeight=53&originWidth=620&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=19989&status=done&style=none&taskId=u81821353-4b04-4d91-a261-29397c65577&title=&width=450.90909090909093)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695743094985-83bbf50c-c89b-4b1f-9dd4-9296358bbac7.png#averageHue=%23e3e6de&clientId=ubf9e8161-73d3-4&from=paste&height=161&id=ue17b818c&originHeight=222&originWidth=553&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=49884&status=done&style=none&taskId=u74611c50-fbe2-4aad-ae4e-00b4cb6c4af&title=&width=402.1818181818182)
修改主机名
etc/hostname
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695743147956-297a66c6-c16b-402b-baae-66fb589500db.png#averageHue=%23e0e1db&clientId=ubf9e8161-73d3-4&from=paste&height=65&id=u2b531b0d&originHeight=90&originWidth=178&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=10448&status=done&style=none&taskId=u17a27695-c962-44b0-b2e0-d06a68a0342&title=&width=129.45454545454547)
修改host映射关系
etc/hosts
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695743201762-215a1d90-45e2-4b14-a58c-a2a6e7ba8ffa.png#averageHue=%23e3e4dd&clientId=ubf9e8161-73d3-4&from=paste&height=60&id=u8207f1d0&originHeight=83&originWidth=310&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=15112&status=done&style=none&taskId=uda5cba9e-c2f5-48d7-a088-5104d4cb12f&title=&width=225.45454545454547)
重启刷新
systemctl restart network
### 用户管理与用户组管理
#### 用户组管理
相同权限用户归入一个组进行管理
##### 新增组-->groupadd
groupadd 组名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695777549381-6d496e3d-394a-4323-be21-dc989e10cc99.png#averageHue=%232c312c&clientId=u1b8d38f3-c523-4&from=paste&height=77&id=u2a0c9548&originHeight=106&originWidth=693&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=80438&status=done&style=none&taskId=u06c21e03-22ec-4c30-94a3-189b4a69470&title=&width=504)
##### 删除组-->groupdel 
groupdel  组名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695777567090-645b0121-5d60-4663-a737-7f0d3f1b1b2c.png#averageHue=%23242422&clientId=u1b8d38f3-c523-4&from=paste&height=108&id=u699d3151&originHeight=149&originWidth=786&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=76297&status=done&style=none&taskId=u5c692689-5e0d-4b3c-9f48-e3c55e91821&title=&width=571.6363636363636)
##### 查看组-->cat/etc/group
#### 用户管理
##### useradd-->添加新用户
useradd 用户名 (添加新用户)--->会新建一个同名的组,在组里创建一个 用户名 的用户
useradd -g 组名 用户名(添加新用户到某个组)
##### passwd-->设置用户密码
passwd 用户名 (设置用户密码)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695778042056-63d59ed7-a8e1-4745-b8b6-e7fe9aa37567.png#averageHue=%23343934&clientId=u1b8d38f3-c523-4&from=paste&height=102&id=ub4d69429&originHeight=140&originWidth=658&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=99879&status=done&style=none&taskId=u079680f9-d201-4db9-8061-7316ca0ca3f&title=&width=478.54545454545456)
##### cat/etc/passwd-->查看创建的所有用户
##### su-->切换用户
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695778319280-852858e4-5f13-42f8-9049-bdbc7c704e30.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=123&id=u8b050e74&originHeight=169&originWidth=778&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=92152&status=done&style=none&taskId=udea30ff3-96a7-4dcb-ad55-9bff64dd729&title=&width=565.8181818181819)
超级管理员向普通用户切换不需要密码
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695778443913-23d44cde-9f71-4bea-915a-a792a48f9b4e.png#averageHue=%23262724&clientId=u1b8d38f3-c523-4&from=paste&height=178&id=u59a35d19&originHeight=245&originWidth=702&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=137298&status=done&style=none&taskId=ue56c2b6e-d140-4419-885a-b6319384ee2&title=&width=510.54545454545456)
su-  可以查看切换过去的用户的环境变量
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695778674682-88fa808a-2031-474d-94c6-ef96f8e67cd0.png#averageHue=%232a2b29&clientId=u1b8d38f3-c523-4&from=paste&height=228&id=uf3dc9aa4&originHeight=313&originWidth=873&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=316638&status=done&style=none&taskId=u023fb09c-f671-4bad-b4b4-1bf339d7927&title=&width=634.9090909090909)
##### userdel-->删除用户
userdel 用户名 -->只删除用户,保存用户的主目录
userdel -r 用户名  -->删除 用户和用户的主目录
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695778729367-1a84f37e-3b0b-4ee2-800c-1fa05f5eb4f3.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=209&id=u477dd81f&originHeight=287&originWidth=733&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=113883&status=done&style=none&taskId=u2ea4b8ca-a8fc-418f-aaa6-ae0a0d8272c&title=&width=533.0909090909091)
创建的用户都出现在了home目录下的各自的组目录下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695778852785-2a106b8b-cea8-41c9-9e04-29b2705c434f.png#averageHue=%233e4a39&clientId=u1b8d38f3-c523-4&from=paste&height=172&id=u8bef5d8b&originHeight=236&originWidth=823&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=226329&status=done&style=none&taskId=u3214916c-833c-4cf0-9264-49526c9d3b1&title=&width=598.5454545454545)
##### who-->查看登录用户信息
whoami-->显示**自身用户**名称
who am i --> 显示**登录用户**的用户名
不切用户的状态下(su -  或 su)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695779151063-3fdc41f7-ed2b-4865-96c3-9248b5f3ae07.png#averageHue=%232b2d28&clientId=u1b8d38f3-c523-4&from=paste&height=91&id=udafd7e6d&originHeight=125&originWidth=707&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=106962&status=done&style=none&taskId=udeb8cd7b-9783-4c45-aa30-75f8ee56c76&title=&width=514.1818181818181)
切换用户的状态下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695779244822-819f87d0-bd67-46a9-beb2-488539949655.png#averageHue=%232c2e29&clientId=u1b8d38f3-c523-4&from=paste&height=103&id=u20e0df8a&originHeight=141&originWidth=719&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=134069&status=done&style=none&taskId=u2f329ecc-4297-49e8-812c-9353fce96b4&title=&width=522.9090909090909)
##### sudo-->让普通用户拥有root的权限
普通用户无法进行新建文件等操作
使用sudo让其具有管理员权限
使用root账号修改配置 vim/etc/studoers(第91行左右)添加内容
普通用户通过sudo 命令 进行操作
##### usermod -g -->把用户移动到别的组
usermod -g 用户组 用户名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695780826743-8df90570-6f82-45cb-a8bc-1a55fbfe3a1b.png#averageHue=%23434b40&clientId=u1b8d38f3-c523-4&from=paste&height=174&id=u190a1fc5&originHeight=239&originWidth=752&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=248224&status=done&style=none&taskId=u12ead284-99d3-4d48-a3d8-c574b357b32&title=&width=546.9090909090909)
###### 修改过程
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695780270500-7660e452-444f-42e2-8919-3c8c00240db5.png#averageHue=%23fbfbf6&clientId=u1b8d38f3-c523-4&from=paste&height=189&id=u3c925233&originHeight=260&originWidth=653&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=131122&status=done&style=none&taskId=u380d6153-e1fd-4917-95ff-8e9cc88d5e5&title=&width=474.90909090909093)
要新加的一行是 **待获取权限用户名 ALL=(ALL) ALL**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695780453029-70be2075-020a-47fc-ad0e-1dcd389f1baa.png#averageHue=%23242422&clientId=u1b8d38f3-c523-4&from=paste&height=91&id=u64bf8583&originHeight=125&originWidth=598&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=62058&status=done&style=none&taskId=uf5f4aa47-f941-461b-9c70-21a7d84e81a&title=&width=434.90909090909093)
或者(不建议)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695780284409-f2b76850-7387-4b10-ba15-edd2b644b460.png#averageHue=%23fafaf5&clientId=u1b8d38f3-c523-4&from=paste&height=150&id=ubd3a84ae&originHeight=206&originWidth=743&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=137085&status=done&style=none&taskId=u6a5a3f9f-c055-4b56-b5ec-b8e848599f4&title=&width=540.3636363636364)
### 文件权限
#### 分类
权限分类
r:可读
w:可写
x:可执行
角色分类:
用户-->所属主  u(user)
组内-->所属组  g(group)
组外-->其他  o(other)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695781106429-2bb93993-9265-4687-96b3-cdb4eaaf8fe0.png#averageHue=%2330382d&clientId=u1b8d38f3-c523-4&from=paste&height=145&id=ua10cbf7b&originHeight=199&originWidth=299&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=109724&status=done&style=none&taskId=u9927fccf-9c2c-4c43-8f5b-de95eddfecc&title=&width=217.45454545454547)
#### 介绍:
d开头都是目录
-开头都是文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695781223770-22a41e99-3be0-45f5-9066-b99144c03bb1.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=141&id=Rpx3j&originHeight=194&originWidth=519&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=40952&status=done&style=none&taskId=u352248d0-795f-4b18-acfc-dd65d5b4726&title=&width=377.45454545454544)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695781247576-14314081-b28b-4890-85de-b8502ff631f4.png#averageHue=%23faf9f5&clientId=u1b8d38f3-c523-4&from=paste&height=87&id=idHmS&originHeight=119&originWidth=628&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=83088&status=done&style=none&taskId=u3eca8651-44b1-4376-bd4d-8c03037e5f0&title=&width=456.72727272727275)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695781378601-e8fa35af-464b-4d2d-8a05-3a7679123100.png#averageHue=%23fbfbf8&clientId=u1b8d38f3-c523-4&from=paste&height=428&id=g0LLE&originHeight=588&originWidth=941&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=168438&status=done&style=none&taskId=uab3e8eff-2f50-4bb2-9b8a-ae93519aac0&title=&width=684.3636363636364)
#### 命令:
##### chmod-->改变文件权限
想给hello的 属主 加一个 可执行 权限
chmod u+x ./hello
想给hello的 属组 和 其他 加 可修改 权限
chmod g+w,o+w ./hello----->[同时修改多个的情况下需要我们去使用 逗号 将其隔开]
同样的,也可以减少某个文件对于某个角色的权限
想给hello 的属组 减少一个 可修改 权限
chmod u-w ./hello
给所有的属都增加可改--->使用 a 来实现
chmod a+w ./hello
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695781587492-3e4da811-5997-4fb9-8bb1-dac3aefcf606.png#averageHue=%232b3428&clientId=u1b8d38f3-c523-4&from=paste&height=147&id=ubba50b4e&originHeight=202&originWidth=1004&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=233190&status=done&style=none&taskId=u63293db0-b777-4ea1-9db0-5a1a7b859c5&title=&width=730.1818181818181)
第二种写法
都写7是满的意思,三种权限都有
是使用和与差的方式来进行的权限修改
三位数字代表的是从前到后的user group other
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695783709889-ef6ed30d-b7b1-4cec-9080-99076e14d3cc.png#averageHue=%23363a37&clientId=u1b8d38f3-c523-4&from=paste&height=76&id=ub401415d&originHeight=105&originWidth=701&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=60358&status=done&style=none&taskId=ua00c42e1-fe49-44da-b6a5-0407991fce6&title=&width=509.8181818181818)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695784359846-2ef794cd-8a30-4eee-ae42-f97dde15d4c7.png#averageHue=%23fafaf5&clientId=u1b8d38f3-c523-4&from=paste&height=76&id=uadbc801d&originHeight=105&originWidth=489&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=41345&status=done&style=none&taskId=u98be13d3-0a9f-4f21-bbe6-d79acb07164&title=&width=355.6363636363636)
加减赋给
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695784473586-f7aa2ca5-9478-48ed-8b5c-9710b0e29e35.png#averageHue=%23fdfdfa&clientId=u1b8d38f3-c523-4&from=paste&height=127&id=uc5986c89&originHeight=174&originWidth=436&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=18747&status=done&style=none&taskId=u27b35c72-e14c-4e6e-b107-9d6f0b17276&title=&width=317.09090909090907)
##### chown-->改变所有主
chown [选项] [最终用户] [文件或目录] --->改变文件或者目录的所有者
改变文件直接在最后写文件
改变目录需要在选项位置增加 -R 选项来对目录进行递归修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695784708414-737a7457-0605-4a92-8452-58a196f83312.png#averageHue=%23252623&clientId=u1b8d38f3-c523-4&from=paste&height=182&id=u06b85892&originHeight=250&originWidth=929&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=220813&status=done&style=none&taskId=u377cda74-1a42-4bbe-aa24-f9be629cc8d&title=&width=675.6363636363636)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695784821260-21e2ff68-255f-40df-a932-e9f37569dd37.png#averageHue=%232d372a&clientId=u1b8d38f3-c523-4&from=paste&height=270&id=ud6646eb3&originHeight=371&originWidth=1000&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=546982&status=done&style=none&taskId=u7c7895ea-3bd7-4f6d-b8db-61b4cb2ab8a&title=&width=727.2727272727273)
修改所属主之后,其相对应的 user 也发生了变化,意味着修改后的属主也有着变化的执行权限(可读可改可执行)
给目录修改.加-R之后将目录内所有文件和次级目录都进行修改
##### chgrp-->改变所有组
chgrp  [最终用户组] [文件或目录]
改变文件或者目录的所属组
与chown相同的,它同样具有-R遍历修改的选项能实现遍历修改目录的功能
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785278063-e4bdecbe-4bdd-433d-900f-39465dd48e56.png#averageHue=%23232322&clientId=u1b8d38f3-c523-4&from=paste&height=86&id=u452c81fd&originHeight=118&originWidth=407&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=31930&status=done&style=none&taskId=u56bf901a-6bc2-4f9a-8389-3684e6bebeb&title=&width=296)
### 搜索查找类
#### find-->查找文件或者目录
find [搜索范围]  [选项]
根据名字查找
根据后缀进行查找
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785618823-a19b7559-8ac0-4d86-a3b1-09f868cd592f.png#averageHue=%23262624&clientId=u1b8d38f3-c523-4&from=paste&height=79&id=u9173d513&originHeight=109&originWidth=574&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=78148&status=done&style=none&taskId=ucdeeeb29-0366-49f1-9274-2c492b314a1&title=&width=417.45454545454544)
根据用户名查找
 根据用户名找到属于这个用户名之下的所有文件/目录![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785674853-117f5cbe-cbdb-4490-accd-ac831f08fb92.png#averageHue=%23303634&clientId=u1b8d38f3-c523-4&from=paste&height=71&id=u1af22b6d&originHeight=98&originWidth=584&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=48897&status=done&style=none&taskId=u37af1259-c5a1-41e4-9400-0e5fec39729&title=&width=424.72727272727275)
根据文件的大小查找
查找大于200m的文件就是
find /home -size +204800
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785761534-ca0227bf-832b-4c54-b0bb-7361a434a02b.png#averageHue=%23fbfaf6&clientId=u1b8d38f3-c523-4&from=paste&height=69&id=u1cada6ce&originHeight=95&originWidth=778&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=56577&status=done&style=none&taskId=u758a79cb-5e04-4c86-a37e-f292e074e05&title=&width=565.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785504489-5e52eedb-64de-4814-8612-041e942a9bc7.png#averageHue=%23fbfaf6&clientId=u1b8d38f3-c523-4&from=paste&height=132&id=u6fb45315&originHeight=181&originWidth=803&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=94271&status=done&style=none&taskId=u5118e434-2c11-489a-b554-1b7d12d99a1&title=&width=584)
#### grep-->过滤查找(二次筛选)
相当于是模糊查找
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785899628-50a504c3-75dd-4f00-aa0c-dac4c558c937.png#averageHue=%23fafaf6&clientId=u1b8d38f3-c523-4&from=paste&height=89&id=u0441089e&originHeight=123&originWidth=745&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=74121&status=done&style=none&taskId=ua86756aa-77aa-442d-a930-00230952613&title=&width=541.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695785911349-6ceae777-a357-4f97-bb6c-49ac83199a7b.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=68&id=u8c316d24&originHeight=93&originWidth=525&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=19530&status=done&style=none&taskId=u773b5d67-a54c-474a-8750-82475356bc8&title=&width=381.8181818181818)
前方也有个语句,前方语句的处理结果过多无法完成所需筛选的状况时,添加 grep 进行结果的过滤
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695786036091-f2c8faf2-6d70-43b1-8cf7-039cda941822.png#averageHue=%23282926&clientId=u1b8d38f3-c523-4&from=paste&height=134&id=u82e7419b&originHeight=184&originWidth=923&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=198679&status=done&style=none&taskId=ubc765f02-f20a-4c9d-bcb4-1c237da9736&title=&width=671.2727272727273)
将符合条件的文件过滤显示出来
常用于--->
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695786143469-f382217d-6ea7-4419-8de6-abe790ae61cd.png#averageHue=%232b3b2a&clientId=u1b8d38f3-c523-4&from=paste&height=72&id=u5f3bfb4f&originHeight=99&originWidth=651&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=66493&status=done&style=none&taskId=u70caf49e-2a4c-4d0d-b1ef-65b14cbff91&title=&width=473.45454545454544)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695786241517-78d9c591-a92f-4e83-b56c-93aa89e15827.png#averageHue=%23fcfcf9&clientId=u1b8d38f3-c523-4&from=paste&height=110&id=ue8c753ad&originHeight=151&originWidth=531&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=37551&status=done&style=none&taskId=ud0a272e7-b76b-4114-8477-d9b0510f27e&title=&width=386.1818181818182)
### 压缩和解压缩
#### 1.gzip/gunzip (不常用)
只能压缩文件,且不能保留源文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695786450629-55a0e059-761b-443b-9695-7f62510688e4.png#averageHue=%23fcfcf8&clientId=u1b8d38f3-c523-4&from=paste&height=235&id=u344d8cf3&originHeight=323&originWidth=644&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=115607&status=done&style=none&taskId=u346b8431-f50d-464b-b097-2770b2e7045&title=&width=468.3636363636364)
#### 2.zip/unzip(通用)
可以保留源文件
解压后的存放目录可选
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695786635834-cb87b203-adce-4af5-8346-4230dc09534f.png#averageHue=%23fcfcf8&clientId=u1b8d38f3-c523-4&from=paste&height=292&id=u20ab3c02&originHeight=401&originWidth=740&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=128341&status=done&style=none&taskId=u20316be2-4d41-48f0-a824-f26fb48ae4b&title=&width=538.1818181818181)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695786901470-23d923f5-9c2c-494b-8127-bbed5668823b.png#averageHue=%23222221&clientId=u1b8d38f3-c523-4&from=paste&height=140&id=uc517048d&originHeight=193&originWidth=939&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=126769&status=done&style=none&taskId=uebcc03a1-ad9b-4cb4-8a78-b363c09cd2e&title=&width=682.9090909090909)
#### 3.tar打包(常用)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695787017364-240abcb3-61a6-45de-b869-486f5d501c31.png#averageHue=%23fafaf6&clientId=u1b8d38f3-c523-4&from=paste&height=51&id=u55f7452a&originHeight=70&originWidth=844&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=49535&status=done&style=none&taskId=u9706812d-1e26-4342-9f5f-ebb256ccf81&title=&width=613.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695787036940-98735f80-4cc1-452e-8d54-3998aa17b8cf.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=210&id=u33567499&originHeight=289&originWidth=501&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=72116&status=done&style=none&taskId=ufcf25ce3-a75a-47ba-98ca-ad1fd4d7fed&title=&width=364.3636363636364)
##### tar的打包并压缩  与解包
打包压缩:   tar -zcvf  取的别名.tar.gz  要打包的文件
解压缩包:   tar -zxvf   要解的包名
### 进程线程
#### 查看进程
ps(process status 进程状态) 查看当前系统进程状态

ps -ef 可以查看所有执行进程以及其父子id关系
可以根据进程id关闭进程
ppid是pid的父id,将父id关闭后,其子id会全部关闭
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695792136774-c1c260cf-238e-4b7e-a7e6-587ccfb642b0.png#averageHue=%23282c24&clientId=u1b8d38f3-c523-4&from=paste&height=241&id=ua85a1ccb&originHeight=332&originWidth=936&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=410855&status=done&style=none&taskId=ue4483bab-8a2a-4a7e-843a-d45042a6a52&title=&width=680.7272727272727)
ps -aux 可以查看所有执行进程以及cpu 和men(内存)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695792323810-7cb181d0-361c-4372-8a4b-8149e268ba79.png#averageHue=%23262a23&clientId=u1b8d38f3-c523-4&from=paste&height=227&id=u020e627c&originHeight=312&originWidth=874&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=377560&status=done&style=none&taskId=u6e5ab81d-ee01-4ea3-8d32-8f8230eeaba&title=&width=635.6363636363636)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695792026257-473c43fc-fa66-4e4a-8557-8e31adebca88.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=276&id=u4bb39aba&originHeight=379&originWidth=655&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=123297&status=done&style=none&taskId=uf686dfab-4442-4ac7-a104-9dcb321891a&title=&width=476.3636363636364)
#### 结束进程
kill结束进程
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695792434551-5824cacf-fd43-4aa5-a0d2-fcfb49428ba2.png#averageHue=%23272925&clientId=u1b8d38f3-c523-4&from=paste&height=377&id=u6b76eb45&originHeight=519&originWidth=1058&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=732039&status=done&style=none&taskId=u7759eeb9-cdf5-4047-9f78-b4951b49efe&title=&width=769.4545454545455)
打开火狐浏览器之后出现的新的进程
如果想关闭

 kill -9 5475(进程id)
 kill -9 xxx  强制关闭
        killall 名字   相关名字的全部关掉
### 磁盘分区 
df -h   查看磁盘的使用情况,加了-h 后,以经过计算的形式来进行显示
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695794799970-404e312c-d780-4f2b-89af-c2826f5733d7.png#averageHue=%23282826&clientId=u1b8d38f3-c523-4&from=paste&height=229&id=uab276f1f&originHeight=315&originWidth=879&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=307314&status=done&style=none&taskId=u1104e92d-7ccd-4c03-a72c-9904870cdcf&title=&width=639.2727272727273)
 fdisk  查看分区
常用的是 dfisk -l  磁盘的扇区会显示出来
### 软件包管理
## 软件包管理
在linux安装软件
### rpm包
条件:  有rpm包
rpm(红帽安装工具)
格式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695795307859-47af8a4d-37a1-46e5-9ad7-036a23945a88.png#averageHue=%23fafaf5&clientId=u1b8d38f3-c523-4&from=paste&height=115&id=ud457af8d&originHeight=158&originWidth=611&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=106593&status=done&style=none&taskId=u2bdb1d62-7a78-427b-a0b2-f449325eb87&title=&width=444.3636363636364)
#### 操作
##### 查看
rpm -qa
rpm -ql
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695795277551-04641d9c-8e4e-47c4-99a6-9bc9f439be37.png#averageHue=%23f9f9f4&clientId=u1b8d38f3-c523-4&from=paste&height=58&id=udddc7c25&originHeight=80&originWidth=523&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=49244&status=done&style=none&taskId=uab0a632e-2e9b-4386-b085-43b823650eb&title=&width=380.3636363636364)
##### 安装
rpm -ivh  软件包的路径

![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695795606776-04277613-16aa-4e49-8925-827b2539fed6.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=171&id=uf707af88&originHeight=235&originWidth=665&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=66969&status=done&style=none&taskId=ua014e811-1f0c-4a4d-a667-999d96bfb91&title=&width=483.6363636363636)
##### 卸载
rpm -e 软件包  --->卸载软件包
rpm -e --nodeps  软件包 --->卸载软件时不检查以来
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695795731047-bec2a87d-3fe6-495c-b189-2cee9068859a.png#averageHue=%232a2a28&clientId=u1b8d38f3-c523-4&from=paste&height=117&id=uccf1ae99&originHeight=161&originWidth=1049&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=233526&status=done&style=none&taskId=u6379c9f5-c534-429a-afb1-75ad392f369&title=&width=762.9090909090909)
### yum仓库(常用)
联网安装软件(类比maven)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695795776335-ef74a9ff-05ea-476d-b5a4-9c4a55acb4e4.png#averageHue=%23f9f9f6&clientId=u1b8d38f3-c523-4&from=paste&height=298&id=ud3dd5ea0&originHeight=410&originWidth=919&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=148066&status=done&style=none&taskId=u1257d978-639a-400b-a5eb-d93d644e0eb&title=&width=668.3636363636364)

基本语法:
yum [选项] [参数]
选项:
-y 所有回答都为yes
参数:
要重点记住一个list
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695795862859-ae65e185-1aed-4991-9887-1519b0b9212a.png#averageHue=%23fbfbf7&clientId=u1b8d38f3-c523-4&from=paste&height=270&id=ud3e9fcb8&originHeight=371&originWidth=739&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=127868&status=done&style=none&taskId=u3939e499-8cbe-492f-b5e9-af119f88308&title=&width=537.4545454545455)
从yum仓库中下载火狐浏览器到linux系统之中
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695796005529-e3bc941b-41ec-4739-831a-7c97df72dd01.png#averageHue=%232a2a28&clientId=u1b8d38f3-c523-4&from=paste&height=127&id=u8c9c1d92&originHeight=175&originWidth=1102&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=228105&status=done&style=none&taskId=ub01d19a5-9849-40ab-9da2-3c7b7427606&title=&width=801.4545454545455)

![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695796604584-9bdab7c4-dcbb-4a7c-aa87-ba87586fb6aa.png#averageHue=%23faf9f6&clientId=u1b8d38f3-c523-4&from=paste&height=126&id=ue43d9767&originHeight=173&originWidth=380&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=38092&status=done&style=none&taskId=ub83215c0-dfa7-4366-a4cf-4a7d7c9dfdd&title=&width=276.3636363636364)
## 服务环境搭建
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695796867795-1c68e159-7f90-4f3c-b91d-1d19edd151dd.png#averageHue=%2322201e&clientId=u1b8d38f3-c523-4&from=paste&height=332&id=u22bbd512&originHeight=457&originWidth=1140&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=90847&status=done&style=none&taskId=ud2edbc1b-3145-4790-8d42-f9d088486bf&title=&width=829.0909090909091)
### 安装jdk
解压安装包
tar包-->  tar -zcvf  xxx 压缩  ; tar -zxvf  xxx 解压
解压tar包,使用解压命令 tar -zxvf
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695796890737-2be33354-93d5-4dbe-b17a-1b087890dba7.png#averageHue=%23222221&clientId=u1b8d38f3-c523-4&from=paste&height=105&id=ua86df21f&originHeight=145&originWidth=1030&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=111042&status=done&style=none&taskId=ue7f2786e-a2a9-412a-a07e-835193184cb&title=&width=749.0909090909091)
#### 配置环境变量
1.首先需要jdk的家目录
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695797089343-aba2833d-5b19-49be-8cd9-2d76dcfd14e8.png#averageHue=%2337403f&clientId=u1b8d38f3-c523-4&from=paste&height=68&id=u8c87c597&originHeight=94&originWidth=607&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=82001&status=done&style=none&taskId=ucb6c5bde-df85-4eae-85d0-9543ccecfc6&title=&width=441.45454545454544)

[将提前自带的jdk使用rpm -e --nodeps 进行删除]

2.在/etc/profile.d 目录下创建my_env.sh文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695797175944-dcb25766-5ab9-4a09-9503-dfa43dd96530.png#averageHue=%23fcfcf7&clientId=u1b8d38f3-c523-4&from=paste&height=76&id=ue15fea32&originHeight=105&originWidth=374&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=31082&status=done&style=none&taskId=u6905c049-b8ae-4af3-8eca-3c190ee3e78&title=&width=272)
3.在my_enc.sh文件中配置java_home环境变量
#JAVA_HOME
JAVA_HOME=/jdk的路径/jdk-17.0.7
PATH=$PATH:$JAVA_HOME/bin
export PATH JAVA_HOME

4.执行刷新并检查
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695798974286-3b1188dc-6a70-433c-ab82-fd1c1824ba52.png#averageHue=%23282522&clientId=u1b8d38f3-c523-4&from=paste&height=92&id=u150615f1&originHeight=126&originWidth=730&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=18283&status=done&style=none&taskId=u52d976b1-8acd-456b-9efb-63726478df8&title=&width=530.9090909090909)
### 安装tomcat
解压即可
也可配置环境变量
任意地区都可使用
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695799345825-f2dcd7e0-d2a4-40fd-af3d-c6fbfa1583c0.png#averageHue=%23292a27&clientId=u1b8d38f3-c523-4&from=paste&height=453&id=u25d48b5a&originHeight=623&originWidth=704&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=594407&status=done&style=none&taskId=u050222a5-9a8f-47db-b67f-5bc0fc4fe8f&title=&width=512)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695800156558-26251980-b8f8-4260-a9c1-3243f6451cf2.png#averageHue=%2362615f&clientId=u1b8d38f3-c523-4&from=paste&height=284&id=u3d299e61&originHeight=390&originWidth=973&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=68736&status=done&style=none&taskId=ubd3bc039-38dd-4c80-9a94-6aa8b9c931e&title=&width=707.6363636363636)
同样的配置环境变量,刷新,操作
### 安装mysql与启用
#### 安装
在mysql官网下载所需的rpm集合包tar
检查安装环境是否已经准备好
卸载系统环境自带的mysql
卸载残留mysql的前置版本
检查必要的依赖
如果三个依赖缺少就使用yum库进行下载
检查/tmp临时目录权限
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695801299129-463e60f1-9ffa-4a21-832d-a52607e15127.png#averageHue=%23a1a19e&clientId=u1b8d38f3-c523-4&from=paste&height=504&id=uc5f3baa4&originHeight=693&originWidth=944&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=471844&status=done&style=none&taskId=u2d179779-a93c-4d84-9633-4807f3da659&title=&width=686.5454545454545)
解压安装包后
按照顺序进行安装
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695801573816-a5e7056d-8942-49f1-8908-306aba26a8e3.png#averageHue=%232d2824&clientId=u1b8d38f3-c523-4&from=paste&height=249&id=u5981792e&originHeight=342&originWidth=740&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=58589&status=done&style=none&taskId=uc703a30f-e48c-4a83-9362-18d8043652d&title=&width=538.1818181818181)
安装顺序
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695801603298-049aeee8-1d8b-4616-9912-a5d0ff18c767.png#averageHue=%23fafaf4&clientId=u1b8d38f3-c523-4&from=paste&height=140&id=u99159e2a&originHeight=193&originWidth=715&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=186805&status=done&style=none&taskId=u28dc5a3e-db5b-474d-9b9f-1bb60129cfc&title=&width=520)
rpm -ivh mysql-community-common-8.0.30-1.el7.x86_64.rpm
rpm -ivh mysql-community-client-plugins-8.0.30-1.el7.x86_64.rpm
rpm -ivh mysql-community-libs-8.0.30-1.el7.x86_64.rpm
rpm -ivh mysql-community-icu-data-files-8.0.30-1.el7.x86_64.rpm
rpm -ivh mysql-community-client-8.0.30-1.el7.x86_64.rpm
rpm -ivh mysql-community-server-8.0.30-1.el7.x86_64.rpm

-ivh的含义
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695801621614-9caef956-b456-464f-a47d-6d86c57c90b9.png#averageHue=%23f8f6ee&clientId=u1b8d38f3-c523-4&from=paste&height=83&id=u0a00eb51&originHeight=114&originWidth=825&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=77196&status=done&style=none&taskId=uf0f9b464-b8e1-4248-ba59-cfa9bceda9c&title=&width=600)
#### 配置启动
查看是否安装成功
rpm -qa | grep mysql
查看版本
mysqladmin --version
启动后查看启动状态--->是否成功启动
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695804324778-478a27d6-ba31-4775-b466-e7b622d26412.png#averageHue=%23997f51&clientId=u1b8d38f3-c523-4&from=paste&height=55&id=ua1217240&originHeight=75&originWidth=491&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=3888&status=done&style=none&taskId=uf86b75fe-e385-42fc-b6a3-6f301f21343&title=&width=357.09090909090907)
##### 初始化数据目录生成密码
start mysqld为开启
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695803053386-d44d86a0-3b8b-4200-a857-119374971488.png#averageHue=%23fafaf4&clientId=u1b8d38f3-c523-4&from=paste&height=160&id=ud9384a43&originHeight=220&originWidth=314&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=78445&status=done&style=none&taskId=u24f6bd32-b0d7-494d-8492-fe919891042&title=&width=228.36363636363637)
mysql --initialize --user=mysql
查看目录结构
ls /var/lib/mysql/
初始化与查看状态
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695802980996-1c4fc311-0d98-491f-b32f-b5d132bc8b67.png#averageHue=%23282926&clientId=u1b8d38f3-c523-4&from=paste&height=146&id=u18098746&originHeight=201&originWidth=1212&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=256955&status=done&style=none&taskId=u82ebcab0-bdf8-43fe-bc10-3a2d0d8fef2&title=&width=881.4545454545455)
启动mysql服务
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695803014204-1005b233-e8dc-4178-adb1-1ff8730d9695.png#averageHue=%23363a35&clientId=u1b8d38f3-c523-4&from=paste&height=96&id=ua08bace6&originHeight=132&originWidth=722&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=49690&status=done&style=none&taskId=u1e3b5c02-0723-41d2-b7ac-1d963c64fb4&title=&width=525.0909090909091)

查找初始密码
> grep 'temporary password' /var/log/mysqld.log


![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695803193194-29e05228-0fb6-48ab-9cbc-455bbdc0213c.png#averageHue=%233d4644&clientId=u1b8d38f3-c523-4&from=paste&height=55&id=u1b909756&originHeight=75&originWidth=370&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=46611&status=done&style=none&taskId=u38f41cfb-067f-4281-992e-b466022b4cf&title=&width=269.09090909090907)冒号后的就是初始化之后的临时密码
##### 使用初始密码进行登录并修改
mysql -root -临时密码
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695803290417-84eb4bf9-59b1-4df2-8f2b-3ce440b626dc.png#averageHue=%23292927&clientId=u1b8d38f3-c523-4&from=paste&height=89&id=u89631153&originHeight=123&originWidth=768&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=115173&status=done&style=none&taskId=u28bd5aa9-740d-4a10-9e96-18f0fc440fa&title=&width=558.5454545454545)
进入后,去修改临时密码
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695803347874-3803bcd8-06c3-444f-9b58-65f45d02a531.png#averageHue=%23232322&clientId=u1b8d38f3-c523-4&from=paste&height=105&id=u1d97102e&originHeight=145&originWidth=1051&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=101461&status=done&style=none&taskId=ubec427da-2295-421d-ba1d-5a1804a39ff&title=&width=764.3636363636364)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695803484335-979e6f1d-b459-4ce3-ad86-cd26c9ada98a.png#averageHue=%23fbfaf6&clientId=u1b8d38f3-c523-4&from=paste&height=115&id=u3c97d706&originHeight=158&originWidth=830&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=97480&status=done&style=none&taskId=u0a456c96-8fa1-44c2-bb70-59e0ddcb651&title=&width=603.6363636363636)
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';
#### 连接可视化工具
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695809372440-6163257c-801c-4d26-9c69-4ff0c9d35036.png#averageHue=%23a4a4a1&clientId=u1b8d38f3-c523-4&from=paste&height=307&id=u9af443da&originHeight=422&originWidth=685&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=202191&status=done&style=none&taskId=uaaed491b-03d9-4028-b221-4ee85deb91c&title=&width=498.1818181818182)
只能通过本机来连接(localhost)--->修改为 '%' 允许任意ip进行连接
语句为:
UPDATE user SET Host = '%' WHERE User ='root';

FLUSH PRIVILEGES; -- Host修改完成后记得执行FLUSH PRIVILEGES使配置立即生效：
