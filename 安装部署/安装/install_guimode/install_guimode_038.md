# install_guimode_038

## 描述

使用软raid盘安装系统

## 预置条件

组软raid
清空用到盘的磁盘分区
mdadm  -Cv /dev/md1 --metadata=1.0 -l1 -n2 -x0 /dev/sda /dev/sdb --size=500G --bitmap=none
cat /proc/mtstat
重启OS系统

## 测试步骤



## 预期结果