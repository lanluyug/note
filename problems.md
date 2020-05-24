# 常见问题及工具用法收录

## 1.  IE起始页的默认页被修改如何解决?

解决网址: https://zhidao.baidu.com/question/105844494.html

解决办法: 

IE起始页的默认页被修改的解决办法：
 
 1.在电脑启动后，点击“开始”→“运行”菜单项，在“打开”栏中键入regedit，然后按“确定”键；
 
 2.展开注册表到HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Main
 下，在右半部分窗口中找到串值“Start Page”双击 ，将Start Page的[键值](http://www.baidu.com/s?wd=键值&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)改为“about:blank”即可；
 
 3.同理，展开注册表到
 HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\Main
 
 在右半部分窗口中找到串值“Start Page”，然后按②中所述方法处理。
 
 4.退出[注册表编辑器](http://www.baidu.com/s?wd=注册表编辑器&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)，重新启动计算机。
 特殊例子：当IE的起始页变成了某些网址后，就算你通过选项设置修改好了，重启以后又会变成那些网址了，十分的难缠。其实他们是在你机器里加了一个自运行程序，它会在系统启动时将你的IE起始页设成他们的网站。
 
 解决办法：运行[注册表编辑器](http://www.baidu.com/s?wd=注册表编辑器&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)regedit.exe，然后依次展开
 HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\Current Version\Run
 
 主键，然后将其下的registry.exe子键删除，然后删除自运行程序c:\Program Files\registry.exe，最后从IE选项中重新设置起始页就好了。



 

## 2. JDK环境配置

1）系统变量→新建 JAVA_HOME 变量 。

变量值填写jdk的安装目录（本人是 E:\Java\jdk1.7.0)

2）系统变量→寻找 Path 变量→编辑

在变量值最后输入 %JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;

（注意原来Path的变量值末尾有没有;号，如果没有，先输入；号再输入上面的代码）

3）系统变量→新建 CLASSPATH 变量

变量值填写  .;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar（注意最前面有一点）

系统变量配置完毕。



 

## 3.  Maven环境变量配置

参考：https://blog.csdn.net/huo920/article/details/82082403

1) 打开环境变量，在系统变量里新建MAVEN_HOME，并填写他的地址，地址就是你安装的位置。

2)点击确定之后，在系统变量里找到path，点击编辑，把;%MAVEN_HOME%\bin;这句放在路径的最后面，前后都有分号。

3) 测试，安装成功之后进行测试，打开cmd：输入mvn -version或者mvn -v命令，如果出现版本信息就成功了。以上就是maven的安装以及配置环境变量。

4）通常我们需要修改解压目录下conf/settings.xml文件

 a) 在<**localRepository**>标签内添加自己的本地位置路径：

<localRepository>D:\tools\repository</localRepository>

在<profiles>标签下添加一个<profile>标签，修改maven默认的JDK版本。

 ```xml
<profile>   

  <id>JDK-1.8</id>   

  <activation>    

    <activeByDefault>true</activeByDefault>    

    <jdk>1.8</jdk>    

  </activation>    

  <properties>    

    <maven.compiler.source>1.8</maven.compiler.source>    

    <maven.compiler.target>1.8</maven.compiler.target>    

    <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>    

  </properties>    

</profile>

 ```

添加<mirrors>标签下<mirror>，添加国内镜像源，这样下载jar包速度很快。默认的中央仓库有时候甚至连接不通。一般使用阿里云镜像库即可。这里我就都加上了，Maven会默认从这几个开始下载，没有的话就会去中央仓库了。

 ```xml
<!-- 阿里云仓库 -->

<mirror>

  <id>alimaven</id>

  <mirrorOf>central</mirrorOf>

  <name>aliyun maven</name>

  <url>http://maven.aliyun.com/nexus/content/repositories/central/</url>

</mirror>

 

<!-- 中央仓库1 -->

<mirror>

  <id>repo1</id>

  <mirrorOf>central</mirrorOf>

  <name>Human Readable Name for this Mirror.</name>

  <url>http://repo1.maven.org/maven2/</url>

</mirror>

 

<!-- 中央仓库2 -->

<mirror>

  <id>repo2</id>

  <mirrorOf>central</mirrorOf>

  <name>Human Readable Name for this Mirror.</name>

  <url>http://repo2.maven.org/maven2/</url>

</mirror>
 ```



## 4. 常用IDE下配置Maven

目前常用的开发工具如idea，eclipse都自身集成了一个版本的Maven。但是通常我们使用自己已经配置好的Maven。

IDEA下配置Maven

​                               

1：此处修改为自己解压的Maven目录

2：勾选Override，修改为自己目录下的settings.xml目录

3：修改为自己的本地仓库地址，一般会自动识别。

 

此处勾选，当修改pom文件时，Maven就能帮我们自动导包了。



 

## 5.  nodeJs配置（npm）

1） 检验是否安装成功：win+r，输入cmd回车，进入Windows命令窗口，输入npm -v，出现版本信息即安装成功。

2） 在node主目录下配置 全局模块 安装路径：

npm config set prefix C:\soft\nodeJs\global

在node主目录下配置 cache缓存 路径：

npm config set cache C:\soft\nodeJs\cache

修改npm包管理器的registry为淘宝镜像，npm config set registry https://registry.npm.taobao.org（官方地址为registry.npmjs.org）

3）①：在系统变量下新建"NODE_PATH"，“C:\soft\nodeJs\global \node_modules\”，这种方法用来指定NODE_PATH环境变量，并且用 ; 分割多个不同的目录（引申：NODE_PATH 是 NODE 中用来 寻找模块所提供的路径注册环境变量 ，NODE_PATH 实现 多个项目 模块复用 的最佳实践方案。node 的包加载机制，从项目的根位置递归搜寻  node_modules 目录，直到文件系统根目录的  node_modules ，如果还没有查找到指定模块的话，就会去 NODE_PATH中注册的路径中查找 。基于 nodejs 的包加载路径搜索算法，我们可以 采用全局安装的方式，将我们的包安装到全局，这样，多个项目可以共享全局中的依赖包。）

  检查 NODE_PATH 是否配置成功：win+r，输入cmd回车，进入Windows命令窗口，执行npm install express -g，安装express模块成功后，输入node，进入node的REPL环境，输入require('express')，如果出现express模块相关信息即配置成功

  ②：在用户变量"PATH"末尾追加，“D:\develop\nodejs\node_global\”（引申：操作系统 PATH 环境变量作用，当系统调用一个命令的时候，就会在PATH变量中注册的路径中寻找，如果注册的路径中有就调用，否则提示命令没找到，“xxx不是内部或外部命令，也不是可运行的程序或批处理文件”，原因是没有配环境变量PATH）

  检查 PATH 是否配置成功：win+r，输入cmd回车，进入Windows命令窗口，对于已经安装成功的模块，执行相应的命令，如：npm、cnpm、vue、webpack，出现相关输出信息即配置成功！

**
**

## 6.  Hbuilder用法

1)   执着于更快一步的理念，hx的左侧项目管理器是单击响应而不是双击。

2)   单击展开目录，单击预览文件，双击打开文件。

3)   预览文件时顶部标签卡是斜体的，此时继续预览其他文件会替换预览标签卡。双击文件后标签卡为正体，不会被替换。预览的文件一旦开始编辑，也会自动变为正式打开状态。

 

4)   项目管理器默认是不显示图标的，可以将鼠标移到项目管理器区域，右上角会悬浮菜单，在里面可以选择显示图标。HBuilderX支持业内多种图标插件，可以在工具-插件安装中找到更多图标插件。

5)   hx的文件保存是免丢失的，并且有热退出功能。所谓热退出，就是关闭hx时不要保存文件。再次打开时仍然是之前的状态。未保存的文件也会继续原样展现。

6)   hx默认带有每30秒保存一次临时文件的策略（可以在设置里调节时间间隔）

7)   不管是关闭hx，还是断电、崩溃，临时文件始终会自动保存。

8)   前端预编译型语言越来越多，每次保存都触发编译比较消耗资源，有了hx，可以专注写代码而不需要隔一会按一下ctrl+s，需要编译时再保存，或编辑多个文件后按ctrl+alt+s全部保存。

### 语法提示

 

### 语法帮助

光标放到某api处，按下F1，就可跳转到这个api的官方手册。目前支持vue、uni-app、5+等api （如下图示例）

 

### 多光标与批量处理

hx支持多光标，按 ctrl+鼠标左键 就可增加一个光标，ctrl+鼠标右键 可取消一个光标或选区。（如下图示例）

 

还可以选择相同词。ctrl+e (mac是cmd+d)可选中相同的词做批处理。（如下图示例）

 

### 列选择

hx的列选择，是alt+鼠标拖选。或者用快捷键ctrl+alt+↑或↓。（如下图示例）

 

### 文件快速打开

在顶部工具栏直接搜索工程下的文件名并打开，或者使用快捷键ctrl+p。（如下图示例）

 

### svn/git项目导入

以git为例：（git项目：需要安装git插件、以及TortoiseGit、并配置ssh秘钥）（如下图示例）

### 预编译器(less/sass)

在【菜单】-->【插件安装】里有各种语言的预编译器，比如less、ts等。安装预编译器后，hx下的所有项目均可用共用。

sass/less插件配置小技巧：

less、sass可以在插件配置里，配置为保存文件时自动编译。

安装less或sass插件后，进入菜单【工具】【插件配置】【compile-less】,点击package.json文件，将onDidSaveExecution修改为true。注意修改后需要重启HBuilderX才能生效

 



 

## 7.   关于 win 10 复制速度慢

> 卸载旧版的winrar软件就OK了! 装最新版的winrar解压软件。

 