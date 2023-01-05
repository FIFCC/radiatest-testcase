# oe_test_pkgmnt_query_single_009

## 描述

自定义初始化配置文件，配置多个数据库配置，查询单包信息，在查询过程中降低db的权限

## 预置条件

配置conf.yaml文件:
- dbname: :yang
  src_db_file: data_1_src.sqlite
  bin_db_file: data_1_bin.sqlite
  status: enable
  priority: 1
- dbname: ylj
  src_db_file: data_2_src.sqlite
  bin_db_file: data_2_bin.sqlite
  status: enable
  priority: 2

## 测试步骤

1. 配置conf.yaml文件，放在指定路径/home/conf.yaml，执行初始化命令：pkgship init
2. 执行以下命令的同时在查询过程中降低db的权限：
   pkgship singe A

## 预期结果

异常