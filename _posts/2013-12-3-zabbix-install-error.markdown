---
layout: post
title:  "configure: error: Jabber library not found"
date:   2013-12-3
author: kter
category: Server
tags: [Zabbix]
---
Zabbix 1.8をソースからインストールした時次のエラーが発生。

```
checking for iksemel support… no
configure: error: Jabber library not found
```


iksemeはEPELリポジトリからインストールします。

AmazonAMIならば次のコマンドでiksemelインストールできるでしょう

```
sudo yum --enablerepo=epel install iksemel iksemel-devel
```
