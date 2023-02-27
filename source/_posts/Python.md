---
title: Python
date: 2022-05-15 18:09:30
author: 殇夜
cover: true
coverImg: 
top: true
tags: Python 学习
categories: Python 学习
---
>学习Python的小白

<!--more-->
## 学习目标
{% markmap 300px %}
- 基础知识
  - 初识Python
       - 熟悉Python开发环境，并且学会编写HelloWord程序
  - Python语言基础
    - 掌握最基础语法，变量，数据类型，输入输出函数
  - 运算符与表达式
    - 掌握Python中的运算符和条件表达式的应用
  - 流程控制语句
    - 深入学习程序结构，控制语句的流程走向
  - 列表和元组
    - 掌握序列中的列表与元组的应用技能
  - 字典和集合
    - 掌握两种不重复且无序的数据结构字典和集合
  - 字符串
    - 深入学习字符串操作的相关知识

{%endmarkmap%}

## Python面试题精选
1 一行代码实现1--100之和( 利用sun()求和)
网上的答案是通过 range 生成 1 至 100 的整数，然后用 sum 求和：
``` Python
>>># 解法一
>>>sum(range(1,101))
5050
```
这行代码确实很有美感，但你想过没有：如果是求 1 至 10000000000 之和呢？候选人必须认识到这是一个 O(N) 算法，真的适合所有场景吗？为什么不用等差数列前 N 项和公式进行计算呢？
```
>>># 解法二
>>>n = 100
>>>(n+1) * n >>1
5050
```
采用前 N 项和公式，求和时间复杂度是 O(1) ，孰优孰劣应该很明显了吧。大家可以对比下当 N 很大时，这两种计算方式的表现：
```
>>> n = 100000000
>>> sum(range(1, n+1))
5000000050000000
>>> (n + 1) * n >> 1
5000000050000000
```
2 如何在一个函数内部修改全局变量
```` Python
a = 5
def fn():
    global a
    a = 4
fn()
print(a)
````
- 相关概念
    - 变量作用域 ( scope )
    - 局部名字空间 ( locals )
    - 闭包名字空间 ( globals )
    - 全局名字空间 ( enclosing )
    - 内建名字空间 ( builtin )
    
3 请描述执行以下程序将输出什么内容？并试着解释其中的原因？
``` Python
def add(n, l=[]):
    l.append(n)
    return l
print(add(1))
print(add(2))
print(add(3))
```
>输出log
```
[1]
[1, 2]
[1, 2, 3]
```

4 列出5个Python标准库
- [re](https://docs.python.org/3/library/re.html), 正则表达式处理
- [datetime](https://docs.python.org/3/library/datetime.html), 日期时间处理
- [json](https://docs.python.org/3/library/json.html), JSON数据处理
- [math](https://docs.python.org/3/library/math.html), 数学计算
- [random](https://docs.python.org/3/library/random.html), 随机数
- [os](https://docs.python.org/3/library/os.html), 系统调用
- [socket](https://docs.python.org/3/library/socket.html), 套接字编程与网络通讯
- [threading](https://docs.python.org/3/library/threading.html), 多线程处理
- [multiprocessing](https://docs.python.org/3/library/multiprocessing.html), 多进程处理
- [queue](https://docs.python.org/3/library/queue.html), 同步任务队列

5 字典如何删除键
方式一: 使用 del 语句进行删除， del 关键字还可用于删除 变量 、 属性 ：
```Python
>>>ages = {'tom' : 18, 'jim' : 20, 'lily' : 19}
>>>del ages['jim']
>>>ages
{'tom' : 18, 'lily' : 19} 
```
方法二 ，调用 pop 方法进行删除，这样可以拿到被删除键对应的值：
``` Python
>>>ages = {'tom' : 18, 'jim' : 20, 'lily' : 19}
>>>jims_age = ages.pop('jim')
>>>jims_age
20
>>>ages
{'tom' : 18, 'lily' : 19}
```
6 如何合并两个字典
``` Python
>>>info1 = {'name' : 'jim', 'age' : 18}
>>>info2 = {'name' : 'jim', 'score' : 95}
```
方法一 ，调用 dict 对象 update 方法：
```Python
>>>info1.update(info2)
>>>info
{'name' : 'jim', age : 18, 'socre' : 95}
```
方法二:
```
>>>info = {**info1, **info2}
>>>info
{'name' : 'jim', age : 18, 'socre' : 95}
```

7 Python 2 和 Python 3 中的 range(100) 的区别
Python 2 中的 range 函数返回一个列表，长度越大消耗内存越多：
````
>>>print(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
````
Python 2 中的 xrange 函数与 range 类似，但返回 生成器 ：
```
>>>r = xrange(10)
>>>ri = iter(r)
>>>next(ri)
0
>>>next(ri)
1
```
生成器内存消耗固定，与长度无关。因此，循环一般使用 xrange ：
```
for i in range(10000):
    pass
```
由于生成器比较高效， Python 3 的 range 函数也选择返回生成器，可以认为与 Python 2 中的 xrange 等价：

```
>>> r = range(10)
>>> ri = iter(r)
>>> next(ri)
0
>>> next(ri)
1
```
Python 3 中也可以实现与 Python 2 中的 range 函数一样的效果：
```
>>>list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
8 Python列表如何去重
```
>>>l = [7, 3, 0, 3, 0, 8, 4, 9, 3, 8]
```
先将列表转换成 集合 ( set )，由于集合元素不重复，便实现去重：
```
>>>set(l)
{0, 3, 4, 7, 8, 9}
```
最后再将集合转化成列表即可：
```
>>>list(set(l))
[0, 3, 4, 7, 8, 9]
```
9 一句话解释什么样的语言能够用装饰器
函数可以 作为参数传递 、 可以作为返回值返回 的语言，都可以实现装饰器。
10 Python 内建数据类型有哪些
- 布尔, bool
- 整数, int
- 浮点, float
- 字符串, str
- 字节序列, bytes
- 元组, tuple
- 列表, list
- 字典, dict