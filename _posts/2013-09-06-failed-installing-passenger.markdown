---
layout: post
title:  "gemでpgをインストールしようとするとNo pg_config... trying anyway. If building fails, please try again withとエラーが表示される"
date:   2013-7-1
author: kter
category: Server
tags: [Ruby, gem, PostgreSQL]
---
gemでpgをインストールしようとするとNo pg_config... trying anyway. If building fails, please try again withとエラーが表示される

```
% sudo gem install pg -v=0.13.2
Building native extensions. This could take a while...

ERROR: Error installing pg:
ERROR: Failed to build gem native extension.

/usr/local/bin/ruby extconf.rb
checking for pg_config... no
No pg_config... trying anyway. If building fails, please try again with
--with-pg-config=/path/to/pg_config
checking for libpq-fe.h... no
Can't find the 'libpq-fe.h header
*** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of
necessary libraries and/or headers. Check the mkmf.log file for more
details. You may need configuration options.

Provided configuration options:
--with-opt-dir
--without-opt-dir
--with-opt-include
--without-opt-include=${opt-dir}/include
--with-opt-lib
--without-opt-lib=${opt-dir}/lib
--with-make-prog
--without-make-prog
--srcdir=.
--curdir
--ruby=/usr/local/bin/ruby
--with-pg
--without-pg
--with-pg-dir
--without-pg-dir
--with-pg-include
--without-pg-include=${pg-dir}/include
--with-pg-lib
--without-pg-lib=${pg-dir}/lib
--with-pg-config
--without-pg-config
--with-pg_config
--without-pg_config
Gem files will remain installed in /usr/local/lib/ruby/gems/1.8/gems/pg-0.13.2 for inspection.
Results logged to /usr/local/lib/ruby/gems/1.8/gems/pg-0.13.2/ext/gem_make.out
```

こんな感じのエラーが表示された場合、

```
sudo gem install pg -v=0.13.2 -- --with-pg-config=/usr/local/pgsql/bin/pg_config
```

などとpg_configのパスを指定すればおｋ
