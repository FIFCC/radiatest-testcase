# oe_test_disable_ctrl_alt_del_reboot

## 描述

禁止通过Ctrl+Alt+Del重启系统

## 预置条件

## 测试步骤

1. 删除两个ctrl-alt-del.target文件，命令如下：
rm -f /etc/systemd/system/ctrl-alt-del.target
rm -f /usr/lib/systemd/system/ctrl-alt-del.target
2. 修改/etc/systemd/system.conf文件，将#CtrlAltDelBurstAction=reboot-force修改为CtrlAltDelBurstAction=none。
3. 重启systemd，使修改生效，参考命令如下：
systemctl daemon-reexec
4. 输入 ctrl+alt+del  预期1

## 预期结果

1.机器没有重启

## 备注

难以实现