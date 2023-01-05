# test_server_management_FUN_004

## 描述

系统关机下电等操作

## 预置条件

## 测试步骤

重启系统
```systemctl reboot```

关闭系统但不下电
```systemctl halt```

关闭系统并下电
```systemctl poweroff```

使系统待机
```systemctl suspend```

使系统休眠
```systemctl hibernate```

休眠且待机
```systemctl hybrid-sleep```

## 预期结果

1.重启成功

2.关闭系统成功

3.关闭下电成功

4.待机成功

5.休眠成功

6.休眠待机成功

## 备注