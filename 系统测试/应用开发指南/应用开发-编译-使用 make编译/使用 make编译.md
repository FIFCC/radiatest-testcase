# 使用 make编译

## 描述

使用 make编译

## 预置条件

## 测试步骤

1.创建代码目录

```mkdir /home/code
cd /home/code
```

2.创建 1 个头文件 hello.h 和 2 个函数 hello.c、main.c

```vim hello.h
```

文件内容如下：

```#pragma once  
#include <stdio.h>  
void hello(); 
vim hello.c
```

文件内容如下:

```#include "hello.h"  
void hello()  
{          
int i=1;          
while(i<5)  
{                  
printf("The %dth say hello.\n", i);                  i++;  
   }  
} 
```

```vim main.c
```

文件内容如下:

```#include "hello.h"  
#include <stdio.h>  
int main()  
{          
hello();          
return 0;  
}  
```

3.创建 Makefile 文件

```vim Makefile
```

文件内容如下：

```main:main.o hello.o
        gcc -o main main.o hello.omain.o:main.c
        gcc -c main.c  hello.o:hello.c
gcc -c hello.c  clean:
        rm -f hello.o main.o main
```

4.执行make命令

```make```

5.执行./main 目标

```./main```

## 预期结果

1.进入到code目录下

2.hello.h /hello.c/ main.c文件创建成功

3.Makefile文件创建成功

4.make命令执行成功，输出gcc -o main main.o hello.o

5../mai命令执行成功，输出

```The 1th say hello.
The 2th say hello.
The 3th say hello.
The 4th say hello.
```

## 备注