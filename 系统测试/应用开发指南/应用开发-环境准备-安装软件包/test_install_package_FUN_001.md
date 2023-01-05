# test_install_package_FUN_001

## 描述

安装JDK软件包

## 预置条件

## 测试步骤

1.检验jdk软件是否已安装

```dnf list installed | grep jdk
```

2.清除缓存

```dnf clean all
```

3.创建缓存

```dnf makecache
```

4.查看可安装的JDK软件包

```dnf search jdk | grep jdk
```

5.安装jdk

```dnf install -y java-1.8.0-openjdk-devel.aarch64
```

6.查询安装jdk版本

```java -version
```

## 预期结果

1.命令执行成功

2.缓存清除成功

3.缓存创建成功

4.查询到可安装的JDK软件包

5.JDK软件包安装成功

6.查询到版本：openjdk version "1.8.0_242"

## 备注