# test_basic_ProcMgmt_004

## 描述

控制挂起脚本

## 预置条件

预备一个脚本test.sh

```while true
do
sleep 1
done
```

## 测试步骤

1.执行脚本sh test.sh

2.执行ctrl+Z键后挂起脚本

fg将挂起的脚步放回前台
bg将挂起的脚步放到后台

## 预期结果

1.执行成功

2.fg将挂起的脚步放回前台
bg将挂起的脚步放到后台

## 备注