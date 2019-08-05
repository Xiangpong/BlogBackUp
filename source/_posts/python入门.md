---
title: Python基础入门
date: 2019-3-26 13:12:19
tags:
- 笔记
- 分享
categories:  学习笔记 
---

## 1.变量及数据类型
#### 1.1 数据类型
python标准数据类型：
* Numbers 数值
* String 字符串
* List 列表
* Tuple 元组
* Dict 字典

<!-- more -->

Demo01:
```python
# Numbers数值分为：
# int整型、long长整型、float浮点型、complex复数

x1 = 10
x2 = 9.99

print(x1, x2)
print(type(x1), type(x2))

# print() 输出/打印内容
# type() 查看数据类型


运行结果：


10 9.99
<class 'int'> <class 'float'>

```

Demo02:
```python
#String字符串

x3 = "hello world"
print(x3, type(x3))
print("python No.1")
print('''python,不值得.jpg''')

# 一定用英文标点符号，单引号('') 双引号("")一样，三引号(''''''或"""""")可以表示多行字符串

运行结果：


hello world <class 'str'>
python No.1
python,不值得.jpg

```

Demo03:
```python
# boolean布尔型：True,False 用于判断
x4 = True
print(x4, type(x4))
print(True == 1)
print(False == 0)
print(True * 10)

# True实际值是1，False实际值是0

运行结果：


True <class 'bool'>
True
True
10

```

Demo04:

```python
# List列表
x5 = [777, "a", "abc", 9.9, [1, 2, 3]]
print(x5, type(x5))

运行结果：


[777, 'a', 'abc', 9.9, [1, 2, 3]] <class 'list'>

```

Demo05:

```python
# Tuple元组，用（）标识，不能二次赋值，可以理解成不可变的列表
x6 = (1, 2, 3, "python")
print(x6, type(x6))

运行结果：


(1, 2, 3, 'python') <class 'tuple'>

```

Demo06:

```python
# Dict字典，用{}标识，由索引（key）和他对应的值value组成，无序对象
x7 = {"name": "pong", "city": "chaozhou", "age": 18}
print(x7, type(x7))

运行结果：


{'name': 'pong', 'city': 'chaozhou', 'age': 18} <class 'dict'>

```

Demo07:

```python
# 数据类型转换方法
# int float str
var1 = 10.8
var2 = int(var1)
var3 = round(var1)
print(var1, type(var1))
print(var2, type(var2))
print(var3, type(var3))
print('--------------')
# int(x)函数，将x转为整数
# round(x)函数，四舍五入

var4 = 10
var5 = float(var4)
print(var4, type(var4))
print(var5, type(var5))
print('--------------')
# float(x)函数，将x转为浮点数

var6 = 10
var7 = str(var6)
var8 = float(var7)
print(var6, type(var6))
print(var7, type(var7))
print(var8, type(var8))
print('--------------')
# str()函数，将x转为字符串


运行结果：


10.8 <class 'float'>
10 <class 'int'>
11 <class 'int'>
--------------
10 <class 'int'>
10.0 <class 'float'>
--------------
10 <class 'int'>
10 <class 'str'>
10.0 <class 'float'>
--------------

```

#### 1.2 什么是变量

number = 100  number就是一个变量

变量的命名：
1. 变量名第一个字符必须是字母（无规定大小写）或者下划线“_”，不能数字
2. 变量名不能和常用功能性名字重合，如if，while，for
3. 不要有空格

Demo08：

```python
# 变量的赋值
count = 100
miles = 99.99
name = "pong"
print(count, miles, name)

运行结果：


100 99.99 pong

```

Demo09:

```python
# 多变量赋值
a = b = c = 8848
d, e, f = 100, 88.88, "py"
print(a, b, c, d, e, f)

运行结果：


8848 8848 8848 100 88.88 py

```

Demo10:

```python
# 动态变量 变量的值是可以改变的
var1 = 10
print(var1)
var1 = 9
print(var1)

运行结果：


10
9

```

#### 1.3 运算符

Demo11：

```python

# 算数运算符
a, b, c = 9, 3, 6

a = b + c  # 加法
print("b+c=", a)

c = a - b  # 减法
print("a-b=", c)

a = b * b  # 乘法
print("b*b=", a)

b = a / b  # 除法
print("a/b=", b)

b = a % c  # 取模 返回余数
print("a%c=", b)

a = b**2  # 幂
print("b的2次方=", a)

b = a // c  # 取整除数
print("9除6的整除数=", b)

运行结果：


b+c= 9
a-b= 6
b*b= 9
a/b= 3.0
a%c= 3
b的2次方= 9
9除6的整除数= 1

```

Demo12:

```python
# 比较运算符

a, b = 21, 10
print(a == b)  # 等于
print(a != b)  # 不等于
print(a > b)  # 大于
print(a < b)  # 小于
print(a >= 21)  # 大于等于
print(a <= 2)  # 小于等于

运行结果：


False
True
True
False
True
False

```

Demo13:
```python
# 逻辑运算符
print(True and False)  # and = 且
print(True or False)  # or = 或
print(not True)  # not = 非

# 布尔型的本质： True = 1 False = 0;
print(True > 0)
print("-----------")

print(bool(0), bool(3), bool(-1), bool([1, 2, 3]))
# bool()函数，将值转为布尔型，其中只有以下情况返回False：0 ， 0.0， None ，[] ，{}


运行结果：


False
True
False
True
-----------
False True True True

```

Demo14:

```python

# 成员运算符

lst = [1, 2, 3, 4, 5, 6]
a, b = 1, 10
print(a in lst)  # a在lst序列中，如果x在y序列中则返回True
print(b not in lst)  # b不在lst序列中，如果x不在y序列中则返回True


运行结果：


True
True

```

## 2.序列及通用操作
#### 2.1 序列通用操作
序列分类：
* 可变序列list
* 不可变序列tuple、str

Demo15:

```python

# 判断值是否属于序列

lst = [1, 2, 3, 4, 5, 6]
a, b = 1, 10
print(a in lst)  # a在lst序列中，如果x在y序列中则返回True
print(b not in lst)  # b不在lst序列中，如果x不在y序列中则返回True

运行结果：


True
True

```
Demo16：

```python

# 序列链接与重复
lst1 = [1, 2, 3]
lst2 = ['a', 'c', 'd']

print(lst1+lst2)  # "+" 序列链接
print(lst1*3, lst2*2)  # “*” 序列重复

运行结果：


[1, 2, 3, 'a', 'c', 'd']
[1, 2, 3, 1, 2, 3, 1, 2, 3] ['a', 'c', 'd', 'a', 'c', 'd']
```

Demo17:

```python
# 下标索引

lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
print(lst[0], lst[5], lst[9])  # 索引从0开始
print(lst[-1])  # 索引-1代表最后一个值

运行结果：

1 3 0
0
```

Demo18:

```python
# 切片

lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
print(lst[2:5])  # 切片可以理解成列表的值区间，且是一个左闭区右开区间，lst[2：5]代表区间是：索引是2的值-索引4的值
print(lst[::5])  # 左边无索引，代表从索引0开始
print(lst[4:])  # 右边无索引，代表最后一个值结束
print(lst[5:-1])  # 索引5的值 - 倒数第二个值（切片是右闭区间，注意了）

运行结果：

[3, 4, 5]
[1, 6]
[5, 6, 7, 8, 9, 0]
[6, 7, 8, 9]

```

Demo19:

```python
# 步长

lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
print(lst[0:5:2])  # list[i:j:n]代表，索引i -索引j，以n为步长
print(lst[::2])  # 按照2为步长，从第一个值开始截取list数据
print(lst[1::2])  # 按照2为步长，从第二个值开始截取list数据

运行结果：

[1, 3, 5]
[1, 3, 5, 7, 9]
[2, 4, 6, 8, 0]

```

Demo20:

```python
# 序列的基本内置全局函数

lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
print(len(lst))  # 序列的个数
print(max(lst), min(lst), sum(lst))
# 返回序列的最大值，最小值，所有元素求和
print(lst.index(3))  # index(obj)方法，从列表中找出某个第一匹配项的索引位置

lst = [1, 1, 1, 2, 3, 4, 5, 5, 5, 5]
print(lst.count(5))  # .count(obj)方法，计算指定值出现次数

运行结果：

10
9 0 45
2
4
```

#### 2.2 列表list常用操作
* 序列是python中最基本的数据结构，支持字符、数字、字符串、甚至可以包含列表
* 列表用[]标识
* 列表中值的切片可以用变量[头下标:尾下标]截取相应列表，从左到右默认索引0开始，从右到左默认索引-1开始，下标可以为空表示取头或取尾
* “ + ”是链接，“ * ”是重复

Demo21:

```python
# 列表的特征
lst = [1, 2, 3, 'a', 'b', 'c', [1, 2, 3]]
# 可以包含数字、字符、列表(即可以嵌套)
print(lst)

print(lst[0], lst[4], lst[-1])
# 可以通过下标访问列表对应的数据元素

lst = [1, 2, 3]
lst = lst * 3
print(lst)
# 可以变换列表长度

lst[0] = 100
print(lst)
# 可以替换指定下标的数据元素

运行结果：

[1, 2, 3, 'a', 'b', 'c', [1, 2, 3]]
1 b [1, 2, 3]
[1, 2, 3, 1, 2, 3, 1, 2, 3]
[100, 2, 3, 1, 2, 3, 1, 2, 3]

```

Demo22:

```python
# 列表与生成器

print(range(5), type(range(5)))
# range()是生成器，指定一个范围
# range(5)代表指定范围为0、1、2、3、4
# range(2, 5)代表指定范围2、3、4
# range(0, 10, 2)代表指定范围为0、2、4、6、8；最后的2代表步长

lst = list(range(5))
print(lst)
# 通过list()函数生成列表

运行结果：

range(0, 5) <class 'range'>
[0, 1, 2, 3, 4]

```

Demo23:

```python
# 可变列表list常用操作 -- 添加元素

lst = list(range(10))
lst.append("python")
print(lst)
# list.append() 添加元素

lst.append(['a', 'b', 'c'])
print(lst)

lst.extend(['a', 'b', 'c'])
print(lst)
# 一次添加多个元素 .extend()；可用来扩展列表

运行结果：

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 'python']
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 'python', ['a', 'b', 'c']]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 'python', ['a', 'b', 'c'], 'a', 'b', 'c']

```

Demo24:

```python
# 可变列表list常用操作 -- 删除元素

lst = ['Jerry', 'Jerry', 'Tom', 'Jack', 'Curry', 'May', 'Tom']
lst.remove('Tom')
print(lst)
# .remove() 删除列表中第一个匹配元素

del lst[3:5]
print(lst)
# del语句，删除列表中相对应索引的值

lst.clear()
print(lst)
# .clear() 移除所有

运行结果：

['Jerry', 'Jerry', 'Jack', 'Curry', 'May', 'Tom']
['Jerry', 'Jerry', 'Jack', 'Tom']
[]

```

Demo25:

```python
# 可变列表list常用操作 -- 插入元素

lst = list(range(10))
print(lst)

lst.insert(3, 'a')
print(lst)
# .insert(i, x) 在索引为i处插入x

lst.insert(5, [1, 2, 3])
print(lst)
# 可以插入一个列表

运行结果：

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[0, 1, 2, 'a', 3, 4, 5, 6, 7, 8, 9]
[0, 1, 2, 'a', 3, [1, 2, 3], 4, 5, 6, 7, 8, 9]

```

Demo26:

```python
# 可变列表list常用操作 -- 复制

lst = list(range(10))
lst1 = lst
lst1[2] = 'python'
print(lst)
print(lst1)
# lst,lst1指向同一个列表

lst = list(range(10))
lst2 = lst.copy()
lst2[2] = 'python'
print(lst)
print(lst2)
# .copy() 复制列表，lst，lst2指向不同列表

运行结果:

[0, 1, 'python', 3, 4, 5, 6, 7, 8, 9]
[0, 1, 'python', 3, 4, 5, 6, 7, 8, 9]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[0, 1, 'python', 3, 4, 5, 6, 7, 8, 9]

```

Demo27:

```python
# 可变列表list常用操作 -- 排序

lst1 = [2, 8, 55, 5, 44, 128]
lst2 = ['x', 'a', 'e', 'c', 'g']

lst1.sort()
lst2.sort()
print(lst1)
print(lst2)
# .sort() 实现排序，默认升序

lst1.sort(reverse=True)
lst2.sort(reverse=True)
print(lst1)
print(lst2)
# 参数reverse = True  反向排序

lst3 = sorted(lst1)
lst3.append('python')
print(lst3)
# sorted(): 排序并复制

运行结果：

[2, 5, 8, 44, 55, 128]
['a', 'c', 'e', 'g', 'x']
[128, 55, 44, 8, 5, 2]
['x', 'g', 'e', 'c', 'a']
[2, 5, 8, 44, 55, 128, 'python']

```

Demo28:

```python
# 元组 - 不可变的列表

tup1 = ('Chinese', 'English', 18, 1997)
tup2 = (1, 2, 3, 4, 5)
tup3 = 'a', 's', 'd', 'f'  # 可以不加括号
tup4 = (11, )  # 元组只有一个元素时，需要在元素后面添加逗号

print(tup1[0], tup3[::2])
# 索引和切片操作和list一致

del tup3  # 因为元组内容不可变，所以只能用del语句整个删除

print(len(tup1))
print(tup1+tup2)
print(tup4*3)
print(max(tup2), min(tup2))
# 操作与list一致

print("------------------------")
lst = list(range(10))
print(lst)
tup5 = tuple(lst)
print(tup5)
# tuple() 将列表转换为元组

运行结果：

Chinese ('a', 'd')
4
('Chinese', 'English', 18, 1997, 1, 2, 3, 4, 5)
(11, 11, 11)
5 1
------------------------
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)

```

#### 2.3 文本序列str常用操作
* 字符串也是python常用的数据类型
* 字符串也是序列（文本序列）

Demo29:
```python
# 字符串的引号

str1 = "abc"
str2 = 'abc'
str3 = 'my name is "pong"'
# 双引号，单引号无区别，但文本中有引号时要相互交替使用

str4 = '''苟利国家生死以，
            岂因祸福避趋之。'''
# 需要多行字符时，用三引号'''


print(str1)
print(str2)
print(str3)
print(str4)

运行结果：

abc
abc
my name is "pong"
苟利国家生死以，
            岂因祸福避趋之。

```

Demo30:
```python
# 转义字符 \
print('\'', "\"")  # 输出单引号，双引号
print("hello\nworld")  # \n 空行
print('\\')  # 输出\

运行结果：

' "
hello
world
\

```

Demo31:
```python
# 序列通用功能
print('a' in 'abc')  # in/not in 判断指定字符是否存在
print('hello '+'world')  # 文本链接
print('python '*4)  # 文本复制

str = 'asdfghjkl'
print(str[0], str[-1])
print(str[:2])
print(str[2:5:2])
# 索引 切片 步长

print(str.index('g'))  # .index()查找指定元素下标
print(len(str))  # 计算字符串长度

运行结果：

True
hello world
python python python python 
a l
as
dg
4
9

```

Demo32：
```python
# 字符串常用功能

str1 = "hello world"
str2 = str1.replace('world', 'python')
print(str1)
print(str2)
str3 = "hahaha"
str4 = str3.replace('ha', 'he', 2)
print(str4)
# .replace(old, new, count) 修改字符串，count：要更换几个

str5 = 'asdfghjkl'
print(str5.startswith('a'), str5.endswith('k'))
# .startswitch("str") 判断是否以“str”开头；.endswitch("str") 判断是否以“str”结尾

str6 = 'AsdFGHjkl'
print(str6.upper())  # 全部大写 .upper()
print(str6.lower())  # 全部小写 .lower()
print(str6.swapcase())  # 字符串中大小写互换 .swapcase()
print(str6.capitalize())  # 首字符大写 .capitalize()

str7 = '123456789'
print(str7.isnumeric())  # 如果字符串全是数字，返回True .isnumeric()

str8 = "QWER"
print(str8.isalpha())  # 如果字符串全是字母返回True .isalpha()

str9 = 'lalala    '
print(str9.rstrip())  # 删除字符末尾空格

运行结果：

hello world
hello python
heheha
True False
ASDFGHJKL
asdfghjkl
aSDfghJKL
Asdfghjkl
True
True
lalala

```

Demo33:
```python
# 格式化字符：在字符串中插入变量

name = 'pong'
truth = '%s is 好人' % name
print(truth)
# %S 表示插入一个变量（字符串）， %name 表示插入name

x = 4
y = "lalala"
z = 4.2
print("this is %i" % x)
print("this is %s" % y)
print("this is %f" % z)
# %i %s %f 都是格式化字符串 分别代表插入一个整数，字符串，浮点数

运行结果：

pong is 好人
this is 4
this is lalala
this is 4.200000

```

Demo34:
```python
# 格式化字符串中，多数字格式化的细节

π = 3.1415926
print("pi is %f" % π)
print("pi is %.2f" % π)  # 输出两位小数 %.2f (存在四舍五入)

n = 10.8
print("n is %i" % n)
print("n is %.0f" % n)
# %i 与 %.0f 的区别在于前者没有四舍五入，而是直接取整

m = 100
print('m is %+i' % m)
print('m is %.2f' % -0.01)
# 显示正号，负号根据数字直接显示

x = 100
print('x is % i' % x)
print('x is % +i' % x)
print('x is % .2f' % -0.01)
# 加空格，空格和+只能显示一个

y = 123.123321231
print('y is %.2e' % y)
print('y is %.4E' % y)
# 科学计算法 %e %E

z1 = 123.321123231
z2 = 3.2
print("z1 is %g" % z1)
print("z2 is %g" % z2)
# 小数位数少的时候自动识别用浮点数，数据复杂的时候自动识别用科学计数法

运行结果：

pi is 3.141593
pi is 3.14
n is 10
n is 11
m is +100
m is -0.01
x is  100
x is +100
x is -0.01
y is 1.23e+02
y is 1.2312E+02
z1 is 123.321
z2 is 3.2

```

Demo35:
```python
# 强大的格式化方法 .format()
print('user id: {0}'.format("root"))
print("{} 喜欢 {}".format('a', 'b'))
# {} 这里代表占位符，其中可以有值也可没有

print('{}{}{}'.format('a', 'b', 'c'), '\n',
      "{0}{1}{2}{0}".format('a', 'b', 'c'))
# {}和{0}的区别:都是占位符，后者有了明确指定

print('我的工作是{work}'.format(work='程序员'))
# 可以用变量来表示

x = "abc{}"
a = x.format("def")
print(a, x)
# .format()可以生成新值

print("{:f}".format(4.1232))
print("{:.2f}".format(4.1231))
print("{:e}".format(4.1233))
print("{:.0f}".format(4.789))
print("{:%}".format(4.522))
print("{:d}".format(55))

运行结果：

user id: root
a 喜欢 b
abc 
 abca
我的工作是程序员
abcdef abc{}
4.123200
4.12
4.123300e+00
5
452.200000%
55

```

Demo36:
```python
x = 'a b c'
print(x.split())

y = x.split()
print('+'.join(y))

运行结果:

['a', 'b', 'c']
a+b+c

```

## 3.字典映射
#### 3.1 字典dict基本概念
* 字典是一种可变容器模型，可以储存任意类型对象
* 字典的每个键值对（key ：value）用冒号“ ：” 分割，每个对之间用逗号分割，整个字典包含在“ {} ”中
* 键唯一，值不唯一

Demo37：
```python
# 什么是映射，什么是字典dict
name = ['Jerry', 'Tom', 'pong']
age = [19, 20, 21]
# 上面定义了两个序列，姓名和年龄。日常生活我们有把姓名和年龄挂钩的操作。
# 但序列虽然有顺序，且不能把姓名和年龄联系起来，不存在一对一的数据逻辑关系

dic = {'Jerry': 19, 'Tom': 20, 'pong': 21}
print(dic, type(dic))
# 用{}来表示，按key：value来表示字典中的元素

dic = [{'name': 'Jerry', 'age': 19}, {'name': 'Tom', 'age': 20}, {'name': 'pong', 'age': 21}]
print(dic)
# 一个以字典为元素的列表

运行结果:

{'Jerry': 19, 'Tom': 20, 'pong': 21} <class 'dict'>
[{'name': 'Jerry', 'age': 19}, {'name': 'Tom', 'age': 20}, {'name': 'pong', 'age': 21}]

```

Demo38:
```python
# 字典的特点

dic = {'a': 1, 'b': 2, 'c': 3}
# 键值对都是同时出现的

dic = {'a': 1, 'a': 2}
print(dic)
# 不允许同一键对应不同的值，如果一个键被赋值两次，后一个赋值被承认

dic = {'var1': 1, 'var2': 'python', 'var3': [1, 2, 3], 'var4': {"a": 1, "b": 2}}
print(dic)
# key必须是字符串，value则可以任意对象

# 字典是一个无序集合，序列是有序的

dic['var5'] = '任意添加一个值'  # 任意添加一个值
dic['var4'] = '任意修改其中一个值'  # 任意修改其中一个值
del dic['var1']  # 任意删除元素
print(dic)

dic.clear()  # 清空词典
print(dic)

del dic  # 删除词典

运行结果：

{'a': 2}
{'var1': 1, 'var2': 'python', 'var3': [1, 2, 3], 'var4': {'a': 1, 'b': 2}}
{'var2': 'python', 'var3': [1, 2, 3], 'var4': '任意修改其中一个值', 'var5': '任意添加一个值'}
{}

```

Demo39:
```python
# 申明一个词典的两种方法

dic = {'a': 1, 'b': 2, 'c': 3}
print(dic)
dic = dict(x=1, y='hello', z=[1, 2, 3])
print(dic)

lst1 = [('a', '000'), ('b', '111')]
lst2 = [['c', 1], ['d', 2]]
lst3 = (('e', [1, 2]), ('f', [3, 4]))
dic1 = dict(lst1)
dic2 = dict(lst2)
dic3 = dict(lst3)
print(dic1)
print(dic2)
print(dic3)
# dict() 由序列生成一个字典，可以是list 或 tuple

keys = ['a', 'b', 'c']
dic4 = dict.fromkeys(keys)
dic5 = dict.fromkeys(keys, "lala")
print(dic4)
print(dic5)
# 只有key能直接生成一个字典

运行结果：

{'a': 1, 'b': 2, 'c': 3}
{'x': 1, 'y': 'hello', 'z': [1, 2, 3]}
{'a': '000', 'b': '111'}
{'c': 1, 'd': 2}
{'e': [1, 2], 'f': [3, 4]}
{'a': None, 'b': None, 'c': None}
{'a': 'lala', 'b': 'lala', 'c': 'lala'}

```

#### 3.2 字典的常用操作

Demo40：
```python
# 字典常用操作

dic1 = {'a': 1, 'b': 2, 'c': 3}
dic2 = {'d': 4, 'e': 5}
dic1.update(dic2)
print(dic1)
print(dic2)
# .update() 更新/合并一个字典，把第二个字典合并到第一个

dic1 = {'a': 1, 'b': 2, 'c': 3}
dic2 = dic1
dic1.update({"来了": "老弟"})
print(dic1)
print(dic2)
# 和序列的原理一样，dic1 和 dic2 都指向同一个字典

dic1 = {'a': 1, 'b': 2, 'c': 3}
dic2 = dic1.copy()
dic1.update({"来了": "老弟"})
print(dic1)
print(dic2)
# .copy() 复制一个新字典

print(len(dic1))  #查看字典元素个数
print('f' in dic1)
print('a' in dic1)
# 适用 in/not in 这里的判断对象是key

运行结果：

{'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}
{'d': 4, 'e': 5}
{'a': 1, 'b': 2, 'c': 3, '来了': '老弟'}
{'a': 1, 'b': 2, 'c': 3, '来了': '老弟'}
{'a': 1, 'b': 2, 'c': 3, '来了': '老弟'}
{'a': 1, 'b': 2, 'c': 3}
4
False
True

```

#### 3.3 字典的元素访问及遍历

Demo41：
```python
# 字典元素的访问

dic1 = {'a': 1, 'b': 2, 'c': 3}
print(dic1['a'])
# 通过key来指向对应元素

poi = {'name': 'pong', 'city': '佛山', 'information': {'address': 'somewhere', 'num': 777777}}
print(poi['information']['address'])
# 对于嵌套字典，输出嵌套内容，通过重复指向来输出

print(poi.get('name'))
print(poi.get('type', print('nothing')))
# .get(key)方法，直接查看key指定的value，如果没有相应的key，则返回None，添加一个prin参数可以多返回一个值


print(poi.values(), type(poi.values()))
print(list(poi.values()))
# .values() 输出字典所有value
print(poi.keys(), type(poi.keys()))
print(list(poi.keys()))
# .keys() 输出字典所有key

运行结果：

1
somewhere
pong
nothing
None
dict_values(['pong', '佛山', {'address': 'somewhere', 'num': 777777}]) <class 'dict_values'>
['pong', '佛山', {'address': 'somewhere', 'num': 777777}]
dict_keys(['name', 'city', 'information']) <class 'dict_keys'>
['name', 'city', 'information']

```

Demo42:
```python
# 字典元素遍历

dic = {'name': 'pong', 'city': '佛山', 'information': {'address': 'somewhere', 'num': 777777}}
for key in dic.keys():
    print(key)
print("----------------")

for value in dic.values():
    print(value)
print("----------------")

for (k, v) in dic.items():
    print('key= %s, value= %s' % (k, v))

运行结果：

name
city
information
----------------
pong
佛山
{'address': 'somewhere', 'num': 777777}
----------------
key= name, value= pong
key= city, value= 佛山
key= information, value= {'address': 'somewhere', 'num': 777777}

```

## 4.条件循环语句
#### 4.1 条件判断：if语句
python条件语句是通过一条或者多条语句的执行结果（True or False）来决定执行的代码块

if 判断条件：
      执行语句
      else：
      执行语句


Demo43：
```python
# 基本判断语句if

age = 12
if age < 18:
    print("未成年人不得进入！")
# if语句后面必须有 ： 
# 自动缩进
# if语句写完后，要退回原有缩进继续写
# Python代码的缩进规则：具有相同缩进的代码被视为代码块

运行结果：

未成年人不得进入！

```

Demo44:
```python
# 输入函数 input()

score = input("请输入成绩：")
print('该学生成绩为：'+score)
print(type(score))
# 可见input返回的是字符串

运行结果：

请输入成绩：66
该学生成绩为：66
<class 'str'>

```

Demo45：
```python 
# if - else

name = 'pong'
if name == 'pong':
    print("hello world")
else:
    print("Who are you？")

运行结果：

hello world

```

Demo46:
```python
# if - elif - else

num = 10
if num == 5:
    print("if")
elif num == 10:
    print("elif")
else:
    print("else")

运行结果：

elif

```

#### 4.2 循环语句：for循环

Demo47：
```python
for i in range(5):
    print('hello world')

运行结果：

hello world
hello world
hello world
hello world
hello world

```

Demo48:
```python
# 通过for循环遍历序列

lst = list(range(10))
for i in lst[::2]:
    print(i)
print("-------------------")


age = {'Tom': 18, 'Jerry': 19, 'pong': 22, 'Mary': 15}
for name in age:
    print(name+'年龄为：%s' % age[name])

运行结果：

0
2
4
6
8
-------------------
Tom年龄为：18
Jerry年龄为：19
pong年龄为：22
Mary年龄为：15

```

Demo49：
```python
# 嵌套循环
for i in range(3):
    for j in range(2):
        print(i, j)

运行结果：

0 0
0 1
1 0
1 1
2 0
2 1

```

#### 4.3 循环语句：while

Demo50：
```python
# 循环语句while
count = 0
while count<9:
    print(count)
    count+=1
print("end")

运行结果：

0
1
2
3
4
5
6
7
8
end

```

关于无限循环：如果条件判断语句永远为 true，循环将会无限的执行下去

Demo51:

```python
var = 1
while var == 1 :  
     num = input("Enter a number  :")
     print( "You entered: ", num)
 print( "Good bye!")

# 该条件永远为true，循环将无限执行下去
# 一定要避免无限循环！！
```

Demo52:
```python
# while - else 语句
count = 0
while count<5:
    print(count,'小于5')
    count+=1
else:
    print(count,'大于等于5')

运行结果：

0 小于5
1 小于5
2 小于5
3 小于5
4 小于5
5 大于等于5

```

#### 4.4 循环控制语句
* break 在语句执行过程中终止并跳出循环
* continue 在语句执行过程中跳出该次循环，执行下一次循环
* pass pass是空语句，保持程序结构的完整

Demo53:
```python
# break
x = 0
y = 1
while y > 0:
    x = x + y
    y = y + 1
    if y == 5:
        break
print(x)
# break语句用来终止循环，即是循环条件没有达成也被终止

s = 0
for i in range(5):
    for j in range(5):
        s = s + (i*j)
        print('i=', i, 'j=', j, 's=', s)
        if s > 10:
            break
print('结果为%i' % s)
# 如果使用嵌套循环，break语句将停止执行最深层的循环，并开始执行下一行代码。
# break跳出的是它所在的那个循环！

运行结果：

10
i= 0 j= 0 s= 0
i= 0 j= 1 s= 0
i= 0 j= 2 s= 0
i= 0 j= 3 s= 0
i= 0 j= 4 s= 0
i= 1 j= 0 s= 0
i= 1 j= 1 s= 1
i= 1 j= 2 s= 3
i= 1 j= 3 s= 6
i= 1 j= 4 s= 10
i= 2 j= 0 s= 10
i= 2 j= 1 s= 12
i= 3 j= 0 s= 12
i= 4 j= 0 s= 12
结果为12

```

Demo54:
```python
# continue语句
s = 0
for i in range(10):
    if i % 2 == 0:
        s += i
    else:
        continue
    print(i)
print(s)
# continue 语句用来告诉Python跳过当前循环的剩余语句，然后继续进行下一轮循环。

运行结果：

0
2
4
6
8
20

```

pass 没用过，不知道这玩意儿有什么用

Demo55:
```python
# pass语句

for letter in 'Python':
    if letter == 'h':
        pass
        print('当前字母 : h，但是我pass了')
    print('当前字母 :', letter)
print("Good bye!")
# pass是空语句，是为了保持程序结构的完整性。（不中断也不跳过）

运行结果：

当前字母 : P
当前字母 : y
当前字母 : t
当前字母 : h，但是我pass了
当前字母 : h
当前字母 : o
当前字母 : n
Good bye!

```

## 5.函数
#### 5.1 自定义函数

Demo56：
```python
# 定义函数

def f(x):
    if x<5:
        print("输入值小于5")
    else:
        print("输入值大于5")
#运行函数
f(10)

运行结果：

输入值大于5

```

Demo57:
```python
# return
def f1(x):
    y = 2**x
    # 没有return

def f2(x):
    y = 2**x
    return y

print(f1(2), f2(2))
# return语句退出函数，并返回一个表达式。不带参数值的return语句返回None

None 4

```

Demo58:
```python
# 默认参数
def f(x, n=2):
    return (x**n)
print(f(10))
print(f(5,3))
# n = 2,这里n的默认值为2，如果不输入则以默认值为主

运行结果:

100
125

```

Demo59:
```python
# 可变参数
def f(*x):
    print(x)
    return x
f(1)
f('a', 'c')
f(1, 2, 3, [6, 6, 6])
print(type(f('a', 'c')))

# 通过*来定义可变参数
# 默认会把可变参数传入一个元祖！

运行结果：

(1,)
('a', 'c')
(1, 2, 3, [6, 6, 6])
('a', 'c')
<class 'tuple'>

```

#### 5.2 局部变量及全局变量
* 定义在函数内部的变量拥有一个局部作用域，定义在函数外部的变量拥有全局作用域
* 局部变量只能在其被声明的函数内部访问，而全局变量在整个程序范围都可被访问。

Demo60：
```python
def f(s):
    s = '啦啦啦'  # 函数作用：把输入变量指向“呵呵哒”
    print('函数内为局部变量：%s' % s)

a = input("请输入一个数字：")
f(a)
print("函数外为全局变量： %s" % a)

运行结果：

请输入一个数字：5
函数内为局部变量：啦啦啦
函数外为全局变量： 5

```

#### 5.3 匿名函数Lambda
* lambda 语句创建匿名函数

Demo61：
```python
def fun(a, b, c):
    return a+b+c
print(fun(2, 3, 4))
# def 创建自定义函数用于求和

f = lambda a, b, c: a+b+c
print(f(2, 3, 4))
# lambda作为匿名函数，不需要函数名→ 需要一个函数，又不想动脑筋去想名字，这就是匿名函数
# lambda的主体是一个表达式，而不是一个代码块。
# lambda只有一行，仅仅能在lambda表达式中封装有限的逻辑进去。

运行代码：

9
9

```

## 6.模块与包
#### 6.1 模块创建及import指令运用
* python 模块（Module）是一个python 文件，以.py 结尾，包含了python对象定义和python语句

Demo62：
```python
# 创建一个模块，包含一个阶乘函数f1(n),一个列表删值函数f2(lst)
def f1(n):
    y = 1
    for i in range(1,n+1):
        y = y * i
    return y
# 创建阶乘函数f1(n)

def f2(lst,x):
    while x in lst:
        lst.remove(x)
    return lst
# 创建列表删值函数f2(lst,x)

def f3(a,d,n):
    an = a
    s = 0
    for i in range(n-1):
        an = an + d
        s = s + an
    return s
# 创建等差数列求和函数f3(a,d,n)
# 创建模块testmodel2，包括三个函数

```

Demo63:
```python
# 模块路径问题

import testmodel2
print(testmodel2.__file__)
# 查看现有包所再路径

```

Demo64:
```python
# 调用模块import

import testmodel2
print(testmodel2.f1(5))
print(testmodel2.f2([2, 3, 4, 5, 5, 5, 6, 6, 4, 4, 4, 4], 4))
print(testmodel2.f3(10, 2, 10))
# 直接用import调用模块，.f1()调用模块函数（方法）

运行结果：

120
[2, 3, 5, 5, 5, 6, 6]
180

```

Demo65:
```python
# 简化模块名 import...as...

import testmodel2 as t2
print(t2.f2([2, 3, 4, 5, 5, 5, 6, 6, 4, 4, 4, 4], 4))

运行结构：

[2, 3, 5, 5, 5, 6, 6]

```

Demo66:
```python
# 调用部分模块语句，from...import
from testmodel2 import f2
print(f2([2, 3, 4, 5, 5, 5, 6, 6, 4, 4, 4, 4], 4))
# 单独导入模块的部分功能，但无法使用其他未导入模块功能

运行结果：

[2, 3, 5, 5, 5, 6, 6]

```

Demo67：
```python
# python的标准模块 - random随机数
import random
x = random.random()
y = random.random()
print(x, y*10)
# random.random() 随机生成一个[0:1)的随机数

m = random.randint(0, 10)
print(m)
# random.randint() 随机生成一个[0:10]的整数

str1 = random.choice(list(range(10)))
str2 = random.choice('asdfghjkl')
print(str1, str2)
# random.choice()随机获取()中的一个元素，()种必须是一个有序类型

lst = list(range(20))
sli = random.sample(lst, 5)
print(sli)
# random.sample(a,b)随机获取a中指定b长度的片段，不会改变原序列

lst = [1, 3, 5, 7, 9, 11, 13]
random.shuffle(lst)
print(lst)
# random.shuffle(list)将一个列表内的元素打乱

```

Demo68:
```python
# python标准模块 - time时间模块
import time
for i in range(2):
    print('hello')
    time.sleep(1)
# time.sleep(t) 程序休息t秒

print(time.ctime())
print(type(time.ctime()))
# 将当前时间转换为一个字符串

print(time.localtime())
print(type(time.localtime()))
# 将当前时间转为当前时区的struct_time
# wday 0-6表示周日到周六
# ydat 1-366 一年中的第几天
# isdst 是否为夏令时，默认为-1

print(time.strftime('%Y-%m-%d %H:%M:%S', time.localtime()))
# time.strftime(a,b)
# a为格式化字符串格式
# b为时间戳，一般用localtime()

运行结果：

hello
hello
Mon Mar 25 23:49:37 2019
<class 'str'>
time.struct_time(tm_year=2019, tm_mon=3, tm_mday=25, tm_hour=23, tm_min=49, tm_sec=37, tm_wday=0, tm_yday=84, tm_isdst=0)
<class 'time.struct_time'>
2019-03-25 23:49:37

```
%y 两位数的年份表示（00-99）

%Y 四位数的年份表示（000-9999）

%m 月份（01-12）

%d 月内中的一天（0-31）

%H 24小时制小时数（0-23）

%I 12小时制小时数（01-12）

%M 分钟数（00=59）

%S 秒（00-59）

%a 本地简化星期名称

%A 本地完整星期名称

%b 本地简化的月份名称

%B 本地完整的月份名称

%c 本地相应的日期表示和时间表示

%j 年内的一天（001-366）

%p 本地A.M.或P.M.的等价符

%U 一年中的星期数（00-53）星期天为星期的开始

%w 星期（0-6），星期天为星期的开始

%W 一年中的星期数（00-53）星期一为星期的开始

%x 本地相应的日期表示

%X 本地相应的时间表示

%Z 当前时区的名称

%% %号本身
