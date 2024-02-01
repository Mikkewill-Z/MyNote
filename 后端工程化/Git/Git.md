## 分布式版本控制系统
### 分布式
具有 远程仓库,本地仓库
远程仓库宕机不影响开发者开发,因为有本地仓库(远程仓库恢复后,从本地仓库进行同步)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696673329849-9e0006f1-96c7-479a-a1c7-f3314f00ff2e.png#averageHue=%23f3f4ee&clientId=u2f2a89f2-61fe-4&from=paste&height=89&id=u0ee2b63f&originHeight=122&originWidth=630&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=128137&status=done&style=none&taskId=ua283d95f-8fab-41ab-aae5-69830f28f0a&title=&width=458.1818181818182)
### 版本控制系统
记录文件的内容变化,以便将来查阅特定版本修订情况的系统
版本控制可以记录文件修改历史记录,从而让用户能查看历史版本,方便版本切换
个人开发过渡到团队协作,就需要版本控制
### 版本控制工具
#### 集中式版本控制工具
即只有一个服务器,单一集中管理的服务器,风险较大

CVS,SVN,VSS....
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696673117238-47bb9ad4-15b3-4d76-abd0-508592da736e.png#averageHue=%23f5f6f1&clientId=u2f2a89f2-61fe-4&from=paste&height=337&id=u76a602e0&originHeight=464&originWidth=699&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=282237&status=done&style=none&taskId=uc5c9650c-edc8-4491-9f5b-af1427660db&title=&width=508.3636363636364)
#### 分布式版本控制工具
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696673527258-a87a4683-7322-430b-ad0c-9cdb69c6eaac.png#averageHue=%23f4f4f0&clientId=u2f2a89f2-61fe-4&from=paste&height=505&id=u5761194c&originHeight=694&originWidth=718&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=346026&status=done&style=none&taskId=u04abf9fb-71c7-401f-a6fb-3bfd3e99578&title=&width=522.1818181818181)

#### 工作机制
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696673508658-1b3be914-04ce-435d-9a4a-76174a1346fb.png#averageHue=%23eef2ed&clientId=u2f2a89f2-61fe-4&from=paste&height=275&id=uf72b0687&originHeight=378&originWidth=411&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=127307&status=done&style=none&taskId=ua795a300-d7c4-4c6a-b9ce-2542c570286&title=&width=298.90909090909093)
文件内容(工作区)-->暂存区-->本地库-->远程库
从工作区到暂存区,用到 git add 文件名 命令
从暂存区到本地库,用到 git commit -m "说明" 文件名
从本地库到远程库,用到 git push 远程库地址 分支名称
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696673790332-922d2387-4712-4e6b-bf0c-29c8caee2f61.png#averageHue=%23f6f6f0&clientId=u2f2a89f2-61fe-4&from=paste&height=119&id=u7e7ef4bd&originHeight=164&originWidth=442&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=77256&status=done&style=none&taskId=u248dbbed-d624-4611-835d-b2a159e654c&title=&width=321.45454545454544)
## Git的使用
### 常用命令与使用
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696674287318-299bd6fd-e0ec-47ea-8534-375fd24d077f.png#averageHue=%23f4f4ef&clientId=u2f2a89f2-61fe-4&from=paste&height=268&id=ufed70e69&originHeight=368&originWidth=952&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=199452&status=done&style=none&taskId=udcffa7d1-e11c-4126-9b7a-4541db08eff&title=&width=692.3636363636364)
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696674484332-f8f7fc38-bc9e-43a4-a4e1-c0f871a0a954.png#averageHue=%23f3f4ef&clientId=u2f2a89f2-61fe-4&from=paste&height=106&id=u3db318eb&originHeight=146&originWidth=523&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=75993&status=done&style=none&taskId=ufac2f8ec-0fe4-495d-9604-c741c588ab6&title=&width=380.3636363636364)
### 本地库使用
首先创建一个工作区(目录)
打开命令窗口
进行全局设置(设置name与email)
##### 初始化(创建本地库)
git init
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675302316-37c05374-80fa-4e91-83a0-6e1c80780d0f.png#averageHue=%23181714&clientId=u2f2a89f2-61fe-4&from=paste&height=71&id=u5877686c&originHeight=98&originWidth=582&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=30329&status=done&style=none&taskId=u70a02ddf-19b1-494e-8152-a008a396f3a&title=&width=423.27272727272725)
##### 开发(创建文件,编写内容)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675374188-22da2ac5-1256-4128-9672-f5b3dd29c677.png#averageHue=%23030201&clientId=u2f2a89f2-61fe-4&from=paste&height=89&id=uea558f32&originHeight=123&originWidth=461&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=19888&status=done&style=none&taskId=u05b34f7d-80dc-40e5-ba76-281de7c293e&title=&width=335.27272727272725)
##### 查看状态
git status
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675447538-4ba58631-abb1-43a8-821d-48102f70c6bf.png#averageHue=%23090705&clientId=u2f2a89f2-61fe-4&from=paste&height=168&id=u416124fc&originHeight=231&originWidth=329&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=47958&status=done&style=none&taskId=uedc28147-84e4-4879-9574-175bc49bb53&title=&width=239.27272727272728)
##### 添加到暂存区
git add 文件名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675464965-c4c129ed-1149-42c6-9e23-c464380af0a5.png#averageHue=%230a0906&clientId=u2f2a89f2-61fe-4&from=paste&height=89&id=u358773e4&originHeight=123&originWidth=432&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=38070&status=done&style=none&taskId=u2f11ce8a-1c08-4a19-a093-a38e095c693&title=&width=314.1818181818182)
添加到暂存区后再次查看状态
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675491468-85b579bf-7369-41a2-8caa-53f6af553f7f.png#averageHue=%23050403&clientId=u2f2a89f2-61fe-4&from=paste&height=154&id=uc83ebc36&originHeight=212&originWidth=532&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=53782&status=done&style=none&taskId=u537cf248-c898-4de1-a514-9c7a44323cd&title=&width=386.90909090909093)
##### 添加到本地库
git commit -m "说明" 文件名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675650813-0a157069-be37-4298-9ad1-1d96032d1f9f.png#averageHue=%230b0907&clientId=u2f2a89f2-61fe-4&from=paste&height=135&id=u56c82ad1&originHeight=186&originWidth=718&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=103501&status=done&style=none&taskId=u8cdae486-86b6-4046-a38e-c3cfa4b7d48&title=&width=522.1818181818181)
添加后再次查看状态为,无可提交
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675685864-1bfae651-d191-4d45-9f0a-53dc4798a02a.png#averageHue=%23090704&clientId=u2f2a89f2-61fe-4&from=paste&height=132&id=ud6fa0ac5&originHeight=182&originWidth=524&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=62847&status=done&style=none&taskId=ue2daebf4-8dfd-4edc-9e12-3eadf06d59f&title=&width=381.09090909090907)
##### 修改文件内容
修改完文件的内容后,再次对文件进行add和commit即可
修改后重新add和commit![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675834472-3ed9f956-5dc3-4740-80bd-0eeb13ef5557.png#averageHue=%23080604&clientId=u2f2a89f2-61fe-4&from=paste&height=333&id=u4ac7ec92&originHeight=458&originWidth=762&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=212275&status=done&style=none&taskId=u714b6ba3-9569-4d6d-812f-7b4c57c2e3f&title=&width=554.1818181818181)
##### 如何切换版本
git reflog--->查看版本信息
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696675738463-74d56d0f-ea0d-44ab-884f-152a438ac6a8.png#averageHue=%230a0803&clientId=u2f2a89f2-61fe-4&from=paste&height=60&id=u127a4f83&originHeight=82&originWidth=879&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=46211&status=done&style=none&taskId=u46a50b4c-2542-48fd-90a2-f3d18a6378c&title=&width=639.2727272727273)
git reset --hard 版本号  ---->版本穿梭
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696676122042-39ca471e-b46a-4f74-a175-9d14b9f24104.png#averageHue=%23090804&clientId=u2f2a89f2-61fe-4&from=paste&height=90&id=ud3751643&originHeight=124&originWidth=606&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=53923&status=done&style=none&taskId=u23387b68-43ed-424d-8814-d786ef2c00e&title=&width=440.72727272727275)
git log --->查看操作信息
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696676274249-6c029580-19aa-4ca4-92ff-24d5dbfb9ac7.png#averageHue=%23090703&clientId=u2f2a89f2-61fe-4&from=paste&height=204&id=u929d2fcd&originHeight=280&originWidth=748&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=116767&status=done&style=none&taskId=u909a5736-da25-4a08-8d98-469a6a1c6c5&title=&width=544)
### 远程库使用
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696673895888-70e0f078-4d5d-4a02-9b54-89285da1b0e9.png#averageHue=%23f8f8f3&clientId=u2f2a89f2-61fe-4&from=paste&height=191&id=u6869d9b1&originHeight=262&originWidth=659&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=88030&status=done&style=none&taskId=u315c2be6-a6ca-4526-bf91-abe0ab3f462&title=&width=479.27272727272725)
远程仓库操作
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696678848207-e44c9342-e0cb-4010-a39a-274a65255834.png#averageHue=%23f2f2ed&clientId=u2f2a89f2-61fe-4&from=paste&height=169&id=u5a180d12&originHeight=232&originWidth=953&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=184277&status=done&style=none&taskId=u7a11f738-0287-4e09-871a-c84c0c1e8ca&title=&width=693.0909090909091)
#### 1.注册登录码云
#### 2.添加远程仓库
远程仓库操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696679568894-1b823942-a80f-4606-a1c8-de01111e5e31.png#averageHue=%23f3f3ee&clientId=u2f2a89f2-61fe-4&from=paste&height=183&id=u8a1f7759&originHeight=252&originWidth=397&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=78000&status=done&style=none&taskId=u827d3237-5b7e-4132-bcef-1e5c0a4f7fd&title=&width=288.72727272727275)
给网址起别名
git remote add ink [https://gitee.com/zyhdq/git-demo01.git](https://gitee.com/zyhdq/git-demo01.git)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696678996674-5e7410ef-c87f-46df-927e-dfbd696ce36c.png#averageHue=%23090704&clientId=u2f2a89f2-61fe-4&from=paste&height=189&id=ua7622f81&originHeight=260&originWidth=809&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=142487&status=done&style=none&taskId=ud65e35ca-dba9-4351-b9b1-1548c9305c5&title=&width=588.3636363636364)
#### 3.从远程库下载(拉取),上传与更新
##### 上传
![image.png|470](https://cdn.nlark.com/yuque/0/2023/png/838436/1696679140821-58a20bb2-eb26-4d8a-9ba1-a6d1559e50a1.png#averageHue=%230e0c09&clientId=u2f2a89f2-61fe-4&from=paste&height=221&id=uda96f314&originHeight=304&originWidth=649&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=171355&status=done&style=none&taskId=uaccfa659-2b57-463b-8d07-204d31329fd&title=&width=472)
更新
在本地写代码
写完添加到暂存区(add
从暂存区提交到本地库(commit
从本地库上传到远程库(push
##### 克隆
在新的目录(毫无文件)中执行克隆操作
克隆操作会自动取别名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696679639425-7260ca4a-cb5f-4e16-b098-8a11528281b4.png#averageHue=%230e0d0a&clientId=u2f2a89f2-61fe-4&from=paste&height=170&id=u460fefae&originHeight=234&originWidth=668&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=124845&status=done&style=none&taskId=uf1cb7bc6-0906-4ea7-9861-85568e55cd1&title=&width=485.8181818181818)
克隆之后对文件编辑与修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696679732584-8b7b56e0-1d72-456c-a958-a83af878cbe0.png#averageHue=%230b0905&clientId=u2f2a89f2-61fe-4&from=paste&height=215&id=u27a22edb&originHeight=295&originWidth=605&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=124987&status=done&style=none&taskId=u24b5f29c-a001-4e00-b103-51b8e81b537&title=&width=440)
##### 拉取
拉取与克隆都是从远程库为本地整过来
拉取是吧本地没有而远程库有的拉过来(增量部分)
克隆是本地啥也没有,从远程库全拿过来(全部部分)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696680012047-eb1eefda-14f8-4fbf-8f9c-1a82264c4708.png#averageHue=%232c2b28&clientId=u2f2a89f2-61fe-4&from=paste&height=312&id=u0018bdea&originHeight=429&originWidth=700&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=183175&status=done&style=none&taskId=u79ea022d-4934-4b8d-a2a1-4369f656bef&title=&width=509.09090909090907)
进行拉取
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696680038157-e25e2d2f-8b70-434f-aa8f-620d9a61199e.png#averageHue=%230d0b08&clientId=u2f2a89f2-61fe-4&from=paste&height=74&id=uae1a6115&originHeight=102&originWidth=589&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=52776&status=done&style=none&taskId=uda45ca63-5884-4e1f-a144-6a7ccf05155&title=&width=428.3636363636364)
当不同开发者对同一文件进行了修改后就会发生冲突
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696680573713-bd482f41-10cd-47c8-bc33-1738d21edfe9.png#averageHue=%23080604&clientId=u2f2a89f2-61fe-4&from=paste&height=316&id=uce0460e3&originHeight=434&originWidth=1327&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=330827&status=done&style=none&taskId=u371aef33-f000-4a5a-b172-92e839fcc5a&title=&width=965.0909090909091)
### 分支操作
将各组开发的功能模块归属到各个分支上,某个分支实现且无误后将其归纳到主分支上
一个分支可以理解为是一个副本
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696682316077-da087020-3236-472a-8b14-90bf4a57c0a8.png#averageHue=%23f1f1ec&clientId=u2f2a89f2-61fe-4&from=paste&height=209&id=u3827c8b6&originHeight=287&originWidth=786&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=179934&status=done&style=none&taskId=u574a538c-d45c-43b0-8866-badcd4505d8&title=&width=571.6363636363636)
#### 好处
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696682359396-11eed099-1af6-4e4a-9933-56db6b52c960.png#averageHue=%23f6f6f1&clientId=u2f2a89f2-61fe-4&from=paste&height=85&id=u218f842b&originHeight=117&originWidth=988&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=109766&status=done&style=none&taskId=u9a6690b5-8ab6-4285-96f2-6f4eb855f8b&title=&width=718.5454545454545)
#### 操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696682380256-75c7bae9-30c0-425c-a6e3-6b016c8329be.png#averageHue=%23f3f3ee&clientId=u2f2a89f2-61fe-4&from=paste&height=148&id=ua96d8968&originHeight=204&originWidth=735&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=89370&status=done&style=none&taskId=uc6c227f2-3845-48f9-b3c9-d5730fed478&title=&width=534.5454545454545)
##### 创建分支
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696682586652-1f317e7d-fe46-46fe-a98b-ba3f479f7e49.png#averageHue=%23070603&clientId=u2f2a89f2-61fe-4&from=paste&height=240&id=u79fdf4e3&originHeight=330&originWidth=688&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=135702&status=done&style=none&taskId=ua278b100-4563-44f5-887a-3355de8118a&title=&width=500.3636363636364)
##### 切换分支
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696682665721-093cf72c-b100-4fca-9269-c87ec107adc5.png#averageHue=%23070603&clientId=u2f2a89f2-61fe-4&from=paste&height=137&id=ua1a5c44d&originHeight=189&originWidth=693&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=75826&status=done&style=none&taskId=u5cc4cb8e-9ac0-4dc5-9812-02c1e3041ef&title=&width=504)
在子分支编写/修改代码对主分支没有任何影响
##### 合并
需要将分支合并到主分支master,那么就必须要在master分支上执行相应的git merge 分支名 命令
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696683225808-3aa67271-68e8-4957-98df-94a3853dfcc2.png#averageHue=%23080604&clientId=u2f2a89f2-61fe-4&from=paste&height=135&id=uaed8f905&originHeight=186&originWidth=662&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=73345&status=done&style=none&taskId=udc498755-3ebb-4ca9-8fc7-dde7c3b3b4b&title=&width=481.45454545454544)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696683240411-f84e8220-f852-445a-aef4-9ab764bf6689.png#averageHue=%23070504&clientId=u2f2a89f2-61fe-4&from=paste&height=119&id=u7179c761&originHeight=163&originWidth=660&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=54040&status=done&style=none&taskId=u69f23e00-89fb-4a39-922b-d614ab2b7bc&title=&width=480)
即可实现,主分支没动,通过其余分支的编写与合并实现主分支的功能实现
##### 合并冲突
出现主分支和分支同时修改代码的状况
由开发者决定留存
两个分支对同一个文件进行修改内容
切换到主分支(git checkout 主分支名
合并分支(git merge 分支名
进入文件
由开发者决定代码的留存
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696683664128-aa7c2c78-494c-4e6a-897f-5282ef93f542.png#averageHue=%23040202&clientId=u2f2a89f2-61fe-4&from=paste&height=177&id=uc502dbf5&originHeight=244&originWidth=634&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=59344&status=done&style=none&taskId=ucaac9612-4b18-4204-80d8-488c3fc3fd4&title=&width=461.09090909090907)
修改冲突文件并再次提交
注意,最后进行git commit命令时不能带文件名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696683837513-1a0093e9-8d09-42f8-bf9f-6b0b2157d957.png#averageHue=%236a5931&clientId=u2f2a89f2-61fe-4&from=paste&height=130&id=u7f233376&originHeight=179&originWidth=691&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=94259&status=done&style=none&taskId=ufa959fa2-3c9b-4d2b-af72-99f8e1979b1&title=&width=502.54545454545456)


## IDEA中使用Git
### IDEA使用本地库
忽略一些不必要的文件(只上传java文件)
#### 1.创建忽略规则文件
创建名为  xxx.ignore 的文件,粘贴忽略规则
```java
# Compiled class file
*.class

# Log file
*.log

# BlueJ files
*.ctxt

# Mobile Tools for Java (J2ME)
.mtj.tmp/

# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

# virtual machine crash logs, see http://www.java.com/en/download/help/error_hotspot.xml
hs_err_pid*

.classpath
.project
.settings
target
.idea
*.iml
```
建议放置于用户家目录下
与git.config放置在同一个目录下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696685231340-63027588-405c-4d82-9d64-023cab3047b6.png#averageHue=%23f6f6f2&clientId=u2f2a89f2-61fe-4&from=paste&height=52&id=uce4560b2&originHeight=72&originWidth=606&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=40768&status=done&style=none&taskId=u5e72bd0f-e547-4651-9575-1a14356c1dd&title=&width=440.72727272727275)
#### 2.在config文件中添加内容
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696685264805-c8977622-22f4-493b-847a-b1e209f8adb2.png#averageHue=%23f5f5f0&clientId=u2f2a89f2-61fe-4&from=paste&height=153&id=u38172f96&originHeight=211&originWidth=591&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=92303&status=done&style=none&taskId=u4385b932-a569-40b9-8611-b86b1792d8a&title=&width=429.8181818181818)
core内复制自己的忽略规则文件的地址
使用/ 不用\
#### 3.定位Git程序
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728140308-9d03fcf4-e84c-4224-af91-8a5f44edbd8d.png#averageHue=%23ecece8&clientId=u2f2a89f2-61fe-4&from=paste&height=338&id=u4e624907&originHeight=465&originWidth=822&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=251980&status=done&style=none&taskId=ua302af13-8371-45d8-a1ef-462980aa53e&title=&width=597.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728159019-67431ce8-39b1-4cd0-ac9c-a63011d5994b.png#averageHue=%23efefeb&clientId=u2f2a89f2-61fe-4&from=paste&height=329&id=u66c799f8&originHeight=452&originWidth=590&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=156806&status=done&style=none&taskId=uf2e96181-3ddd-4ad0-804e-5d8290715a3&title=&width=429.09090909090907)
#### 3.创建Git本地库
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728231688-04d4b9dc-2a98-4ee3-b408-3b225565b395.png#averageHue=%23e2e2dd&clientId=u2f2a89f2-61fe-4&from=paste&height=273&id=uf0afb565&originHeight=376&originWidth=761&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=254412&status=done&style=none&taskId=uc835a9f7-3c04-4e04-b1d3-906284d98e7&title=&width=553.4545454545455)
选中想要通过Git管理版本的文件
点击执行后默认执行了init初始化
#### 4.上传到暂存区
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728470339-def44107-619b-4d4c-904b-e3c655386fb9.png#averageHue=%23e9e9e4&clientId=u2f2a89f2-61fe-4&from=paste&height=372&id=u602d30b6&originHeight=512&originWidth=623&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=307042&status=done&style=none&taskId=u06aa4d6c-a4b2-4bad-934b-3a1161e9b7e&title=&width=453.09090909090907)
#### 5.提交到本地库
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728545289-82b4e837-25b1-4ecc-a67a-5d1bf7917482.png#averageHue=%23e8e8e3&clientId=u2f2a89f2-61fe-4&from=paste&height=124&id=u3cb04e3a&originHeight=170&originWidth=546&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=90124&status=done&style=none&taskId=u2f9edf3d-5a70-4b87-8f57-be2dfc1930b&title=&width=397.09090909090907)
-m后的信息写在下方
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728567971-b200d13c-c65d-425b-8681-ad96ccd5fb3d.png#averageHue=%23eeefea&clientId=u2f2a89f2-61fe-4&from=paste&height=343&id=u426cce4e&originHeight=471&originWidth=491&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=239148&status=done&style=none&taskId=u21e7e252-996b-4274-a94d-29467098803&title=&width=357.09090909090907)
#### 6.查看版本信息
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728603716-0b4f8139-cb4e-4c05-a9da-0d3b2f835846.png#averageHue=%23eaede2&clientId=u2f2a89f2-61fe-4&from=paste&height=74&id=u539d05cd&originHeight=102&originWidth=329&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=48303&status=done&style=none&taskId=u7ad85b54-de51-4b02-bb5f-104c75c7a02&title=&width=239.27272727272728)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728650814-901cbb38-556d-412a-8cb3-dc86c5e12e2b.png#averageHue=%23f2f2ee&clientId=u2f2a89f2-61fe-4&from=paste&height=111&id=u5cabe792&originHeight=153&originWidth=1280&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=109477&status=done&style=none&taskId=u9ee4d6d1-d779-4fa9-b57b-55ba69c57d5&title=&width=930.9090909090909)
#### 7.版本穿梭
对着想要穿梭的版本进行右键选择 checkout R~
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728678754-4fa68450-d064-4d2b-9bf1-28f39afa71fa.png#averageHue=%23f1f1ec&clientId=u2f2a89f2-61fe-4&from=paste&height=250&id=u9db9f3df&originHeight=344&originWidth=635&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=161908&status=done&style=none&taskId=u8428887c-4bcf-4ea9-ad56-187aeac135c&title=&width=461.8181818181818)
#### 8.切换分支
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728836668-083e1de4-02ae-48d7-932c-41d31205eadf.png#averageHue=%23f7f7f3&clientId=u2f2a89f2-61fe-4&from=paste&height=257&id=u17ee3b32&originHeight=354&originWidth=417&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=47721&status=done&style=none&taskId=uf55b43b3-5760-48bc-944f-7a912530a78&title=&width=303.27272727272725)
选中项目文件右键
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728880862-6f10ca23-5ebc-4a7d-ac2e-9246fec94020.png#averageHue=%23eeeee9&clientId=u2f2a89f2-61fe-4&from=paste&height=217&id=u33c0a37e&originHeight=299&originWidth=707&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=191980&status=done&style=none&taskId=u93ec2a62-dbc4-4cd3-b98f-7f9bb27c254&title=&width=514.1818181818181)
建好分支之后,可以对着想要切换的分支使用checkout进行切换
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696728920423-0a21d00a-94b1-4fd9-8aa7-68dcbe302fc3.png#averageHue=%23f3f3ef&clientId=u2f2a89f2-61fe-4&from=paste&height=153&id=u0f30f0bf&originHeight=211&originWidth=437&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=44243&status=done&style=none&taskId=u8f084b17-b8e9-4c1f-9a98-85d08424b39&title=&width=317.8181818181818)
#### 9.分支合并
首先需要先切换到主分支上
然后对着想要合并到主分支的分支右键,选择将其合并到主分支
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696729289881-a0037896-a48b-443e-b27c-a2bf3d784635.png#averageHue=%23f2f2ed&clientId=u2f2a89f2-61fe-4&from=paste&height=195&id=uac868df3&originHeight=268&originWidth=425&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=95613&status=done&style=none&taskId=u8c99fbf4-16d4-4bb9-b6a9-a348792ab48&title=&width=309.09090909090907)
##### 若出现分支冲突时
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696729451852-d55c208f-f5e7-4e72-9ecc-f9bc3ea048e2.png#averageHue=%23f0f0eb&clientId=u2f2a89f2-61fe-4&from=paste&height=185&id=uf7f607d6&originHeight=255&originWidth=449&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=118183&status=done&style=none&taskId=ua7cf7b77-b114-457b-bfbb-34e1ad5438c&title=&width=326.54545454545456)
会出现
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696729465602-998977e0-677d-4287-ae7c-e221aecbd0dd.png#averageHue=%23f4f4f0&clientId=u2f2a89f2-61fe-4&from=paste&height=131&id=uddfef6e7&originHeight=180&originWidth=612&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=74749&status=done&style=none&taskId=u5e143d53-e1c4-462d-a881-3dbfcb45698&title=&width=445.09090909090907)
箭头表示拿取合并到最终
叉号表示删除
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696729506303-2759f468-153d-4bee-a9b9-0c7ac444c837.png#averageHue=%23f4f4ef&clientId=u2f2a89f2-61fe-4&from=paste&height=329&id=u969d1624&originHeight=453&originWidth=921&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=399202&status=done&style=none&taskId=uff7a00ba-c0be-440f-8e98-351588a2531&title=&width=669.8181818181819)
抉择后点击apply完成
### IDEA使用远程库
#### 1.IDEA安装码云插件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696730395075-8e8a3d08-44d4-494f-88d9-2f684edb90de.png#averageHue=%23f1f2ec&clientId=u2f2a89f2-61fe-4&from=paste&height=396&id=ufd80dea7&originHeight=544&originWidth=798&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=342433&status=done&style=none&taskId=u5743817b-1f47-4b77-8f10-af7234d8849&title=&width=580.3636363636364)
#### 2.注册,获取拉取资格
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696731414582-76a57359-0dc9-49fb-96a9-94aaaf13a6e6.png#averageHue=%23f6f6f2&clientId=u2f2a89f2-61fe-4&from=paste&height=452&id=u4f8ac197&originHeight=621&originWidth=800&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=199412&status=done&style=none&taskId=u27ec1c83-a0c0-4962-b289-b567ef85562&title=&width=581.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696730465448-83739d11-5a75-4e29-aef9-681960c66f32.png#averageHue=%23f3f3ee&clientId=u2f2a89f2-61fe-4&from=paste&height=153&id=ubdb5a174&originHeight=210&originWidth=348&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=39941&status=done&style=none&taskId=u00e70287-cd59-426e-b929-1311ee95a46&title=&width=253.0909090909091)
输入邮箱和密码
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696730495481-cf9b27e7-332d-4124-b243-d44a670f02af.png#averageHue=%23f7f7f3&clientId=u2f2a89f2-61fe-4&from=paste&height=87&id=u5e15b052&originHeight=120&originWidth=399&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=17177&status=done&style=none&taskId=u74f0c01e-7bb3-439a-8049-c426db93b3d&title=&width=290.1818181818182)
#### 3.新建仓库接收idea中push的项目
新建仓库,最好见名知意
右键进行push
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696730651437-6e2b9861-db9b-4f54-8d25-7a63bc2f8645.png#averageHue=%23edeee8&clientId=u2f2a89f2-61fe-4&from=paste&height=336&id=u1a28c1ba&originHeight=462&originWidth=710&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=306483&status=done&style=none&taskId=ufe2c579f-de6a-4122-b7ef-5b3bfdbacc8&title=&width=516.3636363636364)
给想要push的目的仓库起别名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696730713650-b3100909-3ea1-45e7-a0a8-e64aa4fc4ceb.png#averageHue=%23f3f3ef&clientId=u2f2a89f2-61fe-4&from=paste&height=254&id=ud1e8d4fe&originHeight=349&originWidth=620&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=81056&status=done&style=none&taskId=u6a08c89f-d0a1-46eb-8bb1-d685cc4dd5d&title=&width=450.90909090909093)
随后经过验证之后就可以进行push
#### 4.将gitee中的文件进行克隆
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696731012036-cc18f1a2-b2ec-49d4-8356-a5115691652a.png#averageHue=%23efefea&clientId=u2f2a89f2-61fe-4&from=paste&height=383&id=u7bc11636&originHeight=527&originWidth=568&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=304160&status=done&style=none&taskId=u262d71cc-09bb-449f-b332-5c21983159e&title=&width=413.09090909090907)
填写仓库网址
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696731029898-e55ae470-7118-4b3b-90de-52874962ffcf.png#averageHue=%23efeeea&clientId=u2f2a89f2-61fe-4&from=paste&height=123&id=ubc68384a&originHeight=169&originWidth=588&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=50806&status=done&style=none&taskId=u508c584e-b570-4167-9583-c740b8c744f&title=&width=427.6363636363636)
克隆完成
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696731064194-1edae8db-db77-4a76-9d23-12c7c98a49c6.png#averageHue=%23eeeee9&clientId=u2f2a89f2-61fe-4&from=paste&height=382&id=u19470725&originHeight=525&originWidth=448&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=183707&status=done&style=none&taskId=u8a15b12d-3148-45de-8c22-cef7ef4ccc0&title=&width=325.8181818181818)
在克隆项目中进行修改后add commit push
#### 5.拉取(pull)
在需要拉取的项目中进行拉取
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696731124787-174cb629-70db-4ec1-b07d-75b53e27baa3.png#averageHue=%23eeeee9&clientId=u2f2a89f2-61fe-4&from=paste&height=372&id=u90a2e0a4&originHeight=511&originWidth=755&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=333074&status=done&style=none&taskId=uf695b40f-5d36-418e-bf3c-7beac81151d&title=&width=549.0909090909091)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696731464255-fbc09cbc-9a3f-46a9-a053-0b70dfbf2056.png#averageHue=%23e6e6e2&clientId=u2f2a89f2-61fe-4&from=paste&height=112&id=uffe4c316&originHeight=154&originWidth=556&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=70228&status=done&style=none&taskId=uca56eae7-42c7-488f-88a6-0795883b2f8&title=&width=404.3636363636364)
