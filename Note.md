# **变量，运算符与数据类型**

1. ## **注释：**

   ```python
   使用“#”，作用于整行，与正常代码字体不同
   #hello world
   print（"hello world"）
   
   使用’’’ （三个单引号），用于多行注释
   
   '''
   hello world
   hello world
   '''
   print("hello world") 
   ```

   

2. ## **运算符：**

   ### **算数运算符**

   ```python
   print(1 + 1)
   print（2 - 1)
   print(2 * 2)
   print(4 / 3)
   print(3 // 4)
   print(3 % 4)
   print(2 ** 3)
   ```

   ![2](C:\Users\liu\Desktop\笔记\task1\2.png)

### **比较运算符**

```python 
print(2 > 1)  # True
print(2 >= 4)  # False
print(1 < 2)  # True
print(5 <= 2)  # False
print(3 == 4)  # False
print(3 != 5)  # True
```



![3](C:\Users\liu\Desktop\笔记\task1\3.png)

### **逻辑运算符**

![4](C:\Users\liu\Desktop\笔记\task1\4.png)

### **位运算符**

![5](C:\Users\liu\Desktop\笔记\task1\5.png)



### **三元运算符**

```python
x, y = 4, 5
if x < y:
    small = x
else:
    small = y
print(small)  # 4
```



### **其他运算符**

如图：

![6](C:\Users\liu\Desktop\笔记\task1\6.png)

（1）检查字符是否在表中

```python
letters = ['A', 'B', 'C']
if 'A' in letters:
    print('A' + ' exists')
if 'h' not in letters:
    print('h' + ' not exists')
# A exists
# h not exists
```



（2）比较两个变量是否相同（两个变量均指向不可变类型）

```python
a = "hello"
b = "hello"
print(a is b, a == b)  # True True
print(a is not b, a != b)  # False False
```

（3）比较的两个变量均指向可变类型

```python
a = ["hello"]
b = ["hello"]
print(a is b, a == b)  # False True
print(a is not b, a != b)  # True False
```

！需要注意的问题：

- is, is not 对比的是两个变量的内存地址
- ==, != 对比的是两个变量的值
- 如果比较的两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的
- 如果对比的两个变量，指向的是地址可变的类型（list，dict，tuple等），则两者是有区别的

## **运算符的优先级**

- 一元运算符优于二元运算符。例如3**-2等价于3**(-2)
- 先算术运算，后移位运算，最后位运算。例如 1 << 3 + 2 & 7等价于 1 << (3 + 2)) & 7。
- 逻辑运算最后结合。例如3 < 4 and 4 < 5等价于(3 < 4) and (4 < 5)。

示例

```python
print(-3 ** 2)  # -9
print(3 ** -2)  # 0.1111111111111111
print(1 << 3 + 2 & 7)  # 0
print(-3 * 2 + 5 / -2 - 4)  # -12.5
print(3 < 4 and 4 < 5)  # True
12345
```

1. ## 变量和赋值

在使用变量之前，我们总需要先对其赋值，才能进行后续变量运算等操作。

变量名可以包括字母，数字，下划线，但不能以数字开头，且当变量名内字母的大小写不同，就会代表不同的变量。
foo！=Foo（foo不等于Foo）

示例

```python
teacher = "张三"
print(teacher)  # 张三
12
first = 2
second = 3
third = first + second
print(third)  # 5
1234
myTeacher = "张三"
yourTeacher = "李四"
ourTeacher = myTeacher + ',' + yourTeacher
print(ourTeacher)  # 张三,李四
1234
```

1. ## 数据类型与转换

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829120413562.png#pic_center)

## **整型**int

查询变量a的类型

```python
a = 1031
print(a, type(a))
# 1031 <class 'int'>
123
```

- tips：Python 里面万物皆对象（object），整型也不例外，只要是对象，就有相应的属性（attributes） 和方法（methods）

```python
b = dir(int)
print(b)
# ['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__',
# '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__',
# '__float__', '__floor__', '__floordiv__', '__format__', '__ge__',
# '__getattribute__', '__getnewargs__', '__gt__', '__hash__',
# '__index__', '__init__', '__init_subclass__', '__int__', '__invert__',
# '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__',
# '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__',
# '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__',
# '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__',
# '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__',
# '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__',
# '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__',
# 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag',
# 'numerator', 'real', 'to_bytes']
12345678910111213141516
```

具体怎么用，需要哪些参数 （argument），还需要查文档。

bit_length()示例

```python
a = 1031
print(bin(a))  # 0b10000000111
print(a.bit_length())  # 11
123
```

## **浮点型float（带小数的数值变量）**

```python
print(1, type(1))  # 1 <class 'int'>
print(1., type(1.)) # 1.0 <class 'float'>
a = 0.00000023
b = 2.3e-7
print(a)  # 2.3e-07
print(b)  # 2.3e-07
123456
```

如果想保留浮点型的小数点后 n 位。可以用 decimal 包里的 Decimal 对象和 getcontext() 方法来实现

```python
import decimal
from decimal import Decimal
12
```

import用于引进需要使用的包。包也是对象，可用dir()来查看属性和方法

getcontext() 示例

```python
a = decimal.getcontext()
print(a)
# Context(prec=28, rounding=ROUND_HALF_EVEN, Emin=-999999, Emax=999999,capitals=1, clamp=0, flags=[], traps=[InvalidOperation, DivisionByZero, Overflow])
123
```

可知Decimal对象的默认精度值是28位(prec=28）

```python
b = Decimal(1) / Decimal(3)
print(b)  
# 0.3333333333333333333333333333
123
```

使用getcontext().prec来调整精度，保留4位

```python
decimal.getcontext().prec = 4
c = Decimal(1) / Decimal(3)
print(c)
# 0.3333
1234
```

## **布尔型boolean（True False）**

```python
print(True + True)  # 2
print(True + False)  # 1
print(True * False)  # 0
123
```

除了直接给变量赋值 True 和 False，还可以用 bool(X) 来创建变量，其中 X 可以是：

- 基本类型：整型、浮点型、布尔型
- 容器类型：字符串、元组、列表、字典和集合

bool示例
（1）作用在基本类型变量：X 只要不是整型 0、浮点型 0.0，bool(X) 就是 True，其余就是 False

```python
print(type(0), bool(0), bool(1))
# <class 'int'> False True

print(type(10.31), bool(0.00), bool(10.31))
# <class 'float'> False True

print(type(True), bool(False), bool(True))
# <class 'bool'> False True
12345678
```

（2)作用在容器类型变量：X 只要不是空的变量，bool(X) 就是 True，其余就是 False

```python
print(type(''), bool(''), bool('python'))
# <class 'str'> False True
print(type(()), bool(()), bool((10,)))
# <class 'tuple'> False True
print(type([]), bool([]), bool([1, 2]))
# <class 'list'> False True
print(type({}), bool({}), bool({'a': 1, 'b': 2}))
# <class 'dict'> False True
print(type(set()), bool(set()), bool({1, 2}))
# <class 'set'> False True
12345678910
```

确定bool(X) 的值是 True 还是 False，就看 X 是不是空，空的话就是 False，不空的话就是 True

- 对于数值变量，0, 0.0 都可认为是空的
- 对于容器变量，里面没元素就是空的

1. ## **获取类型信息type(object)**

示例

```python
print(isinstance(1, int))  # True
print(isinstance(5.2, float))  # True
print(isinstance(True, bool))  # True
print(isinstance('5.2', str))  # True
1234
```

tips：

- type() 不会认为子类是一种父类类型，不考虑继承关系
- isinstance() 会认为子类是一种父类类型，考虑继承关系
  （判断两个类型是否相同可用isinstance() 。）

1. ## **类型转换**

- 转换为整型 int(x, base=10)
- 转换为字符串 str(object=’ ')
- 转换为浮点型 float(x)

示例

```python
print(int('520'))  # 520
print(int(520.52))  # 520
print(float('520.52'))  # 520.52
print(float(520))  # 520.0
print(str(10 + 10))  # 20
print(str(10.1 + 5.2))  # 15.3
123456
```

1. ## print()函数

```python
print(*objects, sep=' ', end='\n', file=sys.stdout, fl
1
```

- 将对象以字符串表示的方式格式化输出到流文件对象file里。其中所有非关键字参数都按str()方式进行转换为字符串输出；
- 参数sep是实现分隔符，比如多个参数输出时想要输出中间的分隔字符；
- 参数end是输出结束时的字符，默认是换行符\n；
- 参数file是定义要输出的流文件，可以是标准的系统输出sys.stdout，也可以重定义为别的文件；
- 参数flush是立即把内容输出到流文件，不作缓存。

示例
（1）没有设置参数end，默认换行

```python
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed without 'end'and 'sep'.")
for item in shoplist:
    print(item)
# This is printed without 'end'and 'sep'.
# apple
# mango
# carrot
# banana
123456789
```

(2)第一个print没有设置参数end，默认换行，第二个print，在每次输出结束都参数end设置结尾，所以没有默认换行

```python
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed with 'end='&''.")
for item in shoplist:
    print(item, end='&')
print('hello world')
# This is printed with 'end='&''.
# apple&mango&carrot&banana&hello world
1234567
```

(3)item值与’another string’两个值之间用sep设置的参数&分割。由于end参数没有设置，因此默认是输出解释后换行，即end参数的默认值为\n

```python
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed with 'sep='&''.")
for item in shoplist:
    print(item, 'another string', sep='&')
# This is printed with 'sep='&''.
# apple&another string
# mango&another string
# carrot&another string
# banana&another string
123456789
```

# 位运算

1. ## 二进制的原码，反码和补码

二进制有三种不同的表示形式：原码、反码和补码，计算机内部使用补码来表示

（1）原码：就是其二进制表示（注意，有一位符号位）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829153606934.png#pic_center)

（2）反码：正数的反码就是原码，负数的反码是符号位不变，其余位取反（对应正数按位取反）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829153625575.png#pic_center)

（3）补码：正数的补码就是原码，负数的补码是反码+1
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829153703472.png#pic_center)

（4）符号位：最高位为符号位，0表示正数，1表示负数。在位运算中符号位也参与运算

1. ## 按位运算

- **按位非操作 ~**



- **按位与操作 &**
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154122918.png#pic_center)
  只有两个对应位都为1时才为1
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154159887.png#pic_center)
- **按位或操作 |**
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154242260.png#pic_center)
  只要两个对应位中有一个是1时就是1
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/2020082915432770.png#pic_center)
- **按位异或操作 ^**
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154406324.png#pic_center)
  只有两个对应为不同时才为1
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154623894.png#pic_center)
  满足交换率和结合律
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154718875.png#pic_center)
- **按位右移操作 >>**
  num>>i将num的二进制表示向右移动i位所得的值
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829154913952.png#pic_center)

1. ## **利用位运算实现快速计算**

通过 <<，>> 快速计算2的倍数问题
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829155219188.png#pic_center)
通过 ^ 快速交换两个整数。 通过 ^ 快速交换两个整数
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829155355566.png#pic_center)
通过 a & (-a) 快速获取a的最后为 1 位置的整数
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829155424180.png#pic_center)

1. ## 利用位运算实现整数集合

一个数的二进制表示可以看作是一个集合（0 表示不在集合中，1 表示在集合中）
比如集合 {1, 3, 4, 8}，可以表示成 01 00 01 10 10 而对应的位运算也就可以看作是对集合进行的操作
（这一部分没看明白）

- 元素与集合的操作：
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829155844954.png#pic_center)
- 集合之间的操作：
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829160341295.png#pic_center)
  整数在内存中是以补码的形式存在的，输出也是按照补码的形式输出

bin()示例

```python
print(bin(3))  # 0b11
print(bin(-3))  # -0b11
print(bin(-3 & 0xffffffff))  
# 0b11111111111111111111111111111101
print(bin(0xfffffffd))       
# 0b11111111111111111111111111111101
print(0xfffffffd)  # 4294967293
1234567
```

- bin一个负数（十进制表示），输出的是它的原码的二进制表示加上个负号
- 整型是补码形式存储的，不限制长度，不会超范围溢出

tips：为了获得负数（十进制表示）的补码，需要手动将其和十六进制数0xffffffff进行按位与操作，再使用bin()进行输出，才能得到负数的补码表示

# 条件语句

1. ## if语句

```python
if expression:
    expr_true_suite
12
```

- expr_true_suite 代码块只有当条件表达式 expression 结果为真时才执行，否则将继续执行紧跟在该代码块后面的语句。
- 单个 if 语句中的 expression 条件表达式可以通过布尔操作符 and，or和not 实现多重条件判断

示例

```python
if 2 > 1 and not 2 > 3:
    print('Correct Judgement!')
# Correct Judgement!
123
```

1. ## if-else语句

```python
if expression:
    expr_true_suite
else:
    expr_false_suite
1234
```

- 如果 if 语句的条件表达式结果布尔值为False，那么程序将执行 else 语句后的代码

示例
（1）f语句支持嵌套，即在一个if语句中嵌入另一个if语句，从而构成不同层次的选择结构

```python
temp = input("猜一猜小姐姐想的是哪个数字？")
guess = int(temp) # input 函数将接收的任何数据类型都默认为 str
if guess == 666:
    print("你太了解小姐姐的心思了！")
    print("哼，猜对也没有奖励！")
else:
    print("猜错了，小姐姐现在心里想的是666！")
print("游戏结束，不玩儿啦！")
12345678
```

（2）Python 使用缩进而不是大括号来标记代码块边界，因此要特别注意else的悬挂问题

- 出错情况：

```python
hi = 6
if hi > 2:
    if hi > 7:
        print('好棒!好棒!')
else:
    print('切~')
# 无输出
1234567
```

- 正常：

```python
temp = input("猜一猜小姐姐想的是哪个数字？")
guess = int(temp)
if guess > 8:
    print("大了，大了")
else:
    if guess == 8:
        print("你太了解小姐姐的心思了！")
        print("哼，猜对也没有奖励！")
    else:
        print("小了，小了")
print("游戏结束，不玩儿啦！")
1234567891011
```

1. ## if-elif-else语句

```python
if expression1:
    expr1_true_suite
elif expression2:
    expr2_true_suite
    .
    .
elif expressionN:
    exprN_true_suite
else:
    expr_false_suite
12345678910
```

- elif 语句即为 else if，用来检查多个表达式是否为真，并在为真时执行特定代码块中的代码

示例

```python
temp = input('请输入成绩:')
source = int(temp)
if 100 >= source >= 90:
    print('A')
elif 90 > source >= 80:
    print('B')
elif 80 > source >= 60:
    print('C')
elif 60 > source >= 0:
    print('D')
else:
    print('输入错误！')
'''
请输入成绩90
A
'''
12345678910111213141516
```

1. ## assert关键词

assert——“断言”，当这个关键词后边的条件结果为 False 时，程序自动崩溃并抛出AssertionError的异常

示例

```python
my_list = ['lsgogroup']
my_list.pop(0)
assert len(my_list) > 0
# AssertionError
1234
```

在进行单元测试时，assert可以用来在程序中植入检查点，只有条件结果为True，程序才能继续正常工作

```python
assert 3 > 7
# AssertionError
12
```

# 循环语句

1. ## while循环

```python
while 布尔表达式:
    代码块
12
```

- while循环的代码块会一直循环执行，直到布尔表达式的值为False
- 如果布尔表达式不带有运算符，而仅仅给出数值- 之类的条件，也是可以的：

当while后写入一个非零整数时，视为真值，执行循环体；写入0时，视为假值，不执行循环体。
也可以写入str、list或任何序列，长度非零则视为真值，执行循环体；否则视为假值，不执行循环体

示例

```python
count = 0
while count < 3:
    temp = input("猜一猜小姐姐想的是哪个数字？")
    guess = int(temp)
    if guess > 8:
        print("大了，大了")
    else:
        if guess == 8:
            print("你太了解小姐姐的心思了！")
            print("哼，猜对也没有奖励！")
            count = 3
        else:
            print("小了，小了")
    count = count + 1
print("游戏结束，不玩儿啦！")
'''
猜一猜小姐姐想的是哪个数字？8
你太了解小姐姐的心思了！
哼，猜对也没有奖励！
游戏结束，不玩儿啦！
'''
123456789101112131415161718192021
```

如果布尔表达式返回0，循环终止

```python
string = 'abcd'
while string:
    print(string)
    string = string[1:]
# abcd
# bcd
# cd
# d
12345678
```

1. ## while-else循环

```python
while 布尔表达式:
    代码块
else:
    代码块
1234
```

当while循环正常执行完的情况下，执行else输出，如果while循环中执行了跳出循环的语句，比如 break，将不执行else代码块的内容

示例
（1）无break：

```python
count = 0
while count < 5:
    print("%d is  less than 5" % count)
    count = count + 1
else:
    print("%d is not less than 5" % count)    
# 0 is  less than 5
# 1 is  less than 5
# 2 is  less than 5
# 3 is  less than 5
# 4 is  less than 5
# 5 is not less than 5
123456789101112
```

（2）有break：

```python
count = 0
while count < 5:
    print("%d is  less than 5" % count)
    count = 6
    break
else:
    print("%d is not less than 5" % count)
# 0 is  less than 5
12345678
```

1. ## for循环

for循环是迭代循环，相当于一个通用的序列迭代器，可以遍历任何有序序列，如str、list、tuple等，也可以遍历任何可迭代对象，如dict

```python
for 迭代变量 in 可迭代对象:
    代码块
12
```

每次循环，迭代变量被设置为可迭代对象的当前元素，提供给代码块使用

```python
for i in 'ILoveLSGO':
    print(i, end=' ')  # 不换行输出
# I L o v e L S G O
123
member = ['张三', '李四', '刘德华', '刘六', '周润发']
for each in member:
    print(each)

# 张三
# 李四
# 刘德华
# 刘六
# 周润发
for i in range(len(member)):
    print(member[i])
# 张三
# 李四
# 刘德华
# 刘六
# 周润发
12345678910111213141516
dic = {'a': 1, 'b': 2, 'c': 3, 'd': 4}
for key, value in dic.items():
    print(key, value, sep=':', end=' ')    
# a:1 b:2 c:3 d:4 
1234
dic = {'a': 1, 'b': 2, 'c': 3, 'd': 4}
for key in dic.keys():
    print(key, end=' ')    
# a b c d 
1234
dic = {'a': 1, 'b': 2, 'c': 3, 'd': 4}
for value in dic.values():
    print(value, end=' ')    
# 1 2 3 4
1234
```

1. ## for-else循环

```python
for 迭代变量 in 可迭代对象:
    代码块
else:
    代码块
1234
```

当for循环正常执行完的情况下，执行else输出，如果for循环中执行了跳出循环的语句，比如 break，将不执行else代码块的内容，与while - else语句一样

示例

```python
for num in range(10, 20):  # 迭代 10 到 20 之间的数字
    for i in range(2, num):  # 根据因子迭代
        if num % i == 0:  # 确定第一个因子
            j = num / i  # 计算第二个因子
            print('%d 等于 %d * %d' % (num, i, j))
            break  # 跳出当前循环
    else:  # 循环的 else 部分
        print(num, '是一个质数')
'''
10 等于 2 * 5
11 是一个质数
12 等于 2 * 6
13 是一个质数
14 等于 2 * 7
15 等于 3 * 5
16 等于 2 * 8
17 是一个质数
18 等于 2 * 9
19 是一个质数
'''
1234567891011121314151617181920
```

1. ## range()函数

```python
range([start,] stop[, step=1])
1
```

- BIF（Built-in functions）有三个参数，其中用中括号括起来的两个表示这两个参数是可选的
- step=1 表示第三个参数的默认值是1
- range 的BIF的作用是生成一个从start参数的值开始到stop参数的值结束的数字序列，该序列包含start的值但不包含stop的值

（这一部分没有特别明白，还要再看看）

示例

```python
for i in range(2, 9):  # 不包含9
    print(i)
'''
2
3
4
5
6
7
8
'''
1234567891011
for i in range(1, 10, 2):
    print(i)
'''
1
3
5
7
9
'''
123456789
```

1. ## enumerate()函数

（1）一般形式：

```python
enumerate(sequence, [start=0])
1
```

- sequence：一个序列、迭代器或其他支持迭代对象
- start：下标起始位置
- 返回 enumerate(枚举) 对象

示例

```python
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
lst = list(enumerate(seasons))
print(lst)
# [(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
lst = list(enumerate(seasons, start=1))  # 下标从 1 开始
print(lst)
# [(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
1234567
```

（2）与for循环结合使用：

```python
for i, a in enumerate(A)
    do something with a
12
```

用 enumerate(A) 返回了 A 中的元素，给该元素一个索引值 (默认从 0 开始)
此外，用 enumerate(A, j) 还可以确定索引起始值为 j

示例

```python
languages = ['Python', 'R', 'Matlab', 'C++']
for language in languages:
    print('I love', language)
print('Done!')
'''
I love Python
I love R
I love Matlab
I love C++
Done!
'''
for i, language in enumerate(languages, 2):
    print(i, 'I love', language)
print('Done!')
'''
2 I love Python
3 I love R
4 I love Matlab
5 I love C++
Done!
'''
123456789101112131415161718192021
```

1. ## break语句

前面已经提到很多次了，懂的都懂啦

1. ## continue语句

终止本轮循环开始下一轮循环

示例

```python
for i in range(10):
    if i % 2 != 0:
        print(i)
        continue
    i += 2
    print(i)
'''
2
1
4
3
6
5
8
7
10
9
'''
123456789101112131415161718
```

1. ## pass语句

pass是空语句，不做任何操作，只起到占位的作用，其作用是为了保持程序结构的完整性

如果在需要有语句的地方不写任何语句，那么解释器会提示出错，而 pass 语句就是用来解决这些问题的

示例
（1）无pass运行出错：

```python
def a_func():
# SyntaxError: unexpected EOF while parsing
12
```

（2）有pass：

```python
def a_func():
    pass
12
```

1. ## 推导式

- **列表推导式**

```python
[ expr for value in collection [if condition] ]
1
```

示例

```python
x = [-4, -2, 0, 2, 4]
y = [a * 2 for a in x]
print(y)
# [-8, -4, 0, 4, 8]
1234
x = [i ** 2 for i in range(1, 10)]
print(x)
# [1, 4, 9, 16, 25, 36, 49, 64, 81]
123
x = [(i, i ** 2) for i in range(6)]
print(x)

# [(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]
1234
x = [i for i in range(100) if (i % 2) != 0 and (i % 3) == 0]
print(x)

# [3, 9, 15, 21, 27, 33, 39, 45, 51, 57, 63, 69, 75, 81, 87, 93, 99]
1234
a = [(i, j) for i in range(0, 3) for j in range(0, 3)]
print(a)
# [(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2), (2, 0), (2, 1), (2, 2)]
123
x = [[i, j] for i in range(0, 3) for j in range(0, 3)]
print(x)
# [[0, 0], [0, 1], [0, 2], [1, 0], [1, 1], [1, 2], [2, 0], [2, 1], [2, 2]]
x[0][0] = 10
print(x)
# [[10, 0], [0, 1], [0, 2], [1, 0], [1, 1], [1, 2], [2, 0], [2, 1], [2, 2]]
123456
a = [(i, j) for i in range(0, 3) if i < 1 for j in range(0, 3) if j > 1]
print(a)
# [(0, 2)]
123
```

- **元组推导式**

```python
( expr for value in collection [if condition] )
1
```

示例

```python
a = (x for x in range(10))
print(a)

# <generator object <genexpr> at 0x0000025BE511CC48>

print(tuple(a))

# (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
12345678
```

- **字典推导式**

```python
{ key_expr: value_expr for value in collection [if condition] }
1
```

示例

```python
b = {i: i % 2 == 0 for i in range(10) if i % 3 == 0}
print(b)
# {0: True, 3: False, 6: True, 9: False}
123
```

- **集合推导式**

```python
{ expr for value in collection [if condition] }
1
```

示例

```python
c = {i for i in [1, 2, 3, 4, 5, 5, 6, 4, 3, 2, 1]}
print(c)
# {1, 2, 3, 4, 5, 6}
123
```

- **其他**
  next(iterator[, default]) Return the next item from the iterator. If default is given and the iterator is exhausted, it is returned instead of raising StopIteration.
  （这一部分不知道是什么）

示例

```python
e = (i for i in range(10))
print(e)
# <generator object <genexpr> at 0x0000007A0B8D01B0>
print(next(e))  # 0
print(next(e))  # 1
for each in e:
    print(each, end=' ')
# 2 3 4 5 6 7 8 9
12345678
s = sum([i for i in range(101)])
print(s)  
# 5050
s = sum((i for i in range(101)))
print(s)  
# 5050
123456
```

# 异常处理

在初次学习python的过程中，总会遇到许多自己不明白的错误，所以知道出现异常时的正确处理方法很重要

1. ## python标准日常总结

- **常见情况**

BaseException：所有异常的 基类
Exception：常规异常的 基类
StandardError：所有的内建标准异常的基类
ArithmeticError：所有数值计算异常的基类
FloatingPointError：浮点计算异常
OverflowError：数值运算超出最大限制
ZeroDivisionError：除数为零
AssertionError：断言语句（assert）失败
AttributeError：尝试访问未知的对象属性
EOFError：没有内建输入，到达EOF标记
EnvironmentError：操作系统异常的基类
IOError：输入/输出操作失败
OSError：操作系统产生的异常（例如打开一个不存在的文件）
WindowsError：系统调用失败
ImportError：导入模块失败的时候
KeyboardInterrupt：用户中断执行
LookupError：无效数据查询的基类
IndexError：索引超出序列的范围
KeyError：字典中查找一个不存在的关键字
MemoryError：内存溢出（可通过删除对象释放内存）
NameError：尝试访问一个不存在的变量
UnboundLocalError：访问未初始化的本地变量
ReferenceError：弱引用试图访问已经垃圾回收了的对象
RuntimeError：一般的运行时异常
NotImplementedError：尚未实现的方法
SyntaxError：语法错误导致的异常
IndentationError：缩进错误导致的异常
TabError：Tab和空格混用
SystemError：一般的解释器系统异常
TypeError：不同类型间的无效操作
ValueError：传入无效的参数
UnicodeError：Unicode相关的异常
UnicodeDecodeError：Unicode解码时的异常
UnicodeEncodeError：Unicode编码错误导致的异常
UnicodeTranslateError：Unicode转换错误导致的异常

- **异常体系内部有层次关系，Python异常体系中的部分关系如下所示：**
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200829174709840.png#pic_center)

1. ## Python标准警告总结

Warning：警告的基类
DeprecationWarning：关于被弃用的特征的警告
FutureWarning：关于构造将来语义会有改变的警告
UserWarning：用户代码生成的警告
PendingDeprecationWarning：关于特性将会被废弃的警告
RuntimeWarning：可疑的运行时行为(runtime behavior)的警告
SyntaxWarning：可疑语法的警告
ImportWarning：用于在导入模块过程中触发的警告
UnicodeWarning：与Unicode相关的警告
BytesWarning：与字节或字节码相关的警告
ResourceWarning：与资源使用相关的警告

1. ## try-except语句

```python
try:
    检测范围
except Exception[as reason]:
    出现异常后的处理代码
1234
```

- try 语句按照如下方式工作：

（1）首先，执行try子句（在关键字try和关键字except之间的语句）
（2）如果没有异常发生，忽略except子句，try子句执行后结束
（3）如果在执行try子句的过程中发生了异常，那么try子句余下的部分将被忽略
（4）如果异常的类型和except之后的名称相符，那么对应的except子句将被执行，最后执行try - except语句之后的代码
（5）如果一个异常没有与任何的except匹配，那么这个异常将会传递给上层的try中

示例

```python
try:
    f = open('test.txt')
    print(f.read())
    f.close()
except OSError:
    print('打开文件出错')
# 打开文件出错
1234567
try:
    f = open('test.txt')
    print(f.read())
    f.close()
except OSError as error:
    print('打开文件出错\n原因是：' + str(error))
# 打开文件出错
# 原因是：[Errno 2] No such file or directory: 'test.txt'
12345678
```

- 一个try语句可能包含多个except子句，分别来处理不同的特定的异常。最多只有一个分支会被执行

示例

```python
try:
    int("abc")
    s = 1 + '1'
    f = open('test.txt')
    print(f.read())
    f.close()
except OSError as error:
    print('打开文件出错\n原因是：' + str(error))
except TypeError as error:
    print('类型出错\n原因是：' + str(error))
except ValueError as error:
    print('数值出错\n原因是：' + str(error))
# 数值出错
# 原因是：invalid literal for int() with base 10: 'abc'
1234567891011121314
dict1 = {'a': 1, 'b': 2, 'v': 22}
try:
    x = dict1['y']
except LookupError:
    print('查询错误')
except KeyError:
    print('键错误')
else:
    print(x)
# 查询错误
12345678910
```

- try-except-else语句尝试查询不在dict中的键值对，从而引发了异常。这一异常准确地说应属于KeyError，但由于KeyError是LookupError的子类，且将LookupError置于KeyError之前，因此程序优先执行该except代码块。所以，使用多个except代码块时，必须坚持对其规范排序，要从最具针对性的异常到最通用的异常
  （这一部分还不算特别明白）

示例

```python
dict1 = {'a': 1, 'b': 2, 'v': 22}
try:
    x = dict1['y']
except KeyError:
    print('键错误')
except LookupError:
    print('查询错误')
else:
    print(x)
# 键错误
12345678910
```

- 一个 except 子句可以同时处理多个异常，这些异常将被放在一个括号里成为一个元组

示例

```python
try:
    s = 1 + '1'
    int("abc")
    f = open('test.txt')
    print(f.read())
    f.close()
except (OSError, TypeError, ValueError) as error:
    print('出错了！\n原因是：' + str(error))
# 出错了！
# 原因是：unsupported operand type(s) for +: 'int' and 'str'
12345678910
```

1. ## try-except-finally语句

try: 检测范围 except Exception[as reason]: 出现异常后的处理代码
finally: 无论如何都会被执行的代码

tips：不管try子句里面有没有发生异常，finally子句都会执行

示例

如果一个异常在try子句里被抛出，而又没有任何的except把它截住，那么这个异常会在finally子句执行后被抛出

```python
def divide(x, y):
    try:
        result = x / y
        print("result is", result)
    except ZeroDivisionError:
        print("division by zero!")
    finally:
        print("executing finally clause")
divide(2, 1)
# result is 2.0
# executing finally clause
divide(2, 0)
# division by zero!
# executing finally clause
divide("2", "1")
# executing finally clause
# TypeError: unsupported operand type(s) for /: 'str' and 'str'
1234567891011121314151617
```

1. ## try-except-else语句

如果在try子句执行时没有发生异常，Python将执行else语句后的语句

```python
try:
    检测范围
except:
    出现异常后的处理代码
else:
    如果没有异常执行这块代码
123456
```

使用except而不带任何异常类型，这不是一个很好的方式，我们不能通过该程序识别出具体的异常信息，因为它捕获所有的异常

try: 检测范围
except(Exception1[, Exception2[,…ExceptionN]]]): 发生以上多个异常中的一个，执行这块代码
else: 如果没有异常执行这块代码

示例

```python
try:
    fh = open("testfile.txt", "w")
    fh.write("这是一个测试文件，用于测试异常!!")
except IOError:
    print("Error: 没有找到文件或读取文件失败")
else:
    print("内容写入文件成功")
    fh.close()
# 内容写入文件成功
123456789
```

需要注意的是，else语句的存在必须以except语句的存在为前提，在没有except语句的try语句中使用else语句，会引发语法错误

1. ## raise语句

抛出一个指定的异常

示例

```python
try:
    raise NameError('HiThere')
except NameError:
    print('An exception flew by!')   
# An exception flew by!
12345
```

