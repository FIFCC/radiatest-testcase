# oe_test_ssoos_67

## 描述

操作系统应为用户提供一个机制，来控制命令的目录/路径的查找顺序

## 预置条件

## 测试步骤

1.命令查找根据环境变量PATH所列目录链表顺序查找。
用户secuser1在home目录下自定义一个与uname同名程序uname.c

```#inculde <stdio.h>
int main(void)
{
  printf("This is my uname!\n")
  return 0;
}
$gcc -o uname uname.c
$mkdir ~/bin
$mv uname ~/bin
$echo $PATH
$uname
$export PATH=/home/secuser1/bin:$PATH
$echo $PATH
$uname
```

2.其他修改环境变量的操作见指导性文档

## 预期结果

步骤1默认PATH为：

第一次uname输出Linux
修改后PATH为：

第二次uname输出为：

```This is my uname！```

命令查找时按照环境变量PATH包含的路径链表中顺序查找

## 备注