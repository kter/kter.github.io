---
layout: post
title:  "AWS EC2でタイムゾーンがUTCに戻る場合の対応"
date:   2014-1-23
author: kter
category: aws
tags: [AWS, EC2]
---
タイムゾーンって/usr/share/zoneinfo/Asia/Tokyoを/etc/localtimeにコピーするなりシンボリックリンクを貼るなりすると思うんですけど、EC2の場合はyum updateのタイミングでUTCに戻ってしまう場合があります。ありました

ということで、/etc/sysconfig/clockを書き換えましょう。

/etc/sysconfig/clockは、ハードウェアクロックから読み込んだ値を制御するそうです。

<http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-rg-ja-4/ch-sysconfig.html>



/etc/sysconfig/clockの内容は

```
ZONE="UTC"
UTC=true
```

となってると思います。それを

```
ZONE="Asia/Tokyo"
UTC=false
```

と書き換えましょう。

私の場合は今のところこれでタイムゾーンがJSTで設定できています。
