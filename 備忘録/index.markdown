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
