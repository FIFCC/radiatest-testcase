# oe_test_KAE_uninstall_001

## 描述

卸载加速引擎软件包

## 预置条件

## 测试步骤

1.卸载加速引擎内核驱动

```# lsmod | grep uacce
uacce 36864 3 hisi_sec2,hisi_qm,hisi_hpre
# rmmod hisi_hpre
# rmmod hisi_sec2
# rmmod hisi_qm
# rmmod uacce
# lsmod | grep uacce 
```

2.卸载相关包

```yum rmove -y uacce* hisi* libwd-* libkae*```

## 预期结果

1.卸载驱动成功

2.卸载相关包无异常

## 备注