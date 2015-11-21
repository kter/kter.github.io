---
layout: post
title:  "Redmineのmigrate時にObject is not missing constant Project!とエラーが出る"
date:   2013-9-6
author: kter
category: Server
tags: [redmine, mysql]
---
Redmineのインストール時、migrateを行うと

Object is not missing constant Project!

と表示された場合。

/etc/ld.so.confに

```
/usr/local/mysql/lib64/
```

と追加し、/sbin/ldconfigを実行する(/usr/local/mysql/lib64/がなければ/usr/local/mysql/lib/かな）



以上はデータベースにMySQL（バイナリインストール）を使った場合。

要はデータベースのライブラリがないということらしい。むがー
