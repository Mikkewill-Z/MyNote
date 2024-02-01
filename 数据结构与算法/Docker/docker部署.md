1. maven的settings.xml配置harbor服务账号信息
2. 在pom引入docker插件^[原理是在docker主机上构建docker对应的镜像,将构建的镜像推送到harbor远程仓库中]
3. docker服务端开启远程访问
4. 编写dockerfile文件
5. 执行maven打包命令
6. 拉取镜像进行部署
![[Pasted image 20240126203441.png]]![[Pasted image 20240126203518.png]]