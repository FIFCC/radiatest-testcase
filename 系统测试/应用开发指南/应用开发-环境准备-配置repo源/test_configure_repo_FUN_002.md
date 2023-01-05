# test_configure_repo_FUN_002

## 描述

通过挂载 ISO 的方式配置 repo 源

## 预置条件

## 测试步骤

1.通过跨平台文件传输工具下载 ISO 镜像
登录 openEuler 社区，网址为：https://openeuler.org
单击“下载”，进入下载页面，单击“获取 ISO：”后面的“Link”，显示版本列表，选择需要下载的版本，如 openEuler 20.03 LTS，则单击“openEuler-20.03-
LTS”，进入下载列表
单击“openEuler-20.03-LTS-aarch64-dvd.iso”，将 openEuler 发布包下载到本地
 单击“openEuler-20.03-LTS-aarch64-dvd.iso.sha256sum”，将 openEuler 校验文件下载到本地

2.新建目录用于存放发布包和检验文件的目录
mkdir /home/iso;

3.使用跨平台文件传输工具（如 WinSCP）将本地的 openEuler 发布包和校验文件上传到/home/iso

4.发布包完整性校验

4.1获取校验文件中的校验值

```cat openEuler-20.03-LTS-aarch64-dvd.iso.sha256sum```

4.2.计算 openEuler 发布包的 sha256 校验值

```sha256sum openEuler-20.03-LTS-aarch64-dvd.iso```

4.3对比4.1与4.2的校验值是否相同

5.挂载 ISO 并配置为 repo 源

```mount /home/iso/openEuler-20.03-LTS-aarch64-dvd.iso /mnt/```

6.在/etc/yum.repos.d目录下创建openEuler.repo文件,使用本地镜像挂载目录作为 yum 源，openEuler.repo 的内容如下

```touch openEuler.repo
[base]  
name=base  
baseurl=file:///mnt  
enabled=1  
gpgcheck=1  
gpgkey=file:///mnt/RPM-GPG-KEY-openEuler
```

## 预期结果

1.iso镜像成功下载到本地

2./home/iso目录创建成功

3.下载镜像文件上传至/home/iso

4.1 返回校验文件校验值

4.2 返回发布包的 sha256 校验值

4.3 对比4.1与4.2的校验值相同

5.挂载镜像文件成功

6.openEuler.repo文件创建成功

## 备注