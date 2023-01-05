# 本地构建RPM包

## 描述

本地构建RPM包

## 预置条件

安装tree . 安装gdb,安装rpmdevtools

## 测试步骤

1.```dnf install rpmdevtools*```

2.下载源码

```cd ~/rpmbuild/SOURCES
wget http://ftp.gnu.org/gnu/hello/hello-2.10.tar.gz
```

3.创建文件 hello.sepc

```Name: hello
Version: 2.10
Release: 1%{?dist}
Summary: The "Hello World" program from GNU
Summary(zh_CN): GNU "Hello World" 程序
License: GPLv3+
URL: http://ftp.gnu.org/gnu/hello 
Source0: http://ftp.gnu.org/gnu/hello/%{name}-%{version}.tar.gz
BuildRequires: gettext
Requires(post): info
Requires(preun): info
%description
The "Hello World" program, done with all bells and whistles of a proper FOSS
project, including configuration, build, internationalization, help files, etc.
%description -l zh_CN
"Hello World" 程序, 包含 FOSS 项目所需的所有部分, 包括配置, 构建, 国际化, 帮助文件等.
%prep
%setup -q
%build
%configure
make %{?_smp_mflags}
%install
make install DESTDIR=%{buildroot}
%find_lang %{name}
rm -f %{buildroot}/%{_infodir}/dir
%post
/sbin/install-info %{_infodir}/%{name}.info %{_infodir}/dir || :
%preun
if [ $1 = 0 ] ; then
/sbin/install-info --delete %{_infodir}/%{name}.info %{_infodir}/dir || :
fi
%files -f %{name}.lang
%doc AUTHORS ChangeLog NEWS README THANKS TODO
%license COPYING
%{_mandir}/man1/hello.1.*
%{_infodir}/hello.info.*
%{_bindir}/hello
%changelog
* Thu Dec 26 2019 Your Name <youremail@xxx.xxx> - 2.10-1
- Update to 2.10
* Sat Dec 3 2016 Your Name <youremail@xxx.xxx> - 2.9-1
- Update to 2.9
```

4.```rpmbuild -ba hello.spec```

5.```tree ~/rpmbuild/*RPMS```

## 预期结果

1.安装成功

2.源码下载成功

3.hello.spec文件创建成功

4.命令执行成功，解析成功x

5.路径显示正确

## 备注