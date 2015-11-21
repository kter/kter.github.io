---
layout: post
title:  "mod_pythonをインストールしようとした時checking for Py_NewInterpreter in -lpython2.6... no configure: error: Can not link to pythonとエラーが出る"
date:   2013-9-6
author: kter
category: Server
tags: []
---
mod_pythonを入れようとして、

```
$ ./configure --with-apxs=/usr/local/apache2/bin/apxs
checking for gcc... gcc
checking for C compiler default output file name... a.out
(略)
checking for Py_NewInterpreter in -lpython2.6... no
configure: error: Can not link to python
```



と表示された場合。

```
yum install python-devel
```

で解決
