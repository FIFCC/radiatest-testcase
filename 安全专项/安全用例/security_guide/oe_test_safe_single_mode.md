# oe_test_safe_single_mode

## 描述

安全单用户模式

## 预置条件

## 测试步骤

1.修改/etc/sysconfig/init  ，将SINGLE选项配置为SINGLE=/sbin/sulogin
2.重启，在启动引导界面按e ，在启动参数后面追加single ，进入单用户(连串进去)， 预期1
3.在提示输入密码后，输入root密码

## 预期结果

1.提示Give root psswword for maintenance

## 备注

难以实现