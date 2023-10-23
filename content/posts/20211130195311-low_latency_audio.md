+++
title = "low_latency_audio"
date = 2021-11-30T19:53:00+08:00
tags = ["PUBLIC"]
draft = false
+++

当我们讨论元宇宙的时候，能不能先把线上讨论的音频延迟问题解决。。。

这个问题解决是乐观的，因为我们通常认为影响延迟的部分（真实的网络延迟，中美做到200ms并不难，但是做到100ms几乎在物理上是不可能的）在这个问题里面并不占主要部分。

而鲜为人知的是，我们现有的audio driver stack（因为历史原因）往往设置了不小的buffer去缓冲网络问题。

因为这个历史问题，现有的端到端音频的延迟在500ms到1s这个级别。

如果在考虑WiFi（网络包更波动）、蓝牙耳机（再加100ms）的因素，我们是在一个&gt;1s的延迟下，妄图在线上做到线下富有特色的small talk。

幸运的是，疫情不只推广了zoom，也推广了低延迟音频，感谢执着于在疫情期间也要排练乐团的人们。

<!--more-->

-   [jamulus](https://jamulus.io/)
-   [jacktrip](https://jacktrip.github.io/jacktrip/)
-   [farplay](https://farplay.io/)
-   [sonobus](https://sonobus.net/)
-   [mumble](https://www.mumble.info/)

测量[Audio Latency - Some Measurements](https://www.cs.cmu.edu/~rbd/blog/latency-blog22sep2020.html)

[latency_test]({{< relref "20230510173526-latency_test.md" >}})
