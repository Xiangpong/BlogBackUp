---
title: 轻量级标记语言！- Markdown
date: 2018-11-09 
tags:
- 笔记
- 分享
categories:  学习笔记 
---
Markdown是一种轻量级的标记语言，相较Word那种复杂的排版设置，和各类文字样式，它使用简洁语法代替排版,使普通文本内容具有一定的格式。相当于带有简化版HTML标记语言的记事本，被写作爱好者，撰稿者广泛使用。

创始人：约翰·格鲁伯（英语：John Gruber)

优点：轻量，学习成本低

<!-- more -->

以下的是markdown一些较为日常的语法

#### Ⅰ、标题
```
# 一级标题 
## 二级标题  
### 三级标题
```
四五六七级标题以此类推

#### Ⅱ、列表
**无序列表**
```
* 列表1 
* 列表2
* 列表3
```
* 列表1
* 列表2
* 列表3

**有序列表**
```
1. 列表1
2. 列表2
3. 列表3
```
1. 列表1
2. 列表2
3. 列表3

#### Ⅲ、连接
```
[Google](https://www.google.com)
```
[Google](https://www.google.com)

**带 title （鼠标悬停在连接上会显示title内容）**
```
[Google](https://www.google.com "一个不存在的网站")
```
[Google](https://www.google.com "一个不存在的网站")

#### Ⅳ、图片
```
![](https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png
```
![](https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png)

**带title（鼠标悬停在连接上会显示title内容）**

```
![alt](https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png "markdown")
```
![alt](https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png "markdown")


**对图片的引用**

```
![alt][img1]

[img1]: https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png "markdown"
```
![alt][img1]

[img1]: https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png "markdown"


#### Ⅴ、文本的引用
**单行引用**

```
> 澳门首家线上赌场，性感荷官在线发牌
```
>澳门首家线上赌场，性感荷官在线发牌

**多行引用**

```
>**赴戍登程口占示家人**
>力微任重久神疲，再竭衰庸定不支。
>苟利国家生死以，岂因祸福避趋之？
>谪居正是君恩厚，养拙刚于戍卒宜。
>戏与山妻谈故事，试吟断送老头皮。
```
>**赴戍登程口占示家人**
>力微任重久神疲，再竭衰庸定不支。
>苟利国家生死以，岂因祸福避趋之？
>谪居正是君恩厚，养拙刚于戍卒宜。
>戏与山妻谈故事，试吟断送老头皮。

#### Ⅵ、文字修饰
```
**粗体**
```
**粗体**

```
*斜体*
```
*斜体*

```
***又粗又斜***
```
***又粗又斜***

```
~~真正的粉丝~~
```
~~真正的粉丝~~

#### Ⅶ、表格
每个表头都要以至少三个破折号+直线分隔开来，默认靠左排列。
冒号标注的位置可以用来设置排列的方位。


```
| 表头1 | 表头2 | 表头3 |
|-------|:-----:|------:|
| 靠左1   |  居中1  |   靠右1 |
| 靠左2   |  居中2  |   靠右2 |
| 靠左3   |  居中3  |   靠右3 |
```
| 表头1 | 表头2 | 表头3 |
|-------|:-----:|------:|
| 靠左1   |  居中1  |   靠右1 |
| 靠左2   |  居中2  |   靠右2 |
| 靠左3   |  居中3  |   靠右3 |
**表格里也可使用基础Markdown语法**

```
|  功能  |    效果    | Markdown语法 |
|:------:|:----------:|:------------:|
|  粗体  |  **粗体**  |  `**粗体**`  |
|  斜体  |   *斜体*   |   `*斜体*`   |
| 删除线 | ~~删除线~~ | `~~删除线~~` |
```
|  功能  |    效果    | Markdown语法 |
|:------:|:----------:|:------------:|
|  粗体  |  **粗体**  |  `**粗体**`  |
|  斜体  |   *斜体*   |   `*斜体*`   |
| 删除线 | ~~删除线~~ | `~~删除线~~` |
#### Ⅷ、代码引用
**单行代码引用**
```
`system.out.print("hello world");`
```
`system.out.print("hello world");`

**多行代码引用**
```
    ```java

    void test(){
        String str = "hello world";
        system.out.print(str);
    }
    ```
```

```java
void test(){
    String str = "hello world";
    system.out.print(str);
}
```

---
到这里日常常被使用到的markdown的语法已经基本介绍完了。
关于markdown的使用，我是用 VS Code 进行日常编辑的，而线上编辑器我也只用过 马克飞象。都是非常好用的编辑工具，网上还有非常多适用markdown的编辑工具，因为没用过就不瞎推荐了。