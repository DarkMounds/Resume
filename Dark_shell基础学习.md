#shell基础学习
##一、第一个shell
打开文本编辑器(可以使用 vi/vim 命令来创建文件)，新建一个文件 test.sh，扩展名为 sh（sh代表shell），扩展名并不影响脚本执行，见名知意就好，如果你用 php 写 shell 脚本，扩展名就用 php 好了。
输入一些代码，第一行一般是这样：
实例
**#!/bin/bash**
**echo "Hello World !"**

·#! 是一个约定的标记，它告诉系统这个脚本需要什么解释器来执行，即使用哪一种 Shell。
echo 命令用于向窗口输出文本。

####运行 Shell 脚本有两种方法：
**1、作为可执行程序**
将上面的代码保存为 test.sh，并 cd 到相应目录：
chmod +x ./test.sh  #使脚本具有执行权限
./test.sh  #执行脚本
注意，一定要写成 ./test.sh，而不是 test.sh，运行其它二进制的程序也一样，直接写 test.sh，linux 系统会去 PATH 里寻找有没有叫 test.sh 的，而只有 /bin, /sbin, /usr/bin，/usr/sbin 等在 PATH 里，你的当前目录通常不在 PATH 里，所以写成 test.sh 是会找不到命令的，要用 ./test.sh 告诉系统说，就在当前目录找。
**2、作为解释器参数**
这种运行方式是，直接运行解释器，其参数就是 shell 脚本的文件名，如：
/bin/sh test.sh
/bin/php test.php
这种方式运行的脚本，不需要在第一行指定解释器信息，写了也没用。

##二、shell变量

####1.定义变量
**定义变量时，变量名不加美元符号（$，PHP语言中变量需要），如：**
your_name="runoob.com"
注意，变量名和等号之间不能有空格，这可能和你熟悉的所有编程语言都不一样。同时，变量名的命名须

遵循如下规则：
**·命名只能使用英文字母，数字和下划线，首个字符不能以数字开头。**
**·中间不能有空格，可以使用下划线（_）。**
**·不能使用标点符号。**
**·不能使用bash里的关键字（可用help命令查看保留关键字）。**

有效的 Shell 变量名示例如下：
RUNOOB
LD_LIBRARY_PATH
_var
var2

无效的变量命名：
?var=123
user*name=runoob

除了显式地直接赋值，还可以用语句给变量赋值，如：
<for file in `ls /etc`>
或
for file in $(ls /etc)
以上语句将 /etc 下目录的文件名循环出来。

####2.使用变量
**使用一个定义过的变量，只要在变量名前面加美元符号即可，如：**
`your_name="qinjx"
echo $your_name
echo ${your_name}`
**变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：**
`for skill in Ada Coffe Action Java; do
    echo "I am good at ${skill}Script"
done`
如果不给skill变量加花括号，写成`echo "I am good at $skillScript"`，解释器就会把`$skillScript`当成一个变量（其值为空），代码执行结果就不是我们期望的样子了。
推荐给所有变量加上花括号，这是个好的编程习惯。
<已定义的变量，可以被重新定义，如：
`your_name="tom"
echo $your_name
your_name="alibaba"
echo $your_name**`

这样写是合法的，但注意，第二次赋值的时候不能写`$your_name="alibaba"`，使用变量的时候才加美元符（$）。

####3.只读变量
使用 readonly 命令可以将变量定义为只读变量，只读变量的值不能被改变。
下面的例子尝试更改只读变量，结果报错：
`#!/bin/bash
myUrl="http://www.w3cschool.cc"
readonly myUrl
myUrl="http://www.runoob.com"`
运行脚本，结果如下：
/bin/sh: NAME: This variable is read only.

####4.删除变量
使用 unset 命令可以删除变量。语法：
unset variable_name
变量被删除后不能再次使用。unset 命令不能删除只读变量。
实例
`#!/bin/sh
myUrl="http://www.runoob.com"
unset myUrl
echo $myUrl`
以上实例执行将没有任何输出

####变量类型
运行shell时，会同时存在三种变量：
1) 局部变量 局部变量在脚本或命令中定义，仅在当前shell实例中有效，其他shell启动的程序不能访问局部变量。
2) 环境变量 所有的程序，包括shell启动的程序，都能访问环境变量，有些程序需要环境变量来保证其正常运行。必要的时候shell脚本也可以定义环境变量。
3) shell变量 shell变量是由shell程序设置的特殊变量。shell变量中有一部分是环境变量，有一部分是局部变量，这些变量保证了shell的正常运行


##三、shell字符串
字符串是shell编程中最常用最有用的数据类型（除了数字和字符串，也没其他类型好用了），字符串可以用单引号，也可以用双引号，也可以不用引号。单双引号的区别跟PHP类似。

####1.单引号
`str='this is a string'`
单引号字符串的限制：
·单引号里的任何字符都会原样输出，单引号字符串中的变量是无效的；
·单引号字符串中不能出现单引号（对引号使用转义符后也不行）

####2.双引号
`your_name='qinjx'
str="Hello, I know you are \"$your_name\"! \n`
双引号的优点：
·双引号里面可以有变量
·双引号里可以出现转义字符

####3.拼接字符串
`your_name="qinjx"
greeting="hello, "$your_name" !"
greeting_1="hello, ${your_name} !"
echo $greeting $greeting_1`

####4.获取字符串长度
`string="abcd"
echo ${#string} #输出 4`
####5.提取子字符串
以下实例从字符串第 2 个字符开始截取 4 个字符：
`string="runoob is a great site"
echo ${string:1:4} # 输出 unoo`

####6.查找子字符串
查找字符 "i 或 s" 的位置：
`string="runoob is a great company"
echo `expr index "$string" is`  # 输出 8`
注意： 以上脚本中 "`" 是反引号，而不是单引号 "'"，不要看错了哦。


##四、shell数组
bash支持一维数组（不支持多维数组），并且没有限定数组的大小。
类似与C语言，数组元素的下标由0开始编号。获取数组中的元素要利用下标，下标可以是整数或算术表达式，其值应大于或等于0。

####1.定义数组
在Shell中，用括号来表示数组，数组元素用"空格"符号分割开。定义数组的一般形式为：
数组名=(值1 值2 ... 值n)
例如：
`array_name=(value0 value1 value2 value3)`
或者
`array_name=(
value0
value1
value2
value3
)`
还可以单独定义数组的各个分量：
`array_name[0]=value0
array_name[1]=value1
array_name[n]=valuen`
可以不使用连续的下标，而且下标的范围没有限制

####2.读取数组
读取数组元素值的一般格式是：
${数组名[下标]}
例如：
valuen=${array_name[n]}
使用@符号可以获取数组中的所有元素，例如：
echo ${array_name[@]}
####4.获取数组的长度
获取数组长度的方法与获取字符串长度的方法相同，例如：
`# 取得数组元素的个数`
`length=${#array_name[@]}`
`# 或者`
`length=${#array_name[*]}`
`# 取得数组单个元素的长度`
`lengthn=${#array_name[n]}`
##五、Shell 注释
以"#"开头的行就是注释，会被解释器忽略。
sh里没有多行注释，只能每一行加一个#号。
`如果在开发过程中，遇到大段的代码需要临时注释起来，过一会儿又取消注释，怎么办呢？
每一行加个#符号太费力了，可以把这一段要注释的代码用一对花括号括起来，定义成一个函数，没有地方调用这个函数，这块代码就不会执行，达到了和注释一样的效果。

