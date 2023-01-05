# test_compile_c_FUN_001

## 描述

使用 GCC 编译 C 程序

## 预置条件

## 测试步骤

1.创建代码目录

```mkdir /home/code
cd /home/code
```

2.编写 Hello World 程序，保存为 helloworld.c

```vim helloworld.c
```
代码如下:

```#include <stdio.h>      
int main()      
{             
printf("Hello World!\n");                
return 0;      
} 
```

3.在代码层目录下进行编译

```gcc helloworld.c -o helloworld
```

4.查看编译结果

```./helloworld
```

## 预期结果

1.进入到/home/code目录下

2.helloworld.c文件创建成功

3.命令执行成功

4.编译完成后，会生成 helloworld 文件，返回编译结果

```Hello World!
```

## 备注