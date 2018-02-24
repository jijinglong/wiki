# Shell

```
#!/bin/bash
echo "Hello World !"
```

## var

定义变量

- 命名只能使用英文字母，数字和下划线，首个字符不能以数字开头。
- 不能使用bash里的关键字（可用help命令查看保留关键字）。

```
your_name="runoob.com"
```

使用变量

使用一个定义过的变量，只要在变量名前面加美元符号即可，如：

```
your_name="qinjx"
echo $your_name
echo ${your_name}
```

变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：

```
for skill in Ada Coffe Action Java; do
    echo "I am good at ${skill}Script"
done
```


已定义的变量，可以被重新定义，如：

```
your_name="tom"
echo $your_name
your_name="alibaba"
echo $your_name
```

只读变量

```
#!/bin/bash
myUrl="http://www.w3cschool.cc"
readonly myUrl
myUrl="http://www.runoob.com"
```

删除变量

```
unset variable_name
```

变量被删除后不能再次使用。unset 命令不能删除只读变量。

```
#!/bin/sh
myUrl="http://www.runoob.com"
unset myUrl
echo $myUrl
```

以上实例执行将没有任何输出。

## String

字符串可以用单引号，也可以用双引号，也可以不用引号

```
str='this is a string'
```

单引号字符串的限制
- 单引号里的任何字符都会原样输出，单引号字符串中的变量是无效的
- 单引号字串中不能出现单引号（对单引号使用转义符后也不行）

双引号
```
your_name='qinjx'
str="Hello, I know your are \"$your_name\"! \n"
```

双引号的优点：

- 双引号里可以有变量
- 双引号里可以出现转义字符

拼接字符串
```
your_name="qinjx"
greeting="hello, "$your_name" !"
greeting_1="hello, ${your_name} !"
echo $greeting $greeting_1
```

获取字符串长度
```
string="abcd"
echo ${#string} #输出 4
```

提取子字符串
以下实例从字符串第 2 个字符开始截取 4 个字符：
```
string="runoob is a great site"
echo ${string:1:4} # 输出 unoo
```

查找子字符串
查找字符 "i 或 s" 的位置：
```
string="runoob is a great company"
echo `expr index "$string" is`  # 输出 8
```

## Array

```
array_name=(value0 value1 value2 value3)
```

或

```
array_name=(
value0
value1
value2
value3
)
```

读取数组

```
${数组名[下标]}
```

使用@符号可以获取数组中的所有元素，例如：
```
echo ${array_name[@]}
```

获取数组的长度
获取数组长度的方法与获取字符串长度的方法相同，例如：

```
length=${#array_name[@]}
```

## Arguement

```
#!/bin/bash
# author:菜鸟教程
# url:www.runoob.com

echo "Shell 传递参数实例！";
echo "执行的文件名：$0";
echo "第一个参数为：$1";
echo "第二个参数为：$2";
echo "第三个参数为：$3";
```

```
$ chmod +x test.sh
$ ./test.sh 1 2 3
Shell 传递参数实例！
执行的文件名：./test.sh
第一个参数为：1
第二个参数为：2
第三个参数为：3
```

- $#	传递到脚本的参数个数
- $*	以一个单字符串显示所有向脚本传递的参数。
- 如"$*"用「"」括起来的情况、以"$1 $2 … $n"的形式输出所有参数。
- $$	脚本运行的当前进程ID号
- $!	后台运行的最后一个进程的ID号
- $@	与$*相同，但是使用时加引号，并在引号中返回每个参数。
- 如"$@"用「"」括起来的情况、以"$1" "$2" … "$n" 的形式输出所有参数。
- $-	显示Shell使用的当前选项，与set命令功能相同。
- $?	显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。


## Operation

原生bash不支持简单的数学运算，但是可以通过其他命令来实现，例如 awk 和 expr，expr 最常用。

expr 是一款表达式计算工具，使用它能完成表达式的求值操作。

例如，两个数相加(注意使用的是反引号 \` 而不是单引号 ')

```
#!/bin/bash

val=`expr 2 + 2`
echo "两数之和为 : $val"
```

注意

- 表达式和运算符之间要有空格，例如 2+2 是不对的，必须写成 2 + 2，这与我们熟悉的大多数编程语言不一样。
- 条件表达式要放在方括号之间，并且要有空格，例如: [$a==$b] 是错误的，必须写成 [ $a == $b ]。

算术运算符
- +	加法	`expr $a + $b` 结果为 30。
- -	减法	`expr $a - $b` 结果为 -10。
- *	乘法	`expr $a \* $b` 结果为  200。
- /	除法	`expr $b / $a` 结果为 2。
- %	取余	`expr $b % $a` 结果为 0。
- =	赋值	a=$b 将把变量 b 的值赋给 a。
- ==	相等。用于比较两个数字，相同则返回 true。	[ $a == $b ] 返回 false。
- !=	不相等。用于比较两个数字，不相同则返回 true。	[ $a != $b ] 返回 true。

关系运算符

- -eq	检测两个数是否相等，相等返回 true。	[ $a -eq $b ] 返回 false。
- -ne	检测两个数是否相等，不相等返回 true。	[ $a -ne $b ] 返回 true。
- -gt	检测左边的数是否大于右边的，如果是，则返回 true。	[ $a -gt $b ] 返回 false。
- -lt	检测左边的数是否小于右边的，如果是，则返回 true。	[ $a -lt $b ] 返回 true。
- -ge	检测左边的数是否大于等于右边的，如果是，则返回 true。	[ $a -ge $b ] 返回 false。
- -le	检测左边的数是否小于等于右边的，如果是，则返回 true。	[ $a -le $b ] 返回 true。

布尔运算符
下表列出了常用的布尔运算符，假定变量 a 为 10，变量 b 为 20：

- !	非运算，表达式为 true 则返回 false，否则返回 true。	[ ! false ] 返回 true。
- -o	或运算，有一个表达式为 true 则返回 true。	[ $a -lt 20 -o $b -gt 100 ] 返回 true。
- -a	与运算，两个表达式都为 true 才返回 true。	[ $a -lt 20 -a $b -gt 100 ] 返回 false。

字符串运算符

- =	检测两个字符串是否相等，相等返回 true。	[ $a = $b ] 返回 false。
- !=	检测两个字符串是否相等，不相等返回 true。	[ $a != $b ] 返回 true。
- -z	检测字符串长度是否为0，为0返回 true。	[ -z $a ] 返回 false。
- -n	检测字符串长度是否为0，不为0返回 true。	[ -n $a ] 返回 true。
- str	检测字符串是否为空，不为空返回 true。	[ $a ] 返回 true。

