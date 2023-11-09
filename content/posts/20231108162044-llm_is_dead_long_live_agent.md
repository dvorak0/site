+++
title = "LLM is dead, long live agent"
date = 2023-11-08T16:20:00+08:00
tags = ["PUBLIC"]
draft = false
+++

![](/ox-hugo/2023-11-08_16-22-44_screenshot.png)
是这样吗？

<!--more-->

自Tesla之后，又多了一个需要逐帧学习的发布会。

那么OpenAI在说什么。

确实需要把重点从world model移开，关注如何更好地使用这个先验模型。

就好像即使人出生的时候已经如此聪明了，还是要经历长时间地教育去获得更多慢思考的品质：耐心、共情、自省等等。

LLM给我们的，只有next ONE token generation接口，那么只是朴素地使用这个接口，能写出来最好的东西吗，现在看起来是未必的。

举一个最简单的例子：RAG(Retrieval Augmented Generation)是不是一个solved problem？不是，否则就不会有那么多的RAG方法。

{{< figure src="/ox-hugo/2023-11-08_16-34-10_screenshot.png" >}}

再结合yann lecun的挑战，我们确实能在这个空间里找到那个token sequences吗，尤其是在面对复杂任务的时候。

{{< figure src="/ox-hugo/2023-11-09_13-48-30_screenshot.png" >}}

新的机会，但是也需要一些新的突破？
