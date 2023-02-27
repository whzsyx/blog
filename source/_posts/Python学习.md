---
title: Python学习
author: 殇莫
top: false
cover: false
toc: true
mathjax: false
date: 2023-02-27 09:20:46
mg:
coverImg:
password:
summary:
tags: Python 学习
categories: Python 学习
---
循环语句：
在嵌套 if 语句中，可以把 if...elif...else 结构放在另外一个 if...elif...else 结构中。
```
if 表达式1:
    语句
    if 表达式2:
        语句
    elif 表达式3:
        语句
    else:
        语句
elif 表达式4:
    语句
else:
    语句
```
# 函数的学习
1. 函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。
2. 函数能提高应用的模块性，和代码的重复利用率。你已经知道Python提供了许多内建函数，比如print()。 但你也可以自己创建函数，这被叫做用户自定义函数。

>定义一个函数打印25个-
```Python
def printLine():
    print(25 * "-")
```
```Python
def printLine():
    print(25 * "-")


def printline1(ac, bd):
    print(ac * bd)


print("函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。")
printLine()
print("函数能提高应用的模块性，和代码的重复利用率。\n你已经知道Python提供了许多内建函数，比如print()。\n但你也可以自己创建函数，这被叫做用户自定义函数")
printline1(10, "*")
```
# 定义一个add函数
```def add(z,j):
    z + j
    return z + j
x = int(input("请输入x:"))
y = int(input("请输入y:"))
print("x + y = ",add(x, y))
```