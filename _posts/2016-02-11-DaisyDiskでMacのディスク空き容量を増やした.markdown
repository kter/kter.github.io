---
layout: post
title:  "DaisyDiskでMacのディスク空き容量を増やした"
date:   2016-2-11
author: kter
category: Mac
tags: []
---

Macの空きディスク容量が1割を切ったので、原因となっているファイルを調べてみた。

フリーのツールもいくつかあるのだが、今回は[DaisyDisk](https://daisydiskapp.com/)という有償のアプリを使って調べてみた。

256GBのSSDの調査に数十秒かかり、後はディレクトリをたどりながら、今いるディレクトリの使用容量を円グラフで表示できる。


これで調べてみるとどうやらEvernoteで約20GB使っているようだった。

![Evernote使用ディスク容量](http://img.kter.jp/2016/0211/evernote.png)


Evernoteは今後デスクトップアプリ版ではなく、Webアプリ版を使用することにして、アプリはAppCleanerで削除しました。

![Evernoteアプリ削除](http://img.kter.jp/2016/0211/evernote-used-size.png)


というような作業を繰り返し、最終的にホームディレクトリの使用量を142GBまでに広げることができました。

![deleted](http://img.kter.jp/2016/0211/deleted.png)

