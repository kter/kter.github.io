---
layout: post
title:  "Zabbix FrontendでDBに接続できない場合の対処"
date:   2015-12-13
author: kter
category: Server
tags: [Zabbix]
---
zabbix-serverはDBに繋がるのにweb frontはDBがタイムアウトになる場合

RPMでインストールした場合、フロントエンドのDB設定は/usr/share/zabbix/conf/zabbix.conf.phpではなく/etc/zabbix/web/zabbix.conf.phpを参照するため、このファイルを変更する必要があります。
