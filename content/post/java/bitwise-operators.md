---
title: "Bitwise Operators"
date: 2020-05-10T21:43:17+08:00
draft: false
tags: ["java", "bit"]
---
&emsp;&emsp;位操作是程序设计中对位模式按位或二进制数的一元或二元的操作。  
&emsp;&emsp; 位运算中要注意：左边最高位是符号位，如果是正数，则最高位用0表示， 否则用1表示；如果是负数，则采用补码表示。  
&emsp;&emsp;在计算机中由于位数的不同所引用的二进制数也不同，在现在大多是32位和64位，以下的例子中，以8位来进行实现。 但在学习位运算时，还要先了解进制等相关的知识。
#### 进制

* 二进制  
    二进制(B)：基于为2的计数制。二进制是“逢2进1”，每一位只有0和1两种状态， 位权为2的各次幂。

* 十进制  
    十进制(D)计数方法为“逢10进1”，一个十进制数的每一位都只有10种状态，分别 用0～9等10个数码表示。

* 八进制  
    八进制(O)数的基数为8，进位规则为“逢8进1”，使用0~7等8个数码，位权是8的 各次幂。

* 十六进制  
    十六进制(H)的基数是16，进位规则为“逢16进1”，使用0~9，A～F等16个数码， 位权是16的各次幂。

#### 二进制原码、反码、补码

* 原码  
    原码是一种计算机中对数字的二进制定点表示方法。规则：如果数值是正数，则 最高符号位是0，如果是负数，最高符号位是1，其他位不变。

* 反码  
    规则：如果数值是正数，则反码和原码相同；如果是负数，则最高符号位是1，其 它位分别取反。

* 补码  
    补码是计算机表示数据的一般形式，规则是如果是正数，则补码和原码一样；如 果是负数，则在反码的基础上+1。

* 原码、反码、补码总结  
    如果所求的数值为正数，则原码、反码、补码都是相同的；如果所求的数值为负 数，则原码的符号位是1，不是0；反码符号位不变，其余位取反；补码是在反码的基础 上+1。  
    e.g 求8和-8的原码、反码和补码

|数值    |	原码   |	反码       | 	补码       |
| :-:    |  :-:        |  :-:              |  :-:          |
|8 	 |0 000 1000   |	0 000 1000 |	0 000 1000 |
|-8 	 |1 000 1000   |	1 111 0111 |    1 000 1001 |

#### 位运算

* 按位与  
    按位与运算符(&)是一个双目运算符，运算规则：如果相与的两个或多个结 果位是1，则返回1，如果相与的两个或多个结果位是0，则返回0；如果相与的结 果位一个是1，一个是0，则返回0。  
    e.g: 求2 & 5的结果

|数字| 	运算符| 二进制值        |
| :-:|  :-:   |  :-:            |
|2   | 	      |	0 0 0 0 0 0 1 0 |
|5   | 	&     |	0 0 0 0 0 1 0 1 |
|——— |	———–  |	——————-         |
|    |        |0 0 0 0 0 0 0 0  |

* 按位或  
    按位或运算符(|)是一个双目运算符，运算规则：如果相或的两个或多个结 果位是1，则返回1；如果相或的两个或多个结果位是0，则返回0；如果相或的结 果位一个是1，一个是0，而最后也只能返回1。  
    e.g 求2 & 5的结果

|数字   |	运算符    |	二进制值   |
| :-:   |  :-:            |  :-:           |
|2 	|	          |0 0 0 0 0 0 1 0 |
|5 	|  &              |0 0 0 0 0 1 0 1 |
|——–    |———– 	          |——————-         |
|	|	          |0 0 0 0 0 1 1 1 |
|最终结果| 	： 	  |7               |

* 按位异或  
    按位异或运算符(^)是一个双目运算符，运算规则：如果异或的两个或多个结 果位是1，则返回0，如果异或两个或多个结果位是0，则返回0；如果异或的结果位 一个是1，一个是0，则返回1。  
    e.g 求2 ^ 5的结果

|数字 	|运算符 |	二进制值|
| :-:   |  :-:  |  :-:          |
|2      |	|0 0 0 0 0 0 1 0|
|5 	|^ 	|0 0 0 0 0 1 0 1|
|——–    |  ———– |	——————- |
|	|	|0 0 0 0 0 1 1 1|
最终结果|     ：|          7    |

* 按位取反  
    取反运算符(~),也叫按位非运算，是一个单目运算符，把0变成1，把1变成0。  
    e.g 求 ~7的结果

|数字 |	运算符| 	二进制值|
| :-: |  :-:  |  :-:            |
|7    |~      |	0 0 0 0 0 1 1 1 |
|——–  |———–   |——————-          |
|     |	      |1 1 1 1 1 0 0 0  |

* 左位移(正负数皆补0）  
    左位移使用"«"符号，e.g：a « b，a代表数值，b是代码所要移动的位 数；规则:先把a转换成二进制数，然后根据b向左移动b位，而移动后右边会空出 b位，则用0来填充b位。  
    e.g 求 6 « 2和 -6 « 2的结果  

|数值   |移动位数| 二进制        |
| :-:   |  :-:   |  :-:          |
|6 	|	 |0 0 0 0 0 1 1 0|
|	|2 	 |0 0 0 1 1 0 0 0|
|结果   |    ：  |	24       |
|—— 	|———— 	 |——————         |
|-6     |	 |1 0 0 0 0 1 1 0|
|	|2 	 |1 1 1 0 1 0 0 0|
|结果   |     ： | 	-24      |

* 右位移(正数左补0，负数左补1）  
    右位移使用"»"符号，e.g：a » b，a代表数值，b是代表所要移动的位数； 规则：先把二进制转化成二进制，然后根据b向右移动b位，而移动后左边会空出b位 ，则用0(为正时，而为负时，用1来填充)来填充b位。  
    e.g 求 6 » 2和 -6 » 2的结果  

|数值 |	移动位数 |  二进制       |
| :-: |  :-:     |  :-:          |
|6    | 	 |0 0 0 0 0 1 1 0|
|     |2 	 |0 0 0 0 0 0 0 1|
|结果 | :        |	1        |
|——   |————      | ——————        |
|-6   |	         |1 0 0 0 0 1 1 0|
|     |2 	 |1 1 1 1 1 1 1 0|
|结果 |	:        | 	-2       |

* 无符号右移  
    无符号右移使用"»>"符号，  

* 总结  
    通过有符号左移和有符号右移，可以得到：一个数左移n位，就是将这个数乘以 2^n；一个数右移n位，就是将这个数除以2^n。  
    右位移和无符号右移的区别：右位移，如果参与运算的数字是正数，则在最高位 补0；如果参与运算的数字是负数，则最高位补1；而无符号右移不管是正数，还是负 数，都在最高位补0。  

#### REFERENCE

[1] 周延怀，崔海源.大学计算机基础及应用教程.北京：清华大学出版社.2016.  
[2] Nicholas C.Zakas.JavaScript高级程序设计.译.北京：人民邮电出版社.2017.  
[3] Java从入门到精通、明日科技编著.北京：清华大学出版社.2016.  
[4] 王长青，韩海玲.C语言开发从入门到精通.北京：人民邮电出版社.2016.  
[5] https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators  
[6] https://blog.csdn.net/u013372487/article/details/45498677  
