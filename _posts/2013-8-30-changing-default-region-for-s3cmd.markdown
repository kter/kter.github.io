---
layout: post
title:  "s3cmdのデフォルトリージョンを東京にする"
date:   2013-8-30
author: kter
category: Server
tags: [s3cmd, aws]
---
s3cmdではデフォルトでUSリージョンが設定されます。

これを東京リージョンで設定するには、ホームディレクトリの.s3cfgを編集します

以下の4つのオプションをそれぞれ書き換えれば大丈夫です

```
bucket_location = ap-northeast-1
host_base = s3-ap-northeast-1.amazonaws.com
host_bucket = %(bucket)s.s3-ap-northeast-1.amazonaws.com
simpledb_host = sdb.ap-northeast-1.amazonaws.com
```
