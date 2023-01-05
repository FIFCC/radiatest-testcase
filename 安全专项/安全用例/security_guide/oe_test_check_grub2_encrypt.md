# oe_test_check_grub2_encrypt

## 描述

检查GRUB2加密口令

## 预置条件

## 测试步骤

1.使用grub2-mkpasswd-pbkdf2命令生成加密的口令， 预期1
2.修改/boot/efi/EFI/openEuler/grub.cfg中password_pbkdf2 位置，改为获得的口令
set superusers="root"
password_pbkdf2 root   第一步获得的口令
3.重启。在启动引导界面按e ， 根据提示输入用户密码，预期2

## 预期结果

1.命令执行成功
2.进入启动参数修改界面

## 备注

难以实现