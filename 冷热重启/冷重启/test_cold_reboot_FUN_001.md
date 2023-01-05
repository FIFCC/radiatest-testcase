# test_cold_reboot_FUN_001

## 描述

使用reboot命令调用poweroff关机

## 预置条件

## 测试步骤

1.关机：reboot -p --poweroff
2.关机等待
3.判断是否关机成功，预期1
ping -c 3 $REMOTE_IP >/dev/null

## 预期结果

1.关机成功