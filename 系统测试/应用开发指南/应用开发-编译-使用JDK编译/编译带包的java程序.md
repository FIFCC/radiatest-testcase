# 编译带包的java程序

## 描述

编译带包的java程序

## 预置条件

安装JDK

## 测试步骤

1.创建目录/home/code/Test/my/example 、/home/code/Hello/world/developers 、/home/code/Hi/openos/openeuler

2.cd 到/home/code/Test/my/example 目录，创建 Test.java

```vi Test.java
```

文件内容如下：

```package my.example;  
import world.developers.Hello;  
import openos.openeuler.Hi;  
public class Test {  
  public static void main(String[] args) {     
  Hello me = new Hello();     
  me.hello();     
  Hi you = new Hi();     
  you.hi();  
  }  
} 
```

3.cd 到/home/code/Hello/world/developers 目录，创建 Hello.java

```vi Hello.java
```

文件内容如下:

```package world.developers;  
	public class Hello {    
		public void hello(){  
			System.out.println("Hello, openEuler.");  
  }  
} 
```

4.cd 到/home/code/Hi/openos/openeuler 目录，创建 Hi.java

```vi Hi.java
```

文件内容如下：

```package openos.openeuler;  public class Hi {    public void hi(){  
   System.out.println("Hi, the global developers.");  
  }  
} 
```

5.cd 到/home/code，使用 javac 编译源文件

```cd /home/code
javac -classpath Hello:Hi Test/my/example/Test.java
```

6.cd 到/home/code，使用 java 运行 Test 程序

```cd /home/code  
java -classpath Test:Hello:Hi my/example/Test
```

## 预期结果

1.目录创建成功

2.文件创建成功

3.文件创建成功

4.文件创建成功

5.执行完命令后，会在“/home/code/Test/my/example”、
“/home/code/Hello/world/developers”、“/home/code/Hi/openos/openeuler”目录下分别生成 Test.class、Hello.class、Hi.class 文件

6.执行结果如下所示：

```Hello, openEuler.  
Hi, the global developers
```

## 备注