---
layout: post
title:  "Raspberry PiでWiFiに繋ぐ方法"
date:   2015-12-18
author: kter
category: Server
tags: [Raspberry Pi]
---
Raspberry PiでWiFiに繋ぐ方法

Xが立ち上がっていない場合のWiFiの設定方法が分からなかったのでメモ。

次のファイルに下記内容を追記すれば良い。
繋げたいWiFiが複数ある場合は、そのままnetworkの項目を増やせばいい。

/etc/wpa_supplicant/wpa_supplicant.conf

~~~

network={
  ssid="SSID"
  psk="PASSWORD"
  proto=RSN
  key_mgmt=WPA-PSK
  pairwise=CCMP
  auth_alg=OPEN
}
~~~

