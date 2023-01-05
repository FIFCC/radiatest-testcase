# oe_test_pkgmnt_queryall_006

## 描述

自定义初始化配置文件，配置多个有效的db；通过平台文件指定初始化配置文件；命令参数指定db，查询指定数据库包列表

## 预置条件

配置conf.yaml文件:
- dbname: openEuler
  src_db_file: openEuler-src.sqlite
  bin_db_file: openEuler-bin.sqlite
  status: enable
  priority: 1
- dbname: fedora
  src_db_file: fedora_src.sqlite
  bin_db_file: fedora-bin.sqlite
  status: enable
  priority: 2

## 测试步骤

1. 配置conf.yaml文件，放在指定路径/home/conf.yaml，执行初始化命令：pkgship init
2. pkgship list -db openEuler | wc -l
3. 执行以下命令来获得指定数据库中实际包数量，与第2步获得的数量进行比较：
dnf list --installroot=/home --repo=openEuler --releasever=1 | grep openEuler | wc -l

## 预期结果

1. 初始化数据库成功_x000D_
2. 查询包数量成功_x000D_
3. pkgship查询到的包的数量与dnf查询到的指定数据库包实际数量相同