---
layout: post
title:  "pg gemインストール時にPlease install the postgresql adapterとエラーが出る"
date:   2013-7-1
author: kter
category: server
tags: [Ruby, gem, PostgreSQL]
---

```
Please install the postgresql adapter: `gem install activerecord-postgresql-adapter` (libpq.so.5: cannot open shared object file: No such file or directory - /usr/local/lib/ruby/gems/1.8/gems/pg-0.13.2/lib/pg_ext.so)


このlibpq.so.5は/usr/local/pgsql/libに入っているので

/usr/lib/にシンボリックリンクを貼ってみる

sudo ln -s /usr/local/pgsql/lib/libpq.so.5 /usr/lib

これでおｋ
```

