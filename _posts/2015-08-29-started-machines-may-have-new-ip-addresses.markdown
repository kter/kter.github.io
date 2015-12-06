---
layout: post
title: docker-machineでStarted machines may have new IP addresses. You may need to
  re-run the `docker-machine env` command.と言われる件について
author: kter
category: Server
tags: [VirtualBox, Docker]
---
<p>docker-machineでStarted machines may have new IP addresses. You may need to re-run the `docker-machine env` command.と言われる件について</p>
<blockquote class="twitter-tweet" lang="ja">
<p dir="ltr" lang="ja">docker-machine startを実行するとdocker-machine envを実行しろと言われ、docker-machine envを実行するとdocker-machine startを実行しろと言われるので詰んだ</p><br />
&mdash; ことえり (@kter) <a href="https:&#47;&#47;twitter.com&#47;kter&#47;status&#47;637494883276591104">2015, 8月 29</a></blockquote><br />
<script src="&#47;&#47;platform.twitter.com&#47;widgets.js" async="" charset="utf-8"></script></p>
<p>とdocker-machine envを実行してもdocker-machine startを実行しろと言われ堂々巡りに。</p>
<p>おもむろにVirtualBoxで直接起動しようとしたらエラーがでて起動できませんでした。</p>
<p>VirtualBoxのバグのようなので4.3にダウングレードしました。</p>
<p>その後docker-machine start default, docker-machine regenerate-certs default, docker-machine env defaultで無事dockerが使えるようになりました。</p>
