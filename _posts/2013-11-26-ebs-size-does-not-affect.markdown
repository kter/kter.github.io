---
layout: post
title:  "EC2ストレージ容量が増えない"
date:   2013-11-26
author: kter
category: [server, aws]
tags: [AWS, EC2, EBS]
---
EC2のインスタンスのEBS容量を増やして作成したのにdfコマンドで確認しても8GBしかない…

resize2fsコマンドを使うと本来のサイズに増やせる。

```
$ df -h
Filesystem Size Used Avail Use% Mounted on
/dev/xvda1 7.9G 973M 6.9G 13% /
tmpfs 839M 0 839M 0% /dev/shm
```

なら

```
$ sudo resize2fs /dev/xvda1
```

でOK
