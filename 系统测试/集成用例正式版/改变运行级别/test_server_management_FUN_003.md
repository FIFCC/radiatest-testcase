# test_server_management_FUN_003

## 描述

改变运行级别

## 预置条件

## 测试步骤

1.查看当前系统默认的启动
目标
```systemctl get-default```

2.查看当前系统所有的启动目标
```systemctl list-units --type=target```

3.改变系统默认的目标
```systemctl set-default name.target```

4.改变当前目标
```systemctl isolate name.target```

5.切换到救援模式x
```systemctl rescue```

6.切换到紧急模式
```systemctl emergency```

## 预期结果

1-2.显示成功

3-4.改变成功

5-6.切换成功

## 备注