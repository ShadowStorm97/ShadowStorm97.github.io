# 彻底搞懂二进制

## 什么是进制？

使用`阿拉伯数字`（0-9）,是在数学上对现实时间中计数这一需求的的一种表示方法。具体的使用个位，十位，百位，千位对数值进行描述。

- 在阿拉伯数字出现之前，也有过罗马数字，使用 I,II,III,V,VI,X 来表示。似乎看起来阿拉伯数字书写更加简单方便，于是在全世界范围内流行了起来并最终成为了通用数字标准。
- 如果想表示的数字不多，貌似0-9就够用。可现实世界里，往往还是有一些大额的数字，那怎么表示呢？
- 还是使用0-9来表示基础数字，而使用进制来赋予不同位的数字使其具有不同的含义。
日常生活中使用的是十进制。如2345，千位为2，百位为3，十位为4，个位为5。以十作为进制单位，逢十才进一。

所以也可以这样写：
```
2345 
    = 2*1000 + 3*100 + 4*10 + 5*1           
    = 2*10^3 + 3*10^2 + 4*10^1 + 5*10^0
```
### 什么是二进制？

十进制掌握后，将进制由十改为二，由于是二进制，基础数字只存在0和1了，因为每逢二就进位加一了。

如二进制的1001，也可以这样写：
```
1001 
    = 1*8 + 0*4 + 0*2 + 1*1     
    = 1*2^3 + 0*2^2 + 0*2^1 + 1*2^0
```
> 可以看出二进制的1001 等价于十进制的9



### 有哪些进制？

以下为常见的进制：

> 2进制、8进制、10进制、16进制

不常见进制：

> 26进制、32进制、36进制、52进制、58进制、62进制

## 为什么是二进制？



### 为什么计算机使用二进制？

- 现代计算机使用二极管来表示0和1两种状态。由于硬件实现的制约，无法表示更多的状态。
- 二进制更稳定，抗干扰能力比其他进制强，毕竟只有两种状态。
- 硬件实现起来也更加的简单，如果使用十进制，硬件实现会非常复杂，可靠性上会有很大的疑问。


### 二进制实现有什么优点？

- 天然支持逻辑运算，0和1，刚好可以表示逻辑运算中的真和假
- 加减乘除的操作都可以通过0和1模拟，运算效率高


## 位运算是什么玩意？

### 左、右移是什么?

- 左移代表将二进制数统一向左偏移一位，末尾补0
- 左移等价于将原数字的值乘以二
- 右移代表将二进制数统一向右偏移一位，由于首位为符号位，所以右移一般有逻辑右移和算术右移两种操作
- 右移等价于将原数字的值除以二
- 逻辑右移在统一向右移动一位后，符号位值为零
- 算术右移在统一向右移动一位后，将符号位拷贝到首位
### 与、或、异或是什么？

#### 与运算

> 与运算其实就是常见的`&`操作符，只有运算符两边都为真才为真。
```
1010 & 0101  
            =  1 0 1 0        0 1 0 1                          
            =  0 0 0 0 
            =  0
```
#### 或运算

> 或运算一样是常见的`|`操作符，只要运算符两 边有一个为真就为真
```
1010 | 0101  
            =  1 0 1 0        0 1 0 1                          
            =  1 1 1 1 
            =  15
```
#### 异或运算

> 异或运算`^`相较于与或运算不太常见，只有运算符两边都相同才为真
```
1010 ^ 0101  
            =  1 0 1 0        0 1 0 1                          
            =  0 0 0 0 = 0
```
### 位运算能做什么？

> 往往用在一些取巧的地方，掌握好位运算，绝对是装逼的入门技巧。

### 不用额外变量交换两个数

例如交换两个整数a=10100001，b=00000110的值，可通过下列语句实现：
```
a = a^b； 　　

a=10100111b = b^a； 　　

b=10100001a = a^b； 　　

a=00000110

```
### 解算法题

318.最大单词长度乘积:https://leetcode-cn.com/problems/maximum-product-of-word-lengths/