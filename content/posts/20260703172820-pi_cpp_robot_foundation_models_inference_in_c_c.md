+++
title = "pi.cpp: Robot Foundation Models inference in C/C++"
date = 2026-07-03T17:28:00+08:00
tags = ["PUBLIC"]
categories = ["pi.cpp: Robot Foundation Models inference in C/C++"]
draft = false
+++

如果没有精确的测量，那么优化就没有意义。

在众多的模型PR之后，我想了解两个问题：

1.  这些模型在有限的算力下（200T以内），能跑在端测吗
2.  如果可以，那么更大更慢的模型，是不是性能更好

为了回答这个问题，第一步我希望有一个准确的时间测量，最好，这个测量的结果，可以帮助我更好地做端测部署。

这里介绍最近做的一个工作，受llama.cpp启发，它的名字是pi.cpp：

{{< figure src="/ox-hugo/2026-07-08_23-59-55_screenshot.png" >}}

<!--more-->
