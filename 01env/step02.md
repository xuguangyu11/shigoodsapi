# 环境搭建

-------

本节详细介绍开发环境的搭建

主要内容：

1. [jdk的安装](#ref1)
2. [eclipse的安装](#ref2)
3. [maven资源库配置](#ref3)
4. [svn插件安装](#ref4)
5. [安装配置tomcat](#ref5)

-----------

<h2 id="ref1">1. jdk的安装</h2>

如果已经安装了jdk的直接跳过，如果没有安装，可以把下载下来的jdk解压安装，按照提示一步步操作

安装完jdk后还需要配置环境变量，说的简单点的，配置环境变量就是配置 lib下载的包和bin下面的包。

1. 设置一个JAVA_HOME 指向自己的jdk安装目录(示例是装在D:\Java\jdk1.7.0_79)
2. 设置jdk的安装目录到bin 这一层为path (path需要分号隔开)
3. 设置jdk的安装目录的lib为classpath(classpath需要 .; 开头)

如图：
1. 设置JAVA_HOME 
![step1](/imgs/20160216152222.png)
![step2](/imgs/20160216152424.jpg)

2. 设置PATH 也就是在path中添加bin目录，也就是 D:\Java\jdk1.7.0_79\bin ，因为设置了JAVA_HOME ,这个路径就等于 %JAVA_HOME%\bin
所以进入path，加上即可（注意分号隔开）
![step2](/imgs/20160216152222_1.png) <br />

3. 设置classpath ,新建一个变量classpath, .;开头，加入lib所在的目录，如下图：<br />
![step3](/imgs/20160217163825.png)

-------
<h2 id="ref2">2. eclipse的安装</h2>
把准备工作中下载的eclispe 直接解压到自己喜欢的目录就可以，如果自行下载eclispe的话，尽量使用4.2以上版本，自带了maven插件，比较好用


-------
<h2 id="ref3">3. maven资源库配置</h2>
eclispe自带的maven，默认的仓库地址是 C:\Users\Administrator\.m2  这里是maven包，项目中使用的jar包
把资源中下载的repository.zip 直接解压到上面的文件夹即可

解压后如图：<br/>
![解压后的图](/imgs/20160216153529.png)<br/>

-------
<h2 id="ref4">4. svn插件安装</h2>
直接解压 准备工作中下载的 site-1.10.6.zip 文件到 eclispe解压的后的dropins 目录即可


-------
<h2 id="ref5">5. 配置tomcat</h2>
tomcat提供的是免安装的版本，直接解压到喜欢的目录即可使用，进入eclipse 配置一下即可

1.找到如图的server视图(如果没有话，自行百度调出来)，在空白的地方右键--> new --> server<br/>
![xxx](/imgs/20160216154100.png)<br/>

2.选择你安装的tomcat的版本<br/>
![xxx](/imgs/20160216154316.jpg)<br/>

3.点击browser 选择tomcat的解压的目录 finish 就行了<br/>
![xxx](/imgs/20160216154546.jpg)<br/>


至此，所有的配置都OK了，接下去开始自己的编码工作了





