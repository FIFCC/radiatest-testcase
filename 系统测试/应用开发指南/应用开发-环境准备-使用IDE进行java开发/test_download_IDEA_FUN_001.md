# test_download_IDEA_FUN_001

## 描述

下载并运行 IntelliJ IDEA

## 预置条件

安装JDK,安装 tar

## 测试步骤

1.在home下创建目录IntelliJIDEA

```mkdir /home/IntelliJIDEA
```

2.下载最新压缩包：https://www.jetbrains.com/idea/download/download-thanks.html?platform=windows
将下载包放置/home/IntelliJIDEA目录下
3.解压压缩包

```tar xf ideaIE-2020.1.1.tar.gz
```

4.解压后切换到 IntelliJ IDEA 的目录下

```cd .idea-IE-201.7223.119
bin/idea.sh & (报错)
```

## 预期结果

1./home/IntelliJIDEA目录创建成功

2.将最新压缩包放置/home/IntelliJIDEA目录下

3.压缩包解压成功

4.进入到idea-IE-201.7223.119目录下

## 备注