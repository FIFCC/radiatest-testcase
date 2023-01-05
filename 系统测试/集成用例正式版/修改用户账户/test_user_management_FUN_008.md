# test_user_management_FUN_008

## 描述

用户密码修改_root用户

## 预置条件

/etc/sudoers文件中的
```％wheel ALL =（ALL）ALL```已取消注释
2.创建用户testuser

## 测试步骤

1.以root用户更改root密码

```passwd```

2.以非root用户身份更改或重置忘记的root用户密码
把普通用户加入wheel组usermod -G wheel testuser
vi /etc/sudoers文件，编辑sudoers文件，
添加需要提升权限的账户，在文件中找到
```root ALL=(ALL) ALL```，在该行下添加提升权限的用户信息

```sudo passwd root
```

## 预期结果

root用户下修改密码成功，非root用户下修改密码成功

## 备注