# 介绍
## 概述
Maven 是一款为 Java **项目管理构建、依赖管理**的工具（软件），使用 Maven 可以自动化构建、测试、打包和发布项目，大大提高了开发效率和质量。

项目需要第三方库（依赖），如Druid连接池、MySQL数据库驱动和Jackson等。那么我们可以将需要的依赖项的信息编写到Maven工程的配置文件，Maven软件就会自动下载并复制这些依赖项到项目中，也会自动下载依赖需要的依赖！确保依赖版本正确无冲突，依赖链路完整！

完成项目开发后，想要将项目打成.war文件，并部署到服务器中运行，使用Maven软件，我们可以通过一行构建命令（mvn package）快速项目构建和打包！节省大量时间！
## 主要作用
### 依赖管理
Maven 可以管理项目的依赖，包括自动下载所需依赖库、自动下载依赖需要的依赖并且保证版本没有冲突、依赖版本管理等。
### 构建管理
项目构建是指将源代码、配置文件、资源文件等转化为能够运行或部署的应用程序或库的过程
# 安装与配置

安装的设备中必须有java-home^[要配置好java的jdk,因为maven本身就是个java的项目管理工具]
解压安装之后,配置maven的环境变量

配置完成后更改maven的配置文件[[项目结构与优化#3.jar包的依赖|Maven文件配置]]
	1.依赖本地缓存位置(本地仓库位置)
	2.Maven下载镜像
	3.Maven选用编译项目的jdk版本

# 使用

在idea中配置maven并进行使用
创建maven格式的java项目之后
## 方式一
使用插件将java项目转换为web项目^[JBLjavatoweb插件实现]
使项目中出现一个webapp为名的文件夹/包
## 方式二
直接在maven格式的java项目中new出webapp文件夹/包
其内的文件也要同名同格式
随后修改pom.xml的打包格式
![[Pasted image 20231124101711.png|300]]
最后在maven选项卡中点击刷新按钮
![[Pasted image 20231124101813.png|200]]
最终得到maven支持的web项目.[[项目结构与优化#4.Maven目录结构|结构]]

## 打包与部署
使用lifecycle内的package命令将我们的项目进行打包
若不匹配就在pom.xml中添加配置进行适配
```
<build>  
  <!-- jdk17 和 war包版本插件不匹配 -->  
  <plugins>  
    <plugin>  
      <groupId>org.apache.maven.plugins</groupId>  
      <artifactId>maven-war-plugin</artifactId>  
      <version>3.2.2</version>  
    </plugin>  
  </plugins>  
</build>
```

完成打包之后出现.war的文件
部署时将其拖拽到对应启动器的目录下
TOMCAT对应webapps
![[Pasted image 20231124105034.png|400]]
最后bin下start.up命令即可
![[Pasted image 20231124105129.png|400]]

## jar包依赖导入
### 坐标 GAVP
![[Pasted image 20231124111214.png|500]]
由此对应相应版本的特定的jar包
### 打jar包并安装到本地仓库
将想要打包的项目使用maven生命周期的install命令
实现一系列的包括编译打包最后到下载至本地仓库的过程
若想使用打成的jar包,可以使用添加依赖dependencies去使用
#### 依赖仓库中的jar包
添加依赖
#### GAVP坐标
group:  com.公司.业务线.子业务线
atrifact: 产品线名-模块名
version: 主版本号.次版本号.修订号
package:   jar(默认),代表普通java工程
				war  代表java的web工程
				pom  代表不会打包,用来做继承的父工程-->springBoot
pom:
在pom.xml中使用GAVP进行指定jar包指定某个特定的依赖 ^ecd55f
#### 关于导入依赖时的scope属性

![[Pasted image 20231124145702.png|500]]

 生效范围
            - compile ：main目录 test目录  运行打包 [默认]
            - provided：main目录 test目录  Servlet
            - runtime： 打包运行           MySQL
            - test:    test目录           junit

## 统一依赖版本

在properties标签中自定义标签名
规定版本值
然后用${}来引入我们定义的版本

## 指定打包名称

 使用final name来决定最终打包之后的命名
![[Pasted image 20231124150919.png|500]]

## Maven依赖传递和依赖冲突

A项目-->B项目-->C项目-->jar包
当某个项目引入某个项目时,其他详谬的jar包是否可以被用来使用
答:scope的值为compile级别的jar包才可以被传递

### 依赖冲突
当直接或者间接引用的相同的jar包,就会导致依赖冲突问题
#### 自动选择原则
短路优先原则(就近原则)^[第一原则,路径更短的优先选择]
依赖路径长度相同的情况下,先声明者优先
#### 手动排除
不推荐
但可以使用dependency中的exclusion来进行排除

## Maven继承性和聚合关系
Maven 继承是指在 Maven 的项目中，让一个项目从另一个项目中继承配置信息的机制。
![[Pasted image 20231124162333.png|500]]
继承作用:
在父工程中统一管理项目中的依赖信息。
它的背景是：
- 对一个比较大型的项目进行了模块拆分。
- 一个 Project 下面，创建了很多个 Module。    
- 每一个 Module 都需要配置自己的依赖信息。

### 继承语法
做为父工程,它的打包方式必须是pom.[[Maven#^ecd55f|package of pom]]
使用parent标签指定当前工程的父工程,parent内写父工程的GAVP
如果子工程坐标中的groupId和version与父工程一致，那么可以省略

子工程引用父工程中的依赖信息时，可以把版本号去掉。  
 把版本号去掉就表示子工程中这个依赖的版本由父工程决定。 
 具体来说是由父工程的dependencyManagement来决定。
### 聚合功能
触发父工程的构建命令,所有的子工程也都会运行

## 加载jar包失败
加载失败时，会在仓库中生成一个*.lastupdated文件，这个文件会导致jar包无法下载，需要将该文件删除后，才可以下载jar包

# 生命周期

![[Pasted image 20231124143034.png|500]]
底层其实也是通过使用插件来进行项目的生命周期的构建
## 方式:命令方式
首先进入项目文件所在的目录中,在mvn上使用cmd进入命令行模式
进入命令行模式后使用相关命令来进行项目的构建

|命令|描述|
|---|---|
|mvn compile|编译项目，生成target文件|
|mvn package|打包项目，生成war文件|
|mvn clean|清理编译或打包后的项目结构|
|mvn install|打包后上传到maven本地仓库(本地部署)|
|mvn deploy|只打包，上传到maven私服仓库(私服部署)|
|mvn site|生成站点 (报告)|
|mvn test|执行测试源码 (测试)|

## 方式二:idea方式
在idea内的maven工具窗口之中进行使用
![[Pasted image 20231124143745.png|400]]
注:触发周期后的命令，会自动触发周期前的命令