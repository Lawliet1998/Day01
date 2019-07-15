#### Java第一阶段
# 第1单元 Java开发起步
### 动手做
- 任务1：下载并安装JDK
- 任务2：配置环境变量
	- 1.Path：E:\Java\jdk\bin;
	- 2.CLASSPATH=.;(英文格式)
	- 问题：Path和CLASSPATH大小写区分吗？
		- 在Windows下不区分，在Linux、UNIX、Mac下严格区分，必须写成Path、CLASSPATH。
	- 问题：在Windows下如果系统变量和用户变量一样，哪个生效？
		- 用户变量生效，系统变量被覆盖。
- 任务3：验证环境变量配置是否成功？
	- 验证方式1：cmd窗口命令输入javac或java
		- 问题：javac和java从哪里来？
			- Path环境变量的值，JDK的bin目录。
	- 验证方式2：cmd窗口命令输入set命令，使用set path或set classpath查看显示的值是否正确。但set设置结果进队当前命令窗口有效，窗口关闭后就失效了。
	- 问题：如何查看当前jdk的版本？
		- 在cmd窗口输入：java -version。
- 任务4：编写HelloWorld，不带包。
	> java文件实际上是文本文件
	- java严格区分大小写，注意代码规范。
	- 编译：javac HelloWorld.java
		- 如果由于GBK编码问题无法正确编译，则使用以下方法：
			- javac -encoding utf-8 HellowWorld.java
	- 执行：java HelloWorld

```

	/*
    	CopyRight(C) YCKJ
	*/

	/**
    在屏幕上输出Hello World!
    @author zhanglintao
    @version 1.0 
	*/
	public class HelloWorld {
    	public static void main(String [] args) {
        	System.out.println("Hello World!");
    	}
	}
```

- 任务5：编写HelloWorld，带包。
> D:\>javac -d . HelloWorld.java                生成包

> D:\>java cn.edu.tit.corejava.HelloWorld       运行HelloWorld.class

> D:\>javadoc HelloWorld.java                   生成javadoc文档

> D:\>javadoc -author -version HelloWorld.java  显示作者、版本等
>
> 经过cmd javac 编译后，生成HelloWorld.class文件,它字节码文件 包含的是JVM的机器指令

```

	/*
    	CopyRight(C) YCKJ
	*/
	package cn.edu.tit.corejava;
	/**
    在屏幕上输出Hello World!
    @author zhanglintao
    @version 1.0 
	*/
	public class HelloWorld {
    	public static void main(String [] args) {
        	System.out.println("Hello World!");
    	}
	}
```

- 任务6：在一个Java文件中写多个class.

```

	/*
    	CopyRight(C) YCKJ
    	版权所有
	*/
	package cn.ychs.corejava.day01;
	/**
    	在一个Java文件中写多个class
    	@author zhanglintao
    	@version 1.0 2019-4-5
	*/
	public class Person {
    		public static void main(String [] args) {
        	System.out.println("Person");
    	}
	}
	class Student {
    	public static void main(String [] args) {
        	System.out.println("Student");
    	}
	}
	class Teacher {
    	public static void main(String [] args) {
        	System.out.println("Teacher");
    	}
	}

```

- 任务7：配置并使用Eclipse
	- 什么是IDE？
		
		- 集成开发环境。
	- 主要的IDE有哪些？
		
		- Eclipse(免费)、IDEA(商业软件)、NetBeans(免费，Sun产品，几乎不用)
	- Eclipse使用的先决条件：先安装JDK，JDK的位数和Eclipse位数是一致的。Eclipse的版本和它匹配的JDK版本要一致。
		> 下载地址：https://www.eclipse.org/downloads/packages/
		> Eclipse简介：https://zh.wikipedia.org/wiki/Eclipse
	- 术语：
		- workspace：工作空间，放写好的项目；
		- 工程或项目，在写程序前必须先建立工程
	- Eclipse的配置
		- 1. 配置编码：指定为UTF-8。
		- 2. 配置JDK：配置自己的JDK。
		- 3. 配置自动提示：在Windows中点击Preference，输入assi,输入a-z,A-Z;如果只能输入abc,则先Export，先导出，再以记事本打开，Ctrl+F查找abc,手动添加a-z,A-Z,保存，之后再导入，重启Eclipse即可。
	- Eclipse常用的快捷键
		- Ctrl+M				放大或还原代码编辑区
		- Ctrl+W				关闭单个窗口
		- Ctrl+Shift+M 			关闭所有窗口
		- Ctrl+E				切换代码窗口
		- Ctrl+D				删除光标所在行的代码
		- Shift+回车				在光标所在行下增加行
		- Ctrl+Shift+回车		在光标所在行上增加行
		- Alt+方向键的上键或下键 	该代码向上或向下
		- Ctrl+/				注释单行或取消注释
		- Ctrl+Shift+/			多行注释
		- Ctrl+Shift+\			取消多行注释
		- Ctrl+L				快速定位行
		- Ctrl+Q				快速返回上一次编辑的位置
		- Ctrl+Shift+F			自动整理代码格式
		- Alt+Shift+S			打开资源
		- Alt+shift+Z    		捕获异常try-catch
		- Ctrl+shift+O   		自动导包
- 如何安装Eclipse插件(Plugins)？
	- 复制插件的jar包，粘贴在eclipse的plugins目录下，然后重启eclipse即可。如果重启之后插件无用，需要删除eclipse中configuration/org.eclipse.update。如果还不管用，可能是插件版本与eclipse版本号不一致。
		- 安装打开文件路径的插件:OpenExplorer
		- 安装阿里巴巴代码规范检查规范的插件
		- 安装PMD插件（代码缺陷检查）


- 思考
	- 问题：如何编译？
		
		- javac -d . Person.java
	- 问题：如何执行？
		- 想执行谁，指定谁。
		- java cn.ychs.corejava.day01.Person
		- java cn.ychs.corejava.day01.Student
		- java cn.ychs.corejava.day01.Teacher
	> 被执行的类必须有main()方法才能执行
	
	- 问题：将Person.java另存为Student.java,为什么无法通过编译？
		
		- 如果一个类被public修饰，在保存时文件名和类名必须相同。
	- 问题：将Student修饰符改为public，为什么无法通过编译？
		- 一个java文件中，最多只能有一个类被public修饰。
	- 如果所有类都不是public修饰的，保存时文件名可以随意。
		> .class文件：字节码文件，里面的内容是内存地址和十六进制数。
	
- 验证
	- 在HelloWorld程序中，删除以下字段
	- 删除public		能否编译(能)		能否执行(否)
	- 删除static		能否编译(能)		能否执行(否)
	- 删除void		能否编译(否)		能否执行(否)
	- 删除[]			能否编译(能)		能否执行(否)
	- 删除String [] args		能否编译(能)		能否执行(否)
	- 将[]换成...		能否编译(能)		能否执行(能)
	- 调换public与static的位置		能否编译(能)		能否执行(能)

### 课后任务
- 任务1：查看Java发展历史
	- 1990年末，Sun公司启动由James Gosling领导的“Green计划”，旨在开发智能家电的嵌入式控制系统。
	- 1991年2月，Green项目小组成员发现C++存在很多弊端，决定在其基础上开发一种新的语言，并命名为“Oak”。
	- 1991年6月，JamesGosling开发了Oak的解释器。1992年，Green完成了Green操作系统、Oak语言、类库等开发。
	- 1992年11月，Green计划转化成“FirstPerson”，一个Sun公司的全资子公司。
	- 1993年，时代华纳发布电视机顶盒提议书，有线电视业界觉得FirstPerson的平台给予用户过多的控制权，因此FirstPerson的投标败给了SGI。同年，FirstPerson公司一笔与3DO公司的机顶盒交易也宣告失败，Green计划几乎夭折。
	- 1994年，FirstPerson公司倒闭，员工都合并到Sun公司。Gosling修改OaK并很快发布第一个Java语言的网页浏览器：WebRunner(后来改名为HotJava)，Oak更名为Java。
	- 1995年5月23日，Sun公司正式在互联网上免费发布Java语言，标志着JAVA语言的正式诞生。几个月后，超过10万人下载Java语言。
	- 1996年，JDK1.0发布，这是java发展历程中的重要里程碑，标志着java成为一种独立的开发工具。1997年2月，JDK1.1发布。
	- 1998年12月，第二代Java平台的企业版J2EE发布。1999年4月27日，HotSpot虚拟机发布。
	- 1999年6月，Java2被分成三个版本：J2SE（标准版）、J2EE(企业版)、J2ME(微型版),是Java发展过程中最重要的一个里程碑，标志着Java的应用开始普及。
	- 2000年5月,JDK1.3,JDK1.4和J2SE1.3相继发布。
	- 2001年9月24日，J2EE1.3发布。2002年2月，J2SE1.4发布,各种开源框架大量出现。
	- 2004年9月30日18:00PM，J2SE1.5发布，成为java语言发展史上的又一里程碑。为了表示该版本的重要性，J2SE1.5更名为Java SE 5.0。
	- 2005年6月，Java SE 6.0发布，三个版本分别改为：JavaSE， JavaEE，， JavaME。
	- 2006年11月13日，Java技术的发明者Sun公司宣布，将Java技术作为免费软件对外发布。2009年4月20日，Oracle以74亿美元收购Sun公司，取得了java的版权。
	- 2011年7月，JavaSE7发布。
	- 2014年3月，JavaSE8发布。
- 任务2：查看Java官方教程
- 任务3：编程任务：

- 口述
	- 1、解释JDK、JRE、JVM
		- JDK： Java 语言的软件开发工具包，主要用于移动设备、嵌入式设备上的java应用程序。JDK是整个java开发的核心，它包含了JAVA的运行环境（JVM+Java系统类库）和JAVA工具（JDK包含JRE和JVM）。
		- JRE：Java Runtime Environment缩写，指Java运行环境，是Sun的产品。运行JAVA程序所必须的环境的集合，包含JVM标准实现及Java核心类库。
		- JVM：Java Virtual Machine（Java虚拟机）的缩写，JVM是一种用于计算设备的规范，它是一个虚构出来的计算机，是通过在实际的计算机上仿真模拟各种计算机功能来实现的。
	- 2、Java程序的执行过程
		- 源程序经过编译生成的字节码(class文件)是在Java虚拟机平台上运行的，而不是直接在操作系统平台上运行的。JVM在任何平台上都提供给编译程序一个共同的接口，编译程序只需要面向JVM，生成JVM能够理解的字节码代码，然后又JVM的解释器负责执行即可。
	- 3、Java平台的划分
		- Java ME 微型版
		- Java SE 标准版
		- Java EE 企业版
	- 4、Java语言有哪些特点
		- Java是一种跨平台，适合于分布式计算环境的面向对象编程语言。 具体来说，它具有如下特性：简单性、面向对象、分布式、解释性、可靠、安全、平台无关、可移植、高性能、多线程、动态性等。
	- 5、C、C++、Java的区别
		- 1)C是面向过程的语言。C++和Java都是面向对象的。在C语言中没有类或者对象的概念。
		- 2)java运行在虚拟机上，与平台无关。可移植性好。
		- 3)C和C++是直接编译成可执行文件，运行效率比java高。
		- 4)java因为是运行在虚拟机上，不需要考虑内存管理和垃圾回收机制。
		- 5)代码重用：java中有一个根类object，所有的类都是其子类，通过这种方式将容器和算法分离，实现一种操作作用于多种对象，提高代码重用。C++中没有总根对象，但是c++提供了另一个更强大的功能“模板”，同样高效地实现了一种操作作用于多种对象，提供了高效的代码重用方法。
		- 6)C语言在一些比较低层，和硬件打交道的地方用得比较多。另外很多开源软件由于unix/linux开发习惯也大多采用C来开发。Java是现在最流行的开发语言，C++比起java稍稍不那么流行一些，但是功能很强大。如能深入掌握，可以写出兼顾效率和美观的优秀代码。