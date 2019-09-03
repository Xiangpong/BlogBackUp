---
title: 雷峰塔不是雷锋的塔，WebScoket不是Web的Socket
date: 2019-09-02 17:37:51
tags:
- TCP/IP
- 网络编程
categories: 学习笔记
---


第一次接触WebSocket，感觉和第一次接触JavaScript一样，诶这玩意是不是socket家的哪门亲戚啊？

当然，有了之前学习JavaScript的经验，知道JavaScript和Java八竿子打不到一块，让我对WebScoket的户口保有怀疑。毕竟这个圈子起名字之随意可是出了名的，Java这个名字不就是喝咖啡想起来的嘛。

<!-- more -->
## What is WebSocket？

> WebSocket是一种网络传输协议，可在单个TCP连接上进行全双工通信，位于OSI模型的应用层。  - 维基百科

简单的google了一下，看到了百科大拿Wiki的解释，这说的是啥玩意儿？

我们拆开来看：

- WebScoket是一种网络传输协议：我们熟知的网络传输协议有TCP/IP、HTTP、Scoket等。难道还真是Socket的亲戚？

- 可在单个TCP连接上进行全双工通信：原来是基于TCP传输，这个全双工有点吊，后面会说到。

- 为与OSI模型的应用层：OSI七层模型的应用层位于第七层，在这里的住户有HTTP、 SMTP、SSH等。而Socket并不是这里的住户，而是常年活动在应用层和传输层之间的物业，姑且算他在第五层吧。

综上所述，这个WebSocket和Scoket的亲缘关系，还没有和HTTP近咧。

![](https://upload-images.jianshu.io/upload_images/13963670-0d1b803f800f0c55.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/1120/format/webp)

## WebScoket和老表HTTP

我们已经知道了WebSocket和HTTP都是应用层协议，而且都是基于TCP进行传输。那么WebSocket和老表HTTP又有什么区别呢？

我们对HTTP已经相当熟悉了，寻常的网站都是使用HTTP协议进行通信的。

而HTTP有一个缺陷：就是通信只能由客户端发起，在客户端没有任何请求的情况下，即使那边服务器整个爆炸了，客户端也不知道。直到某一天客户端想起了他的老铁阿服，问了一下阿服的近况，才知道坟头草已经三米高了。（一个悲伤的故事）

这种单向请求的特点，注定了如果服务器有连续的状态变化，客户端要获知就非常麻烦。我们只能使用"轮询"：每隔一段时候，就发出一个询问，了解服务器有没有新的信息。这是非常消耗资源的一种做法。

### WebSocket的特点：

WebSocket最大特点就是，服务器可以主动向客户端推送信息，客户端也可以主动向服务器发送信息，是真正的双向平等对话，这种情况下可以实现：

- 较少的控制开销
- 更强的实时性
- 保持连接状态
- 数据格式比较轻量，性能开销小，通信高效。

最好的应用就是在聊天通话这类即时通讯上。

其他特点包括：

- 建立在 TCP 协议之上，服务器端的实现比较容易。
- 与 HTTP 协议有着良好的兼容性。默认端口也是80和443，并且握手阶段采用 HTTP 协议，因此握手时不容易屏蔽，能通过各种 HTTP 代理服务器。
- 可以发送文本，也可以发送二进制数据。
- 没有同源限制，客户端可以与任意服务器通信。
- 协议标识符是ws（如果加密，则为wss），服务器网址就是 URL。

![](https://camo.githubusercontent.com/ac29fc3c7576339c0a67ad35b10351ce4789a6d5/68747470733a2f2f7777772e6769746875622e636f6d2f6c616e7975616e7869616f79616f2f47697447616c6c6572792f7261772f6d61737465722f323031372f372f32322f254534254238254241254534254242253830254534254239253838254534254238253844254537253942254234254536253845254135254534254244254246254537253934254138736f636b65742532302c254538254246253938254538254136253831254535254145253941254534254239253839254534254238253830254534254238254141254536253936254230254537253941253834776562736f636b65742532302545372539412538342545352539312541322545462542432539462f6267323031373035313530322e706e67)

## WebSocket和Socket

话说回来，WebSocket和Socket是什么关系呢？我经常说的Socket又是什么。

Socket这个词最早来自Unix，在Unix一切皆文件哲学的思想下，Socket是一种"打开—读/写—关闭"模式的实现。

这种模式被搬运到了网络通讯中，Socket是一套API接口，是建立在TCP和应用程序之间的一个抽象层，就是我们之前说的“面向抽象编程”的这个抽象，Socket既不在OSI七层模型中的哪一层，也不是某种协议，而是对复杂网络层操作的一种封装。

![](https://blog.zengrong.net/uploads/2014/12/socket.gif)

而WebSocket则是一种应用层协议。由此可见WebSocket和Scoket关系一般，不值一提。更不是什么WEB的Socket ：)

## 参考
[Socket 与 WebSocket](https://blog.zengrong.net/post/socket-and-websocket/)

[各种网络传输协议理解(TCP/IP, HTTP, Socket)](https://www.jianshu.com/p/dca7dd8abdce)

[WebSocket 教程  -阮一峰](http://www.ruanyifeng.com/blog/2017/05/websocket.html)

[WebSocket -维基百科](https://zh.wikipedia.org/wiki/WebSocket)