---
layout: post
title:  "SSH fingerprintの確認方法"
date:   2013-7-30
author: kter
category: server
tags: [SSH]
---

```
ssh-keygen -lf /etc/ssh/ssh_host_rsa_key.pub
```


OS再インストールした時、remote host identification has changedとか言われるのはこの公開鍵が変わるからなのね。

参考

<http://d.hatena.ne.jp/Artisan/20130325/1364222117>
