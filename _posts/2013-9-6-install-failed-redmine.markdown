---
layout: post
title:  "passenger-install-apache2-moduleが失敗する件について"
date:   2013-9-6
author: kter
category: Server
tags: [ruby, gem, passenger]
---

Passengerをインストールするとき、passenger-install-apache2-moduleを実行しますが、Apacheをソースインストールしていたりすると、次のようなエラーが出てうまくインストールできません。

```
Checking for required software...

* GNU C++ compiler... found at /usr/bin/g++
* Curl development headers with SSL support... not found
* OpenSSL development headers... found
* Zlib development headers... found
* Ruby development headers... found
* OpenSSL support for Ruby... found
* RubyGems... found
* Rake... found at /usr/bin/rake
* rack... found
* Apache 2... not found
* Apache 2 development headers... not found
* Apache Portable Runtime (APR) development headers... not found
* Apache Portable Runtime Utility (APU) development headers... not found
```


上記例では
```
* Curl development headers with SSL support... not found
```
とあるので、yumかなにかでcurl-develをインストールします(yum install curl-devel)。

Apache関係はソースインストールしたせいで、パスを見失っているだけなので、下記コマンドで場所を教えてあげます

```
passenger-install-apache2-module --apxs2-path /usr/local/apache2/bin/apxs --apr-config-path /usr/local/apache2/bin/apr-1-config
```
