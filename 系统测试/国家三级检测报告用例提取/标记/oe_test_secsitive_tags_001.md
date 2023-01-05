# oe_test_secsitive_tags_001

## 描述

操作系统SSOOS安全功能控制范围内的主体和客体设置敏感标记构成多级安全模型的属性库。

## 预置条件

## 测试步骤

1.系统管理员登录建立各军级帐号并初始化密码

```$su -
# useradd testuser1
#passwd testuser1
# useradd testuser2
#passwd testuser2
# useradd testuser3
#passwd testuser3
```

2.安全管理员登录建立不同安全级用户

```$su -
#semanage user -a -R user_r -r s2 -L s2 testuser1_u
#semanage user -a -R user_r -r s1 -L s1 testuser2_u
#semanage user -a -R user_r -r s0 -L s0 testuser3_u
```

3.安全管理员建立linux用户与不同安全用户建立映射

```#semanage login -a -s testuser1_u -r s2 testuser1
#semanage login -a -s testuser2_u -r s1 testuser2
#semanage login -a -s testuser3_u -r s0 testuser3
```

4.不同用户登录在/tmp目录下建立文件testuser1

```$echo testuser1 > /tmp/testuser1
$chmod 666 /tmp/testuser1
$ls -Z /tmp/testuser1
$echo testuser2 > /tmp/testuser2
$chmod 666 /tmp/testuser2
$ls -Z /tmp/testuser2
$echo testuser3 > /tmp/testuser3
$chmod 666 /tmp/testuser3
$ls -Z /tmp/testuser3
```

5.用户testuser2登录并执行如下命令

（1）```$cat /tmp/testuser1```

（2）```$cat /tmp/testuser2```

（3）```$cat /tmp/testuser3```

（4）```$echo testuser2 >> /tmp/testuser1```

（5）```$echo testuser2 >> /tmp/testuser2```

（6）```$echo testuser2 >> /tmp/testuser3```

（7）```cat /tmp/testuser2 >> /tmp/testuser1```

（8）```cat /tmp/testuser2 >> /tmp/testuser3```

## 预期结果

1-3执行成功

4.各个敏感标记
文件 testuser1 s2
文件 testuser2 s1
文件 testuser3 s0

5.各个命令显示如下
（1）permission denied（低保密主体无法读取高保密性数据）
（2）testuser2 （同级可读）
（3）testuser3 （高保密主体可读低保密性数据）
（4）无显示 （低保密主体可向上写）
（5）无显示（同保密级可写）
（6）permission denied（高保密主体不可向下写）
（7）无显示（低等级安全数据可以流向高等级安全区域）
（8）permission denied（高安全等级数据不能流向低等级区域）
s0,s1,s2表示主客体敏感标记

## 备注

无安全管理员，创建安全级用户报错
semanage执行报错

```semanage
libsepol.mls_from_string: invalid MLS context s2
libsepol.mls_from_string: could not construct mls context structure
libsepol.sepol_user_modify: could not load (null) into policy
libsemanage.dbase_policydb_modify: could not modify record value
libsemanage.semanage_base_merge_components: could not merge local modifications into policy
OSError: [Errno 0] Error
```