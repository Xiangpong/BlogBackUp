---
title: 在Github上备份Hexo原码
date: 2019-04-01 14:06:33
tags: 笔记
categories:  Hexo 
---

前段时间电脑出了点问题重装了系统，一切都是这么突然 ：(

其实还好，每一次重装系统都是电脑的新生，只要做好备份就好了。

然而百密一疏，我的博客，即Hexo的本地配置文件我忘记备份了。苦哈哈的我只能重新安装配置，还要把之前的日志重新整理、部署。整理的时候我就在想：“早知道就把hexo配置文件上传的GitHub了，这样本地文件丢了也可以从GitHub上clone下来，不用配置得那么辛苦。”

水有源树有根，这就是份日志的根。

<!-- more -->
## 在GitHub上备份Hexo原码

网络上对Github备份Hexo原码的方式主要有两种：
* 给hexo配置文件开一个repo存储
* 在原部署hexo博客的repo开出一个分支存储

我选择第二种方案，操作起来挺简单的 ：)

#### 建立分支hexo

首先在repo开出新分支（要叫啥随便你）hexo，并将hexo分支设置成默认分支。

[![1.jpg](https://i.loli.net/2019/06/09/5cfcab848d2e464824.jpg)](https://i.loli.net/2019/06/09/5cfcab848d2e464824.jpg)

[![2.jpg](https://i.loli.net/2019/06/09/5cfcab8657a8d90542.jpg)](https://i.loli.net/2019/06/09/5cfcab8657a8d90542.jpg)

#### clone项目到本地

我选择本地hexo配置文件夹,打开git bash

```
git clone git@github.com:JeffersonQAQ/JeffersonQAQ.github.io.git
```

#### JeffersonQAQ.github.io文件夹操作

进入download好的文件夹，将.git文件夹之外的文件全部删除

[![3.jpg](https://i.loli.net/2019/06/09/5cfcab824cecc26530.jpg)](https://i.loli.net/2019/06/09/5cfcab824cecc26530.jpg)

因为.git文件夹是隐藏文件夹，看不到的话可以 **查看→隐藏/显示→勾选隐藏文件夹**

回到hexo配置文件夹，将.deploy_git和.git文件夹之外的文件夹复制到JeffersonQAQ.github.io文件夹。

[![4.jpg](https://i.loli.net/2019/06/09/5cfcab83de5b314800.jpg)](https://i.loli.net/2019/06/09/5cfcab83de5b314800.jpg)
#### 关键细节

如果Hexo框架有配置其他主题！
进入JeffersonQAQ.github.io文件夹的themes中，找到该文件夹中所有.git文件夹（仔细找）并删除！因为git不能嵌套上传。

#### 上传的GitHub

在JeffersonQAQ.github.io文件夹中打开git bush，执行以下操作：

```
git add .
```

```
git git commit –m "这里填什么随便你"
```

```
git push
```

**上传完毕**

到GitHub检查一下有没有成功:

[![5.jpg](https://i.loli.net/2019/06/09/5cfcab8543dc298330.jpg)](https://i.loli.net/2019/06/09/5cfcab8543dc298330.jpg)

