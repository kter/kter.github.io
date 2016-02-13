---
layout: post
title:  "railsのインストール中のエラー"
date:   2013-11-29
author: kter
category: server
tags: [Ruby, gem]
---
railsをgem installしようとしたら次のエラーが

```
ERROR: While executing gem ... (Gem::DocumentError)
ERROR: RDoc documentation generator not installed: no such file to load -- rdoc/rdoc
```


rdocがないということなのでrdocをgem installしますが次のエラーが発生します。

```
ERROR: While executing gem ... (Gem::DocumentError)
ERROR: RDoc documentation generator not installed: no such file to load -- irb/slex
```


ということで```yum install ruby-irbでruby-irb```をインストールしましょう。

これでエラーがでなくなるのでrdocとrailsをインストールし直しました。
