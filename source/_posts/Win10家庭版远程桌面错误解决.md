---
title: Win10家庭版远程桌面错误解决
date: 2019-03-07 20:34:04
tags:
---

注册表目录添加：
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Policies\System\CredSSP\Parameters
在此添加DWORD（32）位，命名为  AllowEncryptionOracle 
并将此值修改为2

[来源链接](https://blog.csdn.net/qq_42195688/article/details/80505329)