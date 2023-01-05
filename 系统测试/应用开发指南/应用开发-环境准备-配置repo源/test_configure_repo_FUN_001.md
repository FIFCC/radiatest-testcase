# test_configure_repo_FUN_001

## 描述

通过直接获取 repo 源文件的方式配置 repo 源

## 预置条件

## 测试步骤

1.进入到yum源目录

```cd /etc/yum.repos.d;
```

2.新建 local.repo 文件并编辑 local.repo，将 repo 源文件配置为 yum 源

```vi local.repo
```

编辑 local.repo 文件的内容如下：

```[basiclocal] 
name=basiclocal 
baseurl=http://repo.openeuler.org/openEuler-20.03-LTS/OS/aarch64/ 
enabled=1 
gpgcheck=0
```

## 预期结果

1.切换到yum源目录成功

2.编辑local.repo文件成功

## 备注