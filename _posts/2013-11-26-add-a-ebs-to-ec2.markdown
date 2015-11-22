---
layout: post
title:  "EC2にEBSボリュームの追加する"
date:   2013-11-26
author: kter
category: AWS
tags: [AWS, EC2, EBS]
---
EC2はEBSボリュームの追加を追加することができます。

ですが追加したディスクのフォーマットやマウントは自分で行う必要があります。



マウントするためにはまず、lsblkコマンドでどの名前でEBSが認識されているのかを確認します。

```
$ lsblk
NAME MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvdb 202:16 0 200G 0 disk
xvda1 202:1 0 50G 0 disk /
xvda3 202:3 0 896M 0 disk [SWAP]
```

この場合はxvdbという名前で認識されています。xvda1はシステムが入っているRootパーティションですね。



次にファイルシステムを作成します。

ext4で作成するにはmke2fsコマンドを使います

```
# mke2fs -t ext4 /dev/xvdb
mke2fs 1.42.3 (14-May-2012)
Filesystem label=
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
13107200 inodes, 52428800 blocks
2621440 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=0
1600 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks:
32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208,
4096000, 7962624, 11239424, 20480000, 23887872

Allocating group tables: done
Writing inode tables: done
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done
```


これでマウントする準備が出来ました。mountコマンドでマウントしましょう。

下記の例は/dev/xvdbを/mntにマウントします。

```
# mount /dev/xvdb /mnt
```



システム起動時に自動的にマウントしたい時は/etc/fstabに必要な情報を記入します。

基本的には下記のとおりでいいかと。/dev/xvdbで始まる行が追加した行です。

```
$ cat /etc/fstab
#
LABEL=/ / ext4 defaults,noatime 1 1
/dev/xvdb /mnt ext4 defaults,noatime 1 1
tmpfs /dev/shm tmpfs defaults 0 0
devpts /dev/pts devpts gid=5,mode=620 0 0
sysfs /sys sysfs defaults 0 0
proc /proc proc defaults 0 0
/dev/sda3 none swap sw,comment=cloudconfig 0 0
```


