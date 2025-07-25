+++
title = "OOP considered harmful"
date = 2025-07-18T10:28:00+08:00
aliases = ["/posts/oop"]
tags = ["PUBLIC"]
draft = false
+++

一直想记录一下这一点。

现在互联网上很讲究“觉醒”，类似忽然发现小时候习以为常的事情，其实是PUA什么的。

虽然用在这里不是很恰当，但是感觉在我所需要的领域里面，OOP确实带来的都是不好的体验。

但是这个不好来自哪里，做了很多次尝试才慢慢清晰。

这个起点应该是从[从SICP说起：重新学习（函数式）编程]({{< relref "20220224200513-sicp.md" >}})开始，到今天看到一个youtube视频[Casey Muratori – The Big OOPs: Anatomy of a Thirty-five-year Mistake – BSC 2025](https://www.youtube.com/watch?v=wo84LFzx5nI)觉得值得写下来记录一下。

<!--more-->

感觉今天不是很有精力自己总结。。看了下ChatGPT总结的挺好。


## 一个持续了35年的错误 {#一个持续了35年的错误}


### 演讲主题： {#演讲主题}

批判面向对象编程（OOP）作为一种错误持续了35年，并探讨其带来的系统性问题。


### 核心观点总结： {#核心观点总结}

OOP 的初衷与现实脱节

OOP 原本是为了更好地模拟现实世界，通过“对象”封装数据与行为。

但在实际应用中，这一思想往往被误用或滥用，导致系统架构复杂、维护困难。

1.  抽象的陷阱
    OOP 鼓励过度抽象（如复杂的继承层次、多态的过度使用），反而降低了代码可理解性。

    人为构造的“对象层级”无法反映真实的程序需求，只是人为的组织方式。
2.  数据隐藏与封装反而阻碍开发
    OOP 鼓励将数据隐藏在类内部，这反而阻碍了对数据的直接操作和全局理解。

    相比之下，使用结构体和纯函数（如在C语言或数据导向设计中）更有利于程序的清晰性和可调试性。
3.  面向对象的架构膨胀
    使用 OOP 时常会为了“设计模式”而引入过多类和接口，导致“样板代码”泛滥。

    程序员为了迎合OOP范式，被迫遵循复杂的结构，而不是直接解决问题。
4.  工程效率受限
    OOP 在大规模系统中往往带来维护困难和性能问题。

    相比之下，数据驱动编程、函数式编程或 ECS（实体-组件-系统）模型更适合构建复杂系统。
5.  OOP 误导了几代程序员
    教育体系普遍推崇OOP，使得很多开发者从一开始就被错误的范式所引导。

    应当对软件设计进行更本质性的重新思考，而不是机械地遵循某种“范式”。


## 建议和替代方案： {#建议和替代方案}

推崇 数据导向设计（Data-Oriented Design）：将数据结构设计放在核心位置，代码围绕数据流进行组织。

鼓励 纯函数编程 与 最小必要结构设计：减少依赖、提高可读性与可测试性。

强调 实际需求导向 的编程风格：避免“为了设计而设计”，重回“为问题找解法”的本源。


## 更具体的例子 {#更具体的例子}

1.  GUI 组件设计的荒谬性
    他举了“按钮 Button”的例子，来说明 OOP 如何将简单的元素变得过度复杂：

    **例子内容**

    > 开发者经常会创建一个 Button 类，并让它继承自 Widget，Widget 又继承自 Component，然后还有 Renderable, EventEmitter 等接口。
    > 最后只为了画一个按钮，却变成了一个继承树非常庞大的结构。

    **批判点**

    > 他指出这种“把东西强行变成对象”的做法完全没有必要，只是为了迎合 OOP 的范式而构建一大堆抽象层级，反而破坏了代码的可维护性。
2.  矩阵库的设计
    他批评了 OOP 风格的矩阵类库，比如 Matrix4x4 类，这些类往往会绑定具体的接口和操作方式，例如旋转、平移等操作都作为类的方法封装。

    **例子内容**

    > 开发者可能会写成 matrix.rotate(angle) 或 matrix.translate(x, y, z)，让矩阵自己“知道”怎么变换。

    **批判点**

    > 他认为这不如用简单的纯函数来操作矩阵来得清晰，比如 rotateMatrix(matrix, angle)，这种方式不依赖封装，更利于理解和调试。
3.  游戏开发中的实体系统（Entity Systems）
    他以游戏开发为例，说明传统 OOP 风格的“敌人类 Enemy extends Character extends Actor extends Object...”等结构是非常脆弱的。

    **例子内容**

    > 比如某个游戏角色既能飞又能游泳，这时 OOP 风格的继承树就很难处理“多重能力组合”的问题。

    **批判点**

    > 他主张使用组件式设计（ECS，Entity-Component-System），将行为拆解为数据块，如 HasFlight, HasSwimming, HealthComponent 等，用组合而非继承来构建复杂行为。
4.  汽车比喻：你不会让车轮“知道”怎么开车
    这是一个比喻性质的例子，说明对象不应当“知道太多事情”。

    **例子内容**

    > 如果你设计一辆汽车，你不会让“轮子对象”自己知道如何驾驶。你会有一个更高层次的控制系统协调一切。

    **批判点**

    > OOP 鼓励“每个对象封装自己的行为”，但很多时候这根本不符合系统架构的实际逻辑。
5.  操作系统和编译器的设计
    他提到在低层系统开发中（比如操作系统或编译器），很少使用 OOP，因为需要精确控制内存、数据结构和逻辑流。

    **批判点**

    > 这些高性能的系统往往采用结构化编程或函数式风格，说明 OOP 在这类严肃工程中并不合适。
