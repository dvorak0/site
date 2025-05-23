+++
title = "low latency audio: measurement"
date = 2024-07-20T13:02:00+08:00
tags = ["PUBLIC"]
draft = false
+++

终于有时间做一个测试，回答长久以来(见[low latency audio]({{< relref "20211130195311-low_latency_audio.md" >}}))很有疑问的一个问题。

我们常用的语音通话服务的延迟究竟是多少。

<!--more-->


## 测试手段 {#测试手段}

同样的网络环境中，两台设备分别在麦克风/扬声器附近放一个麦克风。
两个麦克风分别作为左右声道接入声卡录音。


## 测试结果 {#测试结果}


### lltalk {#lltalk}

{{< figure src="/ox-hugo/2024-07-20_11-56-44_screenshot.png" >}}

\\[2.173-2.145=0.028s\\]


### 微信语音 {#微信语音}

{{< figure src="/ox-hugo/2024-07-20_11-53-29_screenshot.png" >}}

\\[1.571-0.047=0.524s\\]


### 腾讯会议 {#腾讯会议}

{{< figure src="/ox-hugo/2024-07-20_11-55-01_screenshot.png" >}}

\\[1.563-1.173=0.390s\\]


### 电话，联通-电信 {#电话-联通-电信}

{{< figure src="/ox-hugo/2024-07-20_11-55-45_screenshot.png" >}}

\\[1.652-1.329=0.321s\\]


### Lark {#lark}

{{< figure src="/ox-hugo/2024-07-20_13-18-02_screenshot.png" >}}

\\[2.561-2.253=0.308s\\]


### Lark wired {#lark-wired}

{{< figure src="/ox-hugo/2024-09-13_18-09-04_screenshot.png" >}}

\\[6.458-6.180=0.278s\\]


### [VDO.ninja](https://vdo.ninja/) WebRTC {#vdo-dot-ninja-webrtc}

{{< figure src="/ox-hugo/2024-09-24_21-39-20_screenshot.png" >}}

\\[3.643-3.350 =0.293\\]


### Mumble {#mumble}

{{< figure src="/ox-hugo/2024-07-21_14-54-28_screenshot.png" >}}

\\[2.351-1.618=0.733s\\]


### 腾讯会议 PC Wired {#腾讯会议-pc-wired}

{{< figure src="/ox-hugo/2024-12-13_16-12-36_screenshot.png" >}}
