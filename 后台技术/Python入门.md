[Python官网](https://www.python.org/ )

[运行步骤](http://pythontutor.com/):可以一行一行的进行解读、图文结合

##基本介绍

python是高级语言   后缀 .py    优化后文件.pyo    编译后的文件.pyc

在高级语言中根据特性，其属于解释性语言（还有编译性语言如C/C++）

解释性语言的好处：代码在放入脚本之前，可以在交互模式下测试（如js的console）一下。
    cmd: python 进入调试模式:注意错误类型

高级语言缺点是必须经过转换才可以运行在机器上，不过优点大过缺点：书写高效、可移植性好


##进入Python

###数据类型
5种基本对象类型
   字符串 ' str '   整数  10   浮点数   10.0   布尔数  true  复数  1+1j 

判断值得类型`type()`,结果：str  int  float  function... ...
```
type('as')    # str
type(1)       # int
type(1.0)     #float
type('1')     # str
```

###变量
命名规则同其他语言,注意关键字和保留字
```
n = 1
type(n)    int
```

###运算
运算符
     `+ `  ` -`    `*`     `/`     `**`(指数运算，N次幂：2**3  =8)    `//`      `%`
     ^(XOR异或运算)

差异：版本2中值为小数的话，向下取整；版本3中保留小数;除非参与运算的其中一个值是浮点数

运算优先级

遵循算术的规则括号、加、减... ...

如果类型不同的对象进行运算，自动类型转换顺序
     bool -- int -- float --复数
     true +4 =1 +4 =1.0 +4.0 =5.0

逻辑运算
      和  `and`    或  `or`   否  `not`
      （Python中并不返回布尔值，返回比较值之一 ： 123 and 456 返回456）

条件运算
    `==`   `!=`   `<`  `>`     `<=`    `>=`

###字符串
用引号包裹，里面含有引号的话使用转义字符

`+` 拼接  str1 + str2
`*` 重复  str*3

布尔：一个字符串是否是另一个字符串的子串

    var char in str   #true 或 false

枚举每个字符

    for char in  str  

字符索引

    下标从0开始正序，﹣1开始倒序

切片（截断字符串）

    str = 'hello world'
    str[2:3]   #l
    str[2:]    #llo world
    str[:3]    #hel

    str[2:3:1] #l 字符串连续的（第三个参数控制默认是1）
    str[:3:2]  #隔一个字符输出
    str[::-1]  #字符串倒序输出  'dlrow olleh'

注意：对字符串的操作不会改变原有的值

    str.repeat('o','b')
    str  #还是'hello world'

除非对其重新赋值

    str =str.repeat('o','b')
    str # 'hellb wbrld'

字符串格式化
    'hello {} good {}'.format(5 ,'day')  #hello 5good day

可以设置`{}`精度
```
    'PI is {:.4f}'.format(math.pi) #3.1416保留四位小数
    'PI is {:9.4f}'.format(math.pi) #    3.1416保留四位小数，并且靠右输出（左侧空格）
```

###列表
arr =[]

元祖：不可变的列表
    arr = (1,2,3)  或者 (1,) 或者 1,2,3

拼接的话arr1 += arr2是错误的，可以转存第三方变量
    arr3 = arr1 + arr2

###字典
o = { 键 : 值，键 :值}

集合（没有值）
o = { 键，键 }

###输入和输出
输出 print 
```
1: print 123                    # 123
2: print '结果是：' ,123        # 结果是：123   （逗号）
3: print '第一行 \n另起一行'    #（转义字符）
```

raw_input('提示语')           #接收输入（字符串，使用数字的话需转换）
运行之后，根据提示语输入文字在回车（运行）
```
1： str = float( raw_input('demo:') )   #可以赋值给变量
2： print raw_input('demo:')   #直接输出
```

###函数
自定义函数
```
#函数头  冒号结尾
def  函数名():    
     # Code  函数体必须是缩进的。按照惯例，缩进经常是4个空格

#调用
函数名()
```
实参：传入
形参：占位        它们都是局部的

有返回值/无返回值

###模块
       1.import   math
                 print  math.pi      #正确
                 print  pi           #错误
       2.from  math import *
                 print pi            #正确（缺点:怕命名冲突）

###程序控制
```
  for  in   /   if  等等

  if  条件：# 没有括号要注意
     code
  else：
     code

  if 条件: # 多分支条件语句
      code
  elif 条件:
      code
  else:
      code

  while 条件：# 条件成立的话一直执行，只有条件不成立程序才会往下走
      code

  break  和 continue  #跳出循环

  for  var  in  obj
      code
```
###dir输出对象的所有方法和属性
如 str
    dir(str)

###缩进
       推荐空格     如果tab和空格混用的话，错误不好发现

###注释
      # 后面的一行代码都不会执行
      """   3个引号多行注释  """

###时间复杂度
比如二分法的时间复杂度
    O(log2n)

###DSU模式
Decorate 装饰   Sort排序   Undecorate饭装饰