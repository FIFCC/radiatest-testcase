# oe_test_KAE_openssl_compare_002

## 描述

升级加速器软件包

## 预置条件

1.已安装uacce* hisi* libwd-* libkae*等包

## 测试步骤

1.准备好要升级的包

2.升级

```rpm -Uvh uacce* hisi* libwd-* libkae*
```

3.检查版本是否升级成功

```rpm -qa | grep -iE "uacce|hisi | libwd | libkae "
```

4.卸载旧驱动

```# rmmod hisi_hpre
# rmmod hisi_sec2
# rmmod hisi_qm
# rmmod uacce
```

5.加载新驱动

```modprobe uacce
modprobe hisi_qm
modprobe hisi_sec2
modprobe hisi_hpre
```

## 预期结果

1.已下载要升级软件包

2-3.升级成功

4.卸载成功

5.加载成功

## 备注