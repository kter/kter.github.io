---
layout: post
title:  "LetsEncrypt証明書発行方法"
date:   2016-4-17
author: kter
category: server
tags: [証明書]
---

Dockerで証明書を発行できる。

※外部から443にアクセスできるようポートを開けておく

```
docker run -it --rm -p 443:443 --name letsencrypt -v "/etc/letsencrypt:/etc/letsencrypt" -v "/var/lib/letsencrypt:/var/lib/letsencrypt" quay.io/letsencrypt/letsencrypt:latest certonly
```

生成されたファイルは下記ファイルに保存される

```
/etc/letsencrypt/live/ドメイン名/fullchain.pem
/etc/letsencrypt/live/ドメイン名/privkey.pem
```
