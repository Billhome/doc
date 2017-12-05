##maven安装与配置

>目录:  
>1、安装及配置
>2、高级配置

###1、安装及环境变量配置
  
1.1 安装  
[maven下载](http://maven.apache.org/download.cgi "maven")  

maven是非安装版的，下载之后直接解压缩，放在自己平时安装软件的目录下即可  

1.2 环境变量  
在高级环境变量中进行如下操作：
新增 MAVEN_HOME:maven的安装目录
添加 path: ;%MAVEN_HOME%/bin

1.3检测 

打开dos窗口，输入
`mvn -v`  
即可看到maven的相关配置

到这里，已经完成了maven的基本配置。下面针对开发做一些高级配置

####2、高级配置  

2.1 仓库配置  

maven安装之后默认的本地仓库地址在`C:\Users\Administrator\.m2\repository`,放在c盘下会有诸多不便，我们可以指定特定的仓库地址。

来到maven安装目录，打开conf/setting.xml,通过
`<localRepository>D:\java\mavenrepo</localRepository>`可以将maven本地仓库地址配置到`D:\java\mavenrepo`目录下。  


2.2 maven源配置  
国外maven源速度慢，目前国内好用的是阿里的maven源。
同样的，在setting.xml中。通过
```
<mirrors>
    <mirror>
      <id>alimaven</id>
      <name>aliyun maven</name>
      <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
      <mirrorOf>central</mirrorOf>        
    </mirror>
</mirrors>
```
<font color=red size=4>mirrors是一个列表，每个item对应的mirror是什么意思？有主要的也有次要的？</font>  

2.3 jdk配置  
在不配置maven jdk的情况下，每次在eclipse中创建maven 项目的默认使用的是低版本的jdk,就算每次在properti中修改完之后，再update project一下，还是会重置为默认值。
可以在setting.xml中通过一下配置修改  

```<profile>  
    <id>jdk-1.7</id>  
    <activation>  
        <activeByDefault>true</activeByDefault>  
        <jdk>1.7</jdk>  
    </activation>  
    <properties>  
        <maven.compiler.source>1.7</maven.compiler.source>  
        <maven.compiler.target>1.7</maven.compiler.target>  
        <maven.compiler.compilerVersion>1.7</maven.compiler.compilerVersion>  
    </properties>  
</profile>```

