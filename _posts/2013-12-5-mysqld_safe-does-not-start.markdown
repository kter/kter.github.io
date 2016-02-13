---
layout: post
title:  "File './mysql-bin.index' not found (Errcode: 13)"
date:   2013-12-5
author: kter
category: server
tags: [MySQL]
---
mysqlをソースからインストールして、mysqld_safeなどで起動しようとした時、次のエラーが発生
 
```
File './mysql-bin.index' not found (Errcode: 13)
```


インストールが終わった後にmysql_install_dbでデータベースを初期化?したのだが、オプションを指定しないといけなかったらしい。多分datadirの指定が必要だったんだな。



というわけでインストール先ディレクトリのオーナーとグループを mysqlに

```
$ sudo chown mysql.mysql /usr/local/mysql
```

mysql_install_dbにオプションを付けて次のように実行

```
$ sudo /usr/local/mysql/bin/mysql_install_db --user=mysql --basedir=/usr/local/mysql --datadir=/usr/local/mysql/data
```
