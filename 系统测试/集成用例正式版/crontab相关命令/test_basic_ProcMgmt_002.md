# test_basic_ProcMgmt_002

## 描述

crontab相关命令

## 预置条件

## 测试步骤

1.root 查看自己的 cron 设置

```crontab -u root -l```

2.编辑某个用户的 cron 服务

```crontab -e```

3.列出某个用户 cron 服务的详细内容

```crontab -l```

4.删除某个用户的 cron 服务

```crontab -r```

## 预期结果

1.列出root用户的cron设置

2.编辑某个用户的cron服务

3.列出详细内容

4.删除某个用户的cron服务

## 备注