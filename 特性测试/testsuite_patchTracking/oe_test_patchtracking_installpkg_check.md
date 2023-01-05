# oe_test_patchtracking_installpkg_check

## 描述

包安装后查看各个安装文件路径及权限

## 预置条件

新装补丁管理平台二进制包

## 测试步骤

1   rpm -ql patch-tracking
2   ls -l  xxx

## 预期结果 

1  配置文件路径及权限：/etc/patch-tracking/      644
2  可执行命令路径及权限:                   /usr/bin/              755
3  文档代码路径及权限：                   /usr/lib/python3.8/site-packages/       文件权限 644   目录权限755
4  service文件路径及权限：              /usr/lib/systemd/system/   644
5  数据库文件路径及权限：               /var/patch-tracking/    644
6  其他文件路径及权限如下/etc/ima               644
