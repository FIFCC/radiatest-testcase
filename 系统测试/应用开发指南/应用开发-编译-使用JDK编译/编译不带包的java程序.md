# 编译不带包的java程序

## 描述

编译不带包的java程序

## 预置条件

安装JDK

## 测试步骤

1.创建代码目录

```mkdir /home/code
cd /home/code
```

2.编写 Hello World 程序，保存为 HelloWorld.java

```vi HelloWorld.java```

文件内容如下：

```public class HelloWorld {
     public static void main(String[] args) {           
         System.out.println("Hello World");       
      }   
} 
```

3.在/home/code目录下执行命令

```javac HelloWorld.java
```

4.执行命令查看编译结果

```java HelloWorld```

## 预期结果

1./home/code目录创建成功

2.HelloWorld.java文件创建成功

3.编译通过，生成HelloWorld.class 文件

4.输出Hello World

## 备注