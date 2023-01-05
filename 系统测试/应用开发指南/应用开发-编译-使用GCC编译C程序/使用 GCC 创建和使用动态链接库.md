# 使用 GCC 创建和使用动态链接库

## 描述

使用 GCC 创建和使用动态链接库

## 预置条件

## 测试步骤

1.创建代码目录

```mkdir /home/code
cd /home/code
```

2.在code目录下创建 src，lib， include 子目录，分别用于存放源文件，动态库文件和头文件

```mkdir src / mkdir lib / mkidr include
```

3.cd 到/home/code/src 目录，创建 2个文件，add.c、sub.c，分别实现加、减

```vi add.c
```

文件内容如下：

```#include "math.h"  
int add(int a, int b)  
{         
 return a+b;  
} 
```

```vi sub.c
```

文件内容如下：

```#include "math.h"  
int sub(int a, int b)  
{          
return a-b;  
} 
```

4.将 add.c、sub.c 源文件创建为动态库 libmath.so，并将该动态库存放在/home/code/lib 目录

```gcc -fPIC -shared add.c sub.c -o /home/code/lib/libmath.so
```

5.cd 到/home/code/include 目录，创建 1 个头文件 math.h，声明函数的头文件

```cd /home/code/include
vi math.h
```

文件内容如下:

```#ifndef __MATH_H_  
#define __MATH_H_  
int add(int a, int b);  
int sub(int a, int b);  
#endif
```

6.cd 到/home/code/src 目录，创建一个调用 add()和 sub()的 main.c 函数

```cd /home/code/src
vi main.c
```

文件内容如下:

```#include <stdio.h>  
#include "math.h"  int main()  
{          
int a, b;          
printf("Please input a and b:\n");          
scanf("%d %d", &a, &b);          
printf("The add: %d\n", add(a,b));          
printf("The sub: %d\n", sub(a,b));          
return 0;  
}
```

7.将 main.c 和 libmath.so 一起编译成 math.out

```gcc main.c -I /home/code/include -L /home/code/lib -lmath -o math.out
```

8.将动态链接库所在的路径加入到环境变量中

```export LD_LIBRARY_PATH=/home/code/lib:$LD_LIBRARY_PATH
```

9.执行 math.out

```./math.out
```

## 预期结果

1.进入到/home/code目录下

2.src lib include 子目录创建成功

3.add.c,sub.c文件创建成功

4.命令执行成功

5.文件创建成功

6.文件创建成功

7.命令执行成功

8.命令执行成功

9.执行结果如下所示：

```Please input a and b:
```

## 备注