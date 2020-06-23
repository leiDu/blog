---
title: "String"
date: 2020-05-10T22:05:13+08:00
draft: false
---

&emsp;&emsp;从概念上将，Java字符串就是Unicode字符序列。e.g:串"Java\u2122由5个Unicode 字符J a v a和TM。Java没有内置的的字符串，而是在标准Java类库中提供了一个预 定义类，很自然地叫做String。每一个用引号括起来的字符串就是String类的一个实 例。  
&emsp;&emsp;在字符串中，分为不可变字符串(String)和可变字符串(StringBuffer和StringBuilder)。  
### String

*  String的创建  
    String str = “She is my mother”;  
    String str = new String(“She is my mother”);  
    System.out.println(“She is my mother, and her name” + name);  
    通过println()里的语句，‘+’是一个连接符，如果在一条语句里，存在字符串和‘+’ ，那么这条语句就还是字符串；如果是数值(2+3)，则这时‘+’就起算术运算。  
* String的方法  
    String里面有很多的现成方法使用,如length()、split()、comparaTo()、substring() 等  
    length()方法是获取字符串的长度  
```
      private static int strLength(String str) {
          int sLength = str.length();
          return sLength;
      }
```
* split()方法是对字符串进行切割  
```
       private static void splitStr(String str) {
           String[] splits = str.split(" ");   //以空格进行切割字符串
           for(String s : splits)
           System.out.println(s);
       }
```
* compareTo()用于对子对字符串的比较  
```
       private static void compareStr(String str) {
           String s = "This is a character";
           System.out.println(str.compareTo(s));
       }
```
&emsp;&emsp; 关于String的方法可以查阅JavaAPI原码，以下不做详细讨论。  
&emsp;&emsp;创建成功的字符串对象，其长度是固定的，内容不能被改变和编译。虽然使用“+” 可以达到附加新字符或字符串的目的，但“+”就会产生一个新的String实例，会在内存 中创建心得字符串对象，如果多次对该字符串对象进行反复的修改，就会使内存的开销 增加，使内存耗尽，最终导致系统运行的崩溃。  

#### StringBuffer与StringBudilder

&emsp;&emsp;StringBuffer和StringBudilder都是可以对其字符串进行追加、增加、删除等的操 作。但要注意，StringBuffer允许采用多线程的方式执行添加或删除字符的操作 ，但效率低，而StringBuilder采用单线程来对字符进行增加和删除，效率高。 两个类的API是相同的。

#### REFERENCE
[1] 凯 S.霍斯特曼.java核心技术卷I.译(周立新).北京：机械出版社.2018重印   
[2] 明日科技.Java从入门到精通.北京：清华大学出版社.2016.

