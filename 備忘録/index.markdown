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

## Git

### 日本語ファイル取り扱い設定

```git status```で日本語のファイル名の文字化けを防ぐ

~~~Bash
git config --global core.quotepath false
~~~

### リモートブランチ削除

```
% git push --delete origin foo
```

## シェルスクリプト

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

### 数字だけ抜き出す

```
$ sed -r 's/[^0-9]//g'
```

### 数値化どうか判定

exprで加算し、ステータスコードを確認する

```
expr "判定したい変数" + 1 >/dev/null 2>&1
if [ $? -lt 2 ]
then
  # 数字
else
  # 数字以外
fi
```

## Vim

### 文字コードと改行コードの変更方法

~~~
set fileencoding=文字コード
set fileformat=unixもしくはdos
~~~

### 現在行から文末までa-zで始まる単語の前にsudoを付ける

```
:.,$s/^\([a-z]\)/sudo\ \1/gc
```

### エンコード

読み込みエンコードを変更

```
:e ++enc=sjis
```

文字コード変換

```
:set fenc=sjis
```

