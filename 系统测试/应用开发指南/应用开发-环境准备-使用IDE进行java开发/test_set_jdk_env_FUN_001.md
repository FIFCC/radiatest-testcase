# test_set_jdk_env_FUN_001

## 描述

设置JDK环境

## 预置条件

## 测试步骤

1.查看Java路径

```which java
```

2.查看软链接的实际指向目录

```ls -la /usr/bin/java
ls -la /etc/alternatives/java
```

3.设置JAVA_HOME 和 PATH

```export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.232.b09-1.h2.aarch64 
export PATH=$JAVA_HOME/bin:$PATH
```

## 预期结果

1.java路径为：/usr/bin/java

2.命令返回：

```lrwxrwxrwx. 1 root root 22 May 25 15:30 /usr/bin/java -> /etc/alternatives/java
lrwxrwxrwx. 1 root root 75 May 25 15:30 /etc/alternatives/java -> /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-1.h5.oe1.aarch64/jre/bin/java
```

3.JAVA_HOME 和 PATH配置成功

## 备注