# test_user_management_FUN_003

## 描述

修改用户shell设置

## 预置条件

已创建用户user

## 测试步骤

将用户 user_example 的 shell 改为 csh，命令如下：

```usermod -s /bin/csh user```

## 预期结果

查看用户执行echo $SHELL是否为/bin/csh

１．需安装ush

２．切换至用户user后执行echo $SHELL

## 备注