---
layout: post
title:  "AttributeError: 'module' object has no attribute 'GPIO'"
date:   2015-12-27
author: kter
category: server
tags: [Raspberry Pi]
---

PythonからwebiopiのGPIOを使おうとした時、

AttributeError: 'module' object has no attribute 'GPIO'

と表示される場合の対処。



### WebIOPi-0.7.1をRaspberry Pi2に対応させます

[こちら](http://www.knight-of-pi.org/webiopi-a-simple-but-great-web-api-for-the-raspberry-pi/)を参考に```python/native/cpuinfo.c```と```python/native/gpio.c```を修正します。

* cpuinfo.c

    BCM2708をBCM2709に変更

* gpio.c

    ```define BCM2708_PERI_BASE 0x20000000```を```define BCM2708_PERI_BASE 0x3f000000```に変更

その後```setup.sh```を実行し直します。

### WiringPi2-PythonをPython3で動くようにします

Python3をインストール

```sudo aptitude install python3```

Python3をデフォルトにする
```
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.4 2
```

WiringPi2-Pythonをインストールしなおす

```sudo ./setup.py install```
