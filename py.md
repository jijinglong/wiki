- [Python](#python)
  - [If Statement](#if-statement)
  - [For Statement](#for-statement)
  - [Number](#number)
  - [String](#string)
    - [String Operator](#string-operator)
    - [String Format](#string-format)
    - [String Built-in Function](#string-built-in-function)
      - [string.capitalize()](#stringcapitalize)
      - [string.center(width)](#stringcenterwidth)
      - [string.count(str, beg=0, end=len(string))](#stringcountstr-beg0-endlenstring)
      - [string.decode(encoding='UTF-8', errors='strict')](#stringdecodeencodingutf-8-errorsstrict)
      - [string.encode(encoding='UTF-8', errors='strict')](#stringencodeencodingutf-8-errorsstrict)
      - [string.endswith(obj, beg=0, end=len(string))](#stringendswithobj-beg0-endlenstring)
      - [string.expandtabs(tabsize=8)](#stringexpandtabstabsize8)
      - [string.find(str, beg=0, end=len(string))](#stringfindstr-beg0-endlenstring)
      - [string.isalnum()](#stringisalnum)
      - [string.isalpha()](#stringisalpha)
      - [string.isdecimal()](#stringisdecimal)
      - [string.isdigit()](#stringisdigit)
      - [string.islower()](#stringislower)
      - [string.isnumeric()](#stringisnumeric)
      - [string.isspace()](#stringisspace)
      - [string.istitle()](#stringistitle)
      - [string.isupper()](#stringisupper)
      - [string.join(seq)](#stringjoinseq)
      - [string.ljust(width)](#stringljustwidth)
      - [string.lower()](#stringlower)
      - [string.lstrip()](#stringlstrip)
      - [string.maketrans(intab, outtab])](#stringmaketransintab-outtab)
      - [string.translate(str, del="")](#stringtranslatestr-del)
      - [max(str)](#maxstr)
      - [min(str)](#minstr)
      - [string.partition(str)](#stringpartitionstr)
      - [string.replace(str1, str2,  num=string.count(str1))](#stringreplacestr1-str2--numstringcountstr1)
      - [string.rfind(str, beg=0,end=len(string) )](#stringrfindstr-beg0endlenstring-)
      - [string.rjust(width)](#stringrjustwidth)
      - [string.rstrip()](#stringrstrip)
      - [string.split(str="", num=string.count(str))](#stringsplitstr-numstringcountstr)
      - [string.splitlines([keepends])](#stringsplitlineskeepends)
      - [string.startswith(obj, beg=0,end=len(string))](#stringstartswithobj-beg0endlenstring)
      - [string.strip([obj])](#stringstripobj)
      - [string.swapcase()](#stringswapcase)
      - [string.title()](#stringtitle)
      - [string.upper()](#stringupper)
      - [string.zfill(width)](#stringzfillwidth)
      - [string.isdecimal()](#stringisdecimal-1)
  - [List](#list)
    - [Update](#update)
    - [Del](#del)
    - [List Operator](#list-operator)
    - [List Function](#list-function)
      - [cmp(list1, list2)](#cmplist1-list2)
      - [len(list)](#lenlist)
      - [max(list)](#maxlist)
      - [min(list)](#minlist)
      - [list(seq)](#listseq)
      - [list.append(obj)](#listappendobj)
      - [list.count(obj)](#listcountobj)
      - [list.extend(seq)](#listextendseq)
      - [list.index(obj)](#listindexobj)
      - [list.insert(index, obj)](#listinsertindex-obj)
      - [list.pop(obj=list[-1])](#listpopobjlist-1)
      - [list.remove(obj)](#listremoveobj)
      - [list.reverse()](#listreverse)
      - [list.sort([func])](#listsortfunc)
  - [Tuple](#tuple)
  - [Dictionary](#dictionary)
    - [Find](#find)
    - [Update](#update-1)
    - [Del](#del-1)
    - [Dictionary Built-in Function](#dictionary-built-in-function)
      - [dict.clear()](#dictclear)
      - [dict.copy()](#dictcopy)
      - [dict.fromkeys(seq[, val])](#dictfromkeysseq-val)
      - [dict.get(key, default=None)](#dictgetkey-defaultnone)
      - [dict.has_key(key)](#dicthas_keykey)
      - [dict.items()](#dictitems)
      - [dict.keys()](#dictkeys)
      - [dict.setdefault(key, default=None)](#dictsetdefaultkey-defaultnone)
      - [dict.update(dict2)](#dictupdatedict2)
      - [dict.values()](#dictvalues)
      - [pop(key[,default])](#popkeydefault)
      - [popitem()](#popitem)
  - [Function](#function)
    - [Built-in function](#built-in-function)
      - [len()](#len)
      - [input()](#input)
      - [int()](#int)
      - [ord()](#ord)
      - [pow()](#pow)
      - [sum()](#sum)
      - [bin()](#bin)
      - [tuple()](#tuple)
      - [filter](#filter)
      - [range()](#range)
      - [format()](#format)
      - [reduce()](#reduce)
      - [map()](#map)
      - [cmp()](#cmp)
      - [max()](#max)
      - [reverse()](#reverse)
      - [set()](#set)
      - [dict()](#dict)
    - [Unpacking Argument Lists](#unpacking-argument-lists)
    - [Lambda Expressions](#lambda-expressions)
    - [sort](#sort)
    - [sorted](#sorted)
  - [Class](#class)
  - [Module](#module)
    - [Package](#package)
  - [Use](#use)
  - [Lib](#lib)
  - [References](#references)

# Python

## If Statement

``` python
if condition:
    do something
elif condition:
    do something
else:
    do something
```

## For Statement

``` python
for item in iterable:
    do something
```

## Number

- 整型(Int) - 通常被称为是整型或整数，是正或负整数，不带小数点。
- 长整型(long integers) - 无限大小的整数，整数最后是一个大写或小写的L。
- 浮点型(floating point real values) - 浮点型由整数部分与小数部分组成，浮点型也可以使用科学计数法表示（2.5e2 = 2.5 x 102 = 250）
- 复数(complex numbers) - 复数由实数部分和虚数部分构成，可以用a + bj,或者complex(a,b)表示， 复数的实部a和虚部b都是浮点型。

```
int(x [,base ])         将x转换为一个整数
long(x [,base ])        将x转换为一个长整数
float(x )               将x转换到一个浮点数
complex(real [,imag ])  创建一个复数
str(x )                 将对象 x 转换为字符串
repr(x )                将对象 x 转换为表达式字符串
eval(str )              用来计算在字符串中的有效Python表达式,并返回一个对象
tuple(s )               将序列 s 转换为一个元组
list(s )                将序列 s 转换为一个列表
chr(x )                 将一个整数转换为一个字符
unichr(x )              将一个整数转换为Unicode字符
ord(x )                 将一个字符转换为它的整数值
hex(x )                 将一个整数转换为一个十六进制字符串
oct(x )                 将一个整数转换为一个八进制字符串
```

## String

``` python
var = "Hello"

print "var[0]: ", var[0]
print "var[1:5]: ", var[1:5]
print "更新字符串 :- ", var[:5] + ' World!'
```

### String Operator

+ 字符串连接
```
>>>a + b
'HelloPython'
```

* 重复输出字符串
```
>>>a * 2
'HelloHello'
```

[]  通过索引获取字符串中字符
```
>>>a[1]
'e'
```

[ : ] 截取字符串中的一部分
```
>>>a[1:4]
'ell'
```

in  成员运算符 - 如果字符串中包含给定的字符返回 True
```
>>>"H" in a
True
```

not in  成员运算符 - 如果字符串中不包含给定的字符返回 True
```
>>>"M" not in a
True
```

### String Format

```
print "My name is %s and weight is %d kg!" % ('Zara', 21)
```

### String Built-in Function

#### string.capitalize()
把字符串的第一个字符大写

#### string.center(width)
返回一个原字符串居中,并使用空格填充至长度 width 的新字符串

#### string.count(str, beg=0, end=len(string))
返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数

#### string.decode(encoding='UTF-8', errors='strict')
以 encoding 指定的编码格式解码 string，如果出错默认报一个 ValueError 的 异 常 ， 除 非 errors 指 定 的 是 'ignore' 或 者'replace'

#### string.encode(encoding='UTF-8', errors='strict')
以 encoding 指定的编码格式编码 string，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'

#### string.endswith(obj, beg=0, end=len(string))
检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False.

#### string.expandtabs(tabsize=8)
把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8。

#### string.find(str, beg=0, end=len(string))
检测 str 是否包含在 string 中，如果 beg 和 end 指定范围，则检查是否包含在指定范围内，如果是返回开始的索引值，否则返回-1

#### string.isalnum()
如果 string 至少有一个字符并且所有字符都是字母或数字则返回 True, 否则返回 False

#### string.isalpha()
如果 string 至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False

#### string.isdecimal()
如果 string 只包含十进制数字则返回 True 否则返回 False.

#### string.isdigit()
如果 string 只包含数字则返回 True 否则返回 False.

#### string.islower()
如果 string 中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False

#### string.isnumeric()
如果 string 中只包含数字字符，则返回 True，否则返回 False

#### string.isspace()
如果 string 中只包含空格，则返回 True，否则返回 False.

#### string.istitle()
如果 string 是标题化的(见 title())则返回 True，否则返回 False

#### string.isupper()
如果 string 中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False

#### string.join(seq)
以 string 作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串

#### string.ljust(width)
返回一个原字符串左对齐,并使用空格填充至长度 width 的新字符串

#### string.lower()
转换 string 中所有大写字符为小写.

#### string.lstrip()
截掉 string 左边的空格

#### string.maketrans(intab, outtab])
maketrans() 方法用于创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。

#### string.translate(str, del="")
根据 str 给出的表(包含 256 个字符)转换 string 的字符,
要过滤掉的字符放到 del 参数中

```
from string import maketrans   # 必须调用 maketrans 函数。

intab = "aeiou"
outtab = "12345"
trantab = maketrans(intab, outtab)

str = "this is string example....wow!!!";
print str.translate(trantab);  # th3s 3s str3ng 2x1mpl2....w4w!!!
```

#### max(str)
返回字符串 str 中最大的字母。

#### min(str)
返回字符串 str 中最小的字母。

#### string.partition(str)
有点像 find()和 split()的结合体,从 str 出现的第一个位置起,把 字 符 串 string 分 成 一 个 3 元 素 的 元 组 (string_pre_str,str,string_post_str),如果 string 中不包含str 则 string_pre_str == string.

```
str = "http://www.w3cschool.cc/"

print str.partition("://")
```

#### string.replace(str1, str2,  num=string.count(str1))
把 string 中的 str1 替换成 str2,如果 num 指定，则替换不超过 num 次.

#### string.rfind(str, beg=0,end=len(string) )
类似于 find()函数，不过是从右边开始查找.

#### string.rjust(width)
返回一个原字符串右对齐,并使用空格填充至长度 width 的新字符串

#### string.rstrip()
删除 string 字符串末尾的空格.

#### string.split(str="", num=string.count(str))
以 str 为分隔符切片 string，如果 num有指定值，则仅分隔 num 个子字符串

#### string.splitlines([keepends])
按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。

#### string.startswith(obj, beg=0,end=len(string))
检查字符串是否是以 obj 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查.

#### string.strip([obj])
在 string 上执行 lstrip()和 rstrip()

#### string.swapcase()
翻转 string 中的大小写

#### string.title()
返回"标题化"的 string,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle())

```
str = "this is string example....wow!!!";
print str.title();  # This Is String Example....Wow!!!
```

#### string.upper()
转换 string 中的小写字母为大写

#### string.zfill(width)
返回长度为 width 的字符串，原字符串 string 右对齐，前面填充0

#### string.isdecimal()
isdecimal()方法检查字符串是否只包含十进制字符。这种方法只存在于unicode对象。

## List

列表的数据项不需要具有相同的类型, 与字符串的索引一样，列表索引从0开始

```
list1 = ['physics', 'chemistry', 1997, 2000];
list2 = [1, 2, 3, 4, 5, 6, 7 ];

print "list1[0]: ", list1[0]
print "list2[1:5]: ", list2[1:5]
```

### Update
```
list = ['physics', 'chemistry', 1997, 2000];
print list[2];
```

### Del

```
list1 = ['physics', 'chemistry', 1997, 2000];

print list1;
del list1[2];
```

### List Operator

```
>>> len([1, 2, 3])
3

>>> [1, 2, 3] + [4, 5, 6]
[1, 2, 3, 4, 5, 6]  组合

>>> ['Hi!'] * 4
['Hi!', 'Hi!', 'Hi!', 'Hi!']

>>> 3 in [1, 2, 3]
True

>>> for x in [1, 2, 3]: print x
1 2 3
```

### List Function

#### cmp(list1, list2)
比较两个列表的元素

#### len(list)
列表元素个数

#### max(list)
返回列表元素最大值

#### min(list)
返回列表元素最小值

#### list(seq)
将元组转换为列表

#### list.append(obj)
在列表末尾添加新的对象

#### list.count(obj)
统计某个元素在列表中出现的次数

#### list.extend(seq)
在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）

#### list.index(obj)
从列表中找出某个值第一个匹配项的索引位置

#### list.insert(index, obj)
将对象插入列表

#### list.pop(obj=list[-1])
移除列表中的一个元素（默认最后一个元素），并且返回该元素的值

#### list.remove(obj)
移除列表中某个值的第一个匹配项

#### list.reverse()
反向列表中元素

#### list.sort([func])
对原列表进行排序

```
aList = [123, 'xyz', 'zara', 'abc', 'xyz'];
aList.sort();  # [123, 'abc', 'xyz', 'xyz', 'zara']
```

## Tuple

Python的元组与列表类似，不同之处在于元组的元素不能修改。
元组使用小括号，列表使用方括号。

```
Python的元组与列表类似，不同之处在于元组的元素不能修改。
元组使用小括号，列表使用方括号。
元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。
如下实例：
tup1 = ('physics', 'chemistry', 1997, 2000);
tup2 = (1, 2, 3, 4, 5 );
tup3 = "a", "b", "c", "d";
tup1 = (); # 创建空元组
tup1 = (50,); # 元组中只包含一个元素时，需要在元素后面添加逗号
```

## Dictionary

键必须不可变，所以可以用数字，字符串或元组充当，所以用列表就不行
d = {key1 : value1, key2 : value2 }

### Find
```
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'};
print "dict['Name']: ", dict['Name'];
```

### Update
```
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'};

dict['Age'] = 8; # update existing entry
```

### Del

```
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'};

del dict['Name']; # 删除键是'Name'的条目
dict.clear();     # 清空词典所有条目
del dict ;        # 删除词典
```

### Dictionary Built-in Function

#### dict.clear()
删除字典内所有元素

#### dict.copy()
返回一个字典的浅复制

#### dict.fromkeys(seq[, val])
创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值
```
seq = ('name', 'age', 'sex')

dict = dict.fromkeys(seq)
print "New Dictionary : %s" %  str(dict)  # {'age': None, 'name': None, 'sex': None}

dict = dict.fromkeys(seq, 10)
print "New Dictionary : %s" %  str(dict)  # {'age': 10, 'name': 10, 'sex': 10}
```

#### dict.get(key, default=None)
返回指定键的值，如果值不在字典中返回default值

#### dict.has_key(key)
如果键在字典dict里返回true，否则返回false

#### dict.items()
以列表返回可遍历的(键, 值) 元组数组

```
dict = {'Google': 'google.com', 'Runoob': 'runoob.com', 'taobao': 'taobao.com'}
print "字典值 : %s" %  dict.items() # [('Google', 'google.com'), ('taobao', 'taobao.com'), ('Runoob', 'runoob.com')]
```

#### dict.keys()
以列表返回一个字典所有的键

#### dict.setdefault(key, default=None)
和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default

#### dict.update(dict2)
把字典dict2的键/值对更新到dict里

```
dict = {'Name': 'Zara', 'Age': 7}
dict2 = {'Sex': 'female' }

dict.update(dict2)
print "Value : %s" %  dict  ## {'Age': 7, 'Name': 'Zara', 'Sex': 'female'}
```

#### dict.values()
以列表返回字典中的所有值

#### pop(key[,default])
删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。

#### popitem()
随机返回并删除字典中的一对键和值。

## Function

def functionname( parameters ):
   "函数_文档字符串"
   function_suite
   return [expression]

### Built-in function

#### len()

```
s = "abc"
len(s)
cubes = [1, 8, 27, 65, 125]
cubes.append(216)  # [1, 8, 27, 64, 125, 216]
x = cubes + [343]  # [1, 8, 27, 64, 125, 216, 343]
```

#### input()

input() 和 raw_input() 这两个函数均能接收 字符串 ，但 raw_input() 直接读取控制台的输入（任何类型的输入它都可以接收）。而对于 input() ，它希望能够读取一个合法的 python 表达式，即你输入字符串的时候必须使用引号将它括起来，否则它会引发一个 SyntaxError 。

```
>>>a = input("input:")
input:123                  # 输入整数
>>> type(a)
<type 'int'>               # 整型
```

raw_input() 将所有输入作为字符串看待

```
>>>a = raw_input("input:")
input:123
>>> type(a)
<type 'str'>              # 字符串
```

#### int()

int(x, base=10) 函数用于将一个字符串会数字转换为整型。

- x -- 字符串或数字。
- base -- 进制数，默认十进制。


#### ord()

ord(c) 函数是 chr() 函数的配对函数

- c -- 字符。

```
>>>ord('a')
97
```

#### pow()

pow(x, y[, z])

- x -- 数值表达式。
- y -- 数值表达式。
- z -- 数值表达式。

```
>>> 5 ** 2  # power
25
>>> pow(5, 2)
25
```

#### sum()

sum(iterable[, start])

```
>>>sum([0,1,2])
3
>>> sum((2, 3, 4), 1)        # 元组计算总和后再加 1
10
>>> sum([0,1,2,3,4], 2)      # 列表计算总和后再加 2
12
```

#### bin()

bin(x) 返回一个整数 int 或者长整数 long int 的二进制表示。

- x -- int 或者 long int 数字

```
>>>bin(10)
'0b1010'
>>> bin(20)
'0b10100'
```

#### tuple()

```
>>>tuple([1,2,3,4])

(1, 2, 3, 4)

>>> tuple({1:2,3:4})    #针对字典 会返回字典的key组成的tuple

(1, 3)

>>> tuple((1,2,3,4))    #元组会返回元组自身

(1, 2, 3, 4)
```

#### filter

filter(function, iterable)

```
def is_odd(n):
    return n % 2 == 1

newlist = filter(is_odd, [1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
print(newlist)
```

#### range()

range(start, stop[, step])

``` bash
>>> range(10)
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> range(5, 10)
[5, 6, 7, 8, 9]
>>> range(0, 10, 3)
[0, 3, 6, 9]
>>> range(-10, -100, -30)
[-10, -40, -70]
```

``` bash
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
...     print i, a[i]
...
0 Mary
1 had
2 a
3 little
4 lamb
```

In most such cases, however, it is convenient to use the enumerate() function
``` bash
>>> seasons = ['Spring', 'Summer', 'Fall', 'Winter']
>>> list(enumerate(seasons))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
>>> list(enumerate(seasons, start=1))
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]

arr = ["a", "b", "c"]
for i, v in enumerate(arr):
    print i, v
```

#### format()

```
>>>"{} {}".format("hello", "world")    # 不设置指定位置，按默认顺序
'hello world'

>>> "{0} {1}".format("hello", "world")  # 设置指定位置
'hello world'

>>> "{1} {0} {1}".format("hello", "world")  # 设置指定位置
'world hello world'

print("网站名：{name}, 地址 {url}".format(name="菜鸟教程", url="www.runoob.com"))

# 通过字典设置参数
site = {"name": "菜鸟教程", "url": "www.runoob.com"}
print("网站名：{name}, 地址 {url}".format(**site))

# 通过列表索引设置参数
my_list = ['菜鸟教程', 'www.runoob.com']
print("网站名：{0[0]}, 地址 {0[1]}".format(my_list))  # "0" 是必须的

>>> print("{:.2f}".format(3.1415926));
3.14
>>> print("{:0>2d}".format(5));
05
>>> print("{:x<4d}".format(5));
5xxx
```

#### reduce()

```
>>>def add(x, y) :            # 两数相加
...     return x + y
...
>>> reduce(add, [1,2,3,4,5])   # 计算列表和：1+2+3+4+5
15
>>> reduce(lambda x, y: x+y, [1,2,3,4,5])  # 使用 lambda 匿名函数
15
```

#### map()

map(function, iterable, ...)

- function -- 函数，有两个参数
- iterable -- 一个或多个序列

```
>>>def square(x) :            # 计算平方数
...     return x ** 2
...
>>> map(square, [1,2,3,4,5])   # 计算列表和：1+2+3+4+5
[1, 4, 9, 16, 25]
>>> map(lambda x: x ** 2, [1, 2, 3, 4, 5])  # 使用 lambda 匿名函数
[1, 4, 9, 16, 25]

# 提供了两个列表，对相同位置的列表数据进行相加
>>> map(lambda x, y: x + y, [1, 3, 5, 7, 9], [2, 4, 6, 8, 10])
[3, 7, 11, 15, 19]
```

#### cmp()

cmp(x,y) 函数用于比较2个对象，如果 x < y 返回 -1, 如果 x == y 返回 0, 如果 x > y 返回 1。

#### max()

max(x, y, z, .... ) 方法返回给定参数的最大值，参数可以为序列。

```
print max(80, 100, 1000)
print max([80, 100, 1000])
```

#### reverse()

reverse() 函数用于反向列表中元素

```
aList = [123, 'xyz', 'zara', 'abc', 'xyz'];
aList.reverse();
['xyz', 'abc', 'zara', 'xyz', 123]
```

#### set()

```
>>>x = set('runoob')
>>> y = set('google')
>>> x, y
(set(['b', 'r', 'u', 'o', 'n']), set(['e', 'o', 'g', 'l']))   # 重复的被删除
>>> x & y         # 交集
set(['o'])
>>> x | y         # 并集
set(['b', 'e', 'g', 'l', 'o', 'n', 'r', 'u'])
>>> x - y         # 差集
set(['r', 'b', 'u', 'n'])
>>>
```

#### dict()

```
>>>dict()                        # 创建空字典
{}
>>> dict(a='a', b='b', t='t')     # 传入关键字
{'a': 'a', 'b': 'b', 't': 't'}
>>> dict(zip(['one', 'two', 'three'], [1, 2, 3]))   # 映射函数方式来构造字典
{'three': 3, 'two': 2, 'one': 1}
>>> dict([('one', 1), ('two', 2), ('three', 3)])    # 可迭代对象方式来构造字典
{'three': 3, 'two': 2, 'one': 1}
>>>
```

### Unpacking Argument Lists

```
>>> range(3, 6)             # normal call with separate arguments
[3, 4, 5]
>>> args = [3, 6]
>>> range(*args)            # call with arguments unpacked from a list
[3, 4, 5]
```

In the same fashion, dictionaries can deliver keyword arguments with the ** operator:

```
>>> def parrot(voltage, state='a stiff', action='voom'):
...     print "-- This parrot wouldn't", action,
...     print "if you put", voltage, "volts through it.",
...     print "E's", state, "!"
...
>>> d = {"voltage": "four million", "state": "bleedin' demised", "action": "VOOM"}
>>> parrot(**d)
```

### Lambda Expressions

匿名函数

```
>>> def make_incrementor(n):
...     return lambda x: x + n
...
>>> f = make_incrementor(42)
>>> f(0)
42
>>> f(1)
43
```

### sort

```
>>> pairs = [(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
>>> pairs.sort(key=lambda pair: pair[1])
>>> pairs
[(4, 'four'), (1, 'one'), (3, 'three'), (2, 'two')]
```

### sorted

sorted(iterable[, cmp[, key[, reverse]]])

- iterable -- 可迭代对象。
- cmp -- 比较的函数，这个具有两个参数，参数的值都是从可迭代对象中取出，此函数必须遵守的规则为，大于则返回1，小于则返回-1，等于则返回0。
- key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
- reverse -- 排序规则，reverse = True 降序 ， reverse = False 升序（默认）。

```
>>>a = [5,7,6,3,4,1,2]
>>> b = sorted(a)       # 保留原列表
>>> a
[5, 7, 6, 3, 4, 1, 2]
>>> b
[1, 2, 3, 4, 5, 6, 7]

>>> L=[('b',2),('a',1),('c',3),('d',4)]
>>> sorted(L, cmp=lambda x,y:cmp(x[1],y[1]))   # 利用cmp函数
[('a', 1), ('b', 2), ('c', 3), ('d', 4)]
>>> sorted(L, key=lambda x:x[1])               # 利用key
[('a', 1), ('b', 2), ('c', 3), ('d', 4)]


>>> students = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
>>> sorted(students, key=lambda s: s[2])            # 按年龄排序
[('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]

>>> sorted(students, key=lambda s: s[2], reverse=True)       # 按降序
[('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
>>>
```

## Class

``` python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']

# instance
cola = CocaCola()
print(cola.formula)

# inherit
class CocaColaChina(CocaCola):
    formula = ['caffeine','sugar','water','soda']
```

## Module

```
import module1[, module2[,... moduleN]
```

Python 的 from 语句让你从模块中导入一个指定的部分到当前命名空间中

```
from modname import name1[, name2[, ... nameN]]
```

### Package

包是一个分层次的文件目录结构，它定义了一个由模块及子包，和子包下的子包等组成的 Python 的应用环境。
简单来说，包就是文件夹，但该文件夹下必须存在 __init__.py 文件, 该文件的内容可以为空。__int__.py用于标识当前文件夹是一个包。
考虑一个在 package_runoob 目录下的 runoob1.py、runoob2.py、__init__.py 文件，test.py 为测试调用包的代码，目录结构如下：

```
test.py
package_runoob
|-- __init__.py
|-- runoob1.py
|-- runoob2.py
```

源代码如下



## Use

逗号分隔整数
```
str=raw_input()
res=[int(s) for s in str.split(',') if s.isdigit()]
```

## Lib

``` bash
pip install PackageName
pip install --upgrade PackageName
pip uninstall PackageName
pip list
python3 -m pip install PackageName
```

## References

- 侯爵. 编程小白的第一本 Python 入门书. Retrieved July 17, 2017, from http://www.ituring.com.cn/book/1863.
