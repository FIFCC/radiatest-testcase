# test_install_package_FUN_002

## 描述

安装rpm-build软件包

## 预置条件

## 测试步骤

1.检验rpm-build软件是否已安装

```dnf list installed | grep rpm-build
```

2.清除缓存

```dnf clean all
```

3.创建缓存

```dnf makecache
```

4.安装rpm-build

```dnf install -y rpm-build
```

5.查询安装jdk版本

```rpmbuild --version
```

## 预期结果

1.命令执行成

2.缓存清除成功

3.缓存创建成功

4.rpm-build包安装成功

5.显示正确版本号：RPM version 4.15.1

## 备注