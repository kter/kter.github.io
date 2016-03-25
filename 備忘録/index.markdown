---
layout: page
title:  "備忘録"
author: kter
---

# 備忘録

## MySQL文字コード確認

tableのcharset

~~~MySQL
mysql> show variables like 'character\_set\_%';
~~~

dbのcharset

~~~MySQL
mysql> show create database DBname;
~~~

## Gitの日本語ファイル取り扱い設定

```git status```で日本語のファイル名の文字化けを防ぐ

~~~Bash
git config --global core.quotepath false
~~~

## Vimで文字コードと改行コードの変更方法

~~~
set fileencoding=文字コード
set fileformat=unixもしくはdos
~~~

## sedサンプル

以下のサンプルはMacのsedでは動かない。<br />
これはMacに入っているsedはBSD由来のPOSIX sedなためである。<br />
一般的なLinuxに入っているsedを使用するためにはGNU sedをインストールする。<br />
brewを使っているならgnu-sedをインストールし、PATHの優先を上げ、POSIX sedではなくGNU sedが呼び出されるようにする。

### ファイル名の.gzの前に文字列を挿入する

```
$ echo hoge.log.201603170000.gz | sed -r "s/(\.gz)/-hoge\1/g"
hoge.log.201603170000-hoge.gz
```

### ファイル名の日付部分のみを抽出する

\1を使うときは全範囲を指定しつつカッコでグループ化する

```
$ echo hoge.log.201603170000.gz | sed -r 's/^.*([0-9]{12}).*$/\1/g'
201603170000
```


