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
```Python
def add(z,j):
    z + j
    return z + j
x = int(input("请输入x:"))
y = int(input("请输入y:"))
print("x + y = ",add(x, y))
```
>下标:indexes
> 值:  values
# 数据类型
```Python
l = ["a", "b", "c", "d", "e", "f"]
print("列表里面第二个元素：", l[1])
l[3] = "n"
l.append("xyz")
del l[1]
i = 1
for li in l:
    print("遍历集合中的元素：", i, "个", li)
    i += 1
# i = i + 1
print(25 * "-")
# list的操作
list = ["a", "b", "c", "d", "e"]
list1 = ["f", "g", "h", "d"]
# # append是整体添加数据
# list.append(list1)
# print(list)
# print(len(list))
# # expend是list1里面的数据挨个添加
list.extend(list1)

print(len(list))

print(list)

list2 = ["aa", "bb", "cc", "dd", "ee"]
# 清空列表里面的所有数据
list2.clear()
# 删除列表里面的最后一个元素
list2.pop()
# 根据内容删除数据
list2.remove()
# 根据下表删除数据
del list2[1]
print(list2)
# 字典
# 语法{"key1":values1, "key2":values2, "key3":values3}, key不可重复, values可重复
d1 = {'局长': '张三', '市长': '李六', '县长': "王五"}
d1['省长'] = '李四'

print(d1)
print(d1['局长'])
d1['局长'] = '王五'
print(d1)
# 清除字典的所有数据
# d1.clear()
d1.pop('局长')

for a1 in d1:
    print('key=', a1, 'values=', d1[a1])



# 字典
# 语法{"key1":values1, "key2":values2, "key3":values3}, key不可重复, values可重复
d1 = {'局长': '张三', '市长': '李六', '县长': "王五"}
d1['省长'] = '李四'

print(d1)
print(d1['局长'])
d1['局长'] = '王五'
print(d1)
# 清除字典的所有数据
# d1.clear()
d1.pop('局长')

for a1 in d1:
    print('key=', a1, 'values=', d1[a1])



```
###### 定义一个列表，包含学生的成绩，移除小于60分的成绩
```Python
l = [34, 67, 65, 58, 95, 69]
for j in l:
    if j < 60:
        l.remove(j)
print(l)
```