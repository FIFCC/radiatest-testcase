# test_install_package_FUN_003

## 描述

下载安装 GTK 库

## 预置条件

## 测试步骤

1.查询GTK是否已安装

```dnf list installed | grep gtk
```

2.未安装执行下面命令安装

```dnf -y install gtk2 libXtst libXrender  xauth
```

## 预期结果

1.查询命令执行成功

2.GTK安装成功

## 备注