# test_set_XXL_FUN_001

## 描述

设置XLL Forwarding

## 预置条件

## 测试步骤

1.切换到sshd配置目录，目录不存在时创建目录

```cd ~/.ssh
```

2.在ssh下编辑config文件并保存

```vim config
```

内容如下：

```Host *  
 	 	  ForwardAgent yes  
 	 	  ForwardX11 yes
```

## 预期结果

1.进入到ssh目录下

2.config文件编辑成功

## 备注