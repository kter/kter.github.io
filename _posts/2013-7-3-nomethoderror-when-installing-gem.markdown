---
layout: post
title:  "ERROR: While executing gem ... (NoMethodError) undefined method `map' for Gem::Specification:Class"
date:   2013-7-3
author: kter
category: server
tags: [Ruby, gem]
---
```
% sudo gem install hogehoge_gem
Successfully installed hogehoge_gem
1 gem installed
Installing ri documentation for hogehoge_gem...
ERROR: While executing gem ... (NoMethodError)
undefined method `map' for Gem::Specification:Class
```

とか表示されるとき

~/.gemrcに

```gem: --no-rdoc --no-ri```

 を追加すればよろし。
  
 ```sudo gem install hogehoge_gem --no-rdoc --no-ri```
 でも同じことだと思う(未確認)
  
  
 参考
 <http://stackoverflow.com/questions/7535737/using-no-rdoc-and-no-ri-with-bundler>
