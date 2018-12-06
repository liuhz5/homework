# 机器语言编程


![](https://github.com/liuhz5/hz-homework/blob/master/fengmian.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/mulu.png?raw=true)

# 一、实验目的


- 理解冯·诺伊曼计算机的结构

- 理解机器指令的构成

- 理解机器指令执行周期

- 用汇编编写简单程序

# 二、	实验步骤与结果

## 任务 1：简单程序

（1）打开网页 The PIPPIN User’s Guide ，然后输入 Program 1：Add 2 number

（2）点step after step。观察并回答下面问题：


Ⅰ. PC，IR 寄存器的作用。

- 答：

PC，程序计数器，是用来计数的，指示指令在存储器的存放位置，也就是个地址信息  
IR，指令寄存器，是用来存放指令的，存放当前正在执行的指令，包括指令的操作码，地址码，地址信息

Ⅱ.  ACC 寄存器的全称与作用。

- 答：全称：accumulator，是累加器A缩写  
作用：累加器A是一个具有特殊用途的二进制8位寄存器，专门用来存放操作数或运算结果。在CPU执行某种运算前，两个操作数中的一个通常应放在累加器A中，运算完成后累加器A中便可得到运算结果。

III.  用“LOD #3”指令的执行过程，解释Fetch-Execute周期。

答：PC 根据地址从RAM取出指令LOD #3


![](https://github.com/liuhz5/hz-homework/blob/master/1.png?raw=true)


指令先传入IR，之后传入Decoder

![](https://github.com/liuhz5/hz-homework/blob/master/2.png?raw=true)

无需取址，将数字3传入MUX ，并且ALU执行=操作，再将数字3传入ALU，运算后传入ACC

![](https://github.com/liuhz5/hz-homework/blob/master/3.png?raw=true)

![](https://github.com/liuhz5/hz-homework/blob/master/4.png?raw=true)

![](https://github.com/liuhz5/hz-homework/blob/master/5.png?raw=true)

![](https://github.com/liuhz5/hz-homework/blob/master/6.png?raw=true)


Ⅳ. 用“ADD W” 指令的执行过程，解释Fetch-Execute周期。

答：  
- PC根据地址从RAM取出指令ADD W   
指令传入IR之后传入Decoder  
指令再传给MUX，之后使ALU执行+操作，  
再将数字7传入ALU  
IR再次访问RAM中的W，从W地址中取值   
W的值传入ALU   
ALU执行加法运算，结果传入ACC

V. “LOD #3” 与 “ADD W” 指令的执行在Fetch-Execute周期级别，有什么不同。

答：
- ADD W的Fetch-Execute周期更为复杂，它两次读取RAM中的值，而LOD #3只读 取了一次RAM中的值。


（3）点击“Binary”,观察回答下面问题

Ⅰ. 写出指令 “LOD #7” 的二进制形式，按指令结构，解释每部分的含义。

答：
- 00010100 00000111  
- 第4位二进制数代表寻址模式：1表示操作数是数值，0表示操作数是该地址的内容；第5~8位二进制数代表操作码；后八位代表一个数值，或者一个内存地址。例子中表示对数值进行某项操作。


Ⅱ. 解释 RAM 的地址。

- 由于RAM是临时数据储存媒介，所以RAM中的地址都是临时的，具有易挥发性，即断电丢失。

该机器CPU是几位的？（按累加器的位数）

- 8位

写出该程序对应的 C语言表达。

```
#include<stdio.h>

int main()
{
	int W=3;
           int X=7;
           int Y;
           Y=W+X;
	        printf("%d",Y);
	      return 0;
}
```

## 任务 2：简单循环

（1） 输入程序Program 2，运行并回答问题：

Ⅰ. 用一句话总结程序的功能

- X的值从3开始，每次减1，直到x的值为0

Ⅱ. 写出对应的 c 语言程序

```
#include<stdio.h>

int main()
{
	int X=3;
    while(X>0){
	    X--;
	 }
	printf("%d",X);
	return 0;
}

```


（2） 修改该程序，用机器语言实现 10+9+8+..1 ，输出结果存放于内存 Y

Ⅰ.  写出 c 语言的计算过程

```
#include<stdio.h>

int main()
{
	int X=10;
	int Y=0;
	while(X>=0){
	    Y=Y+X;
		X--;
	}
	printf("%d",Y);
	return 0;
}

```

Ⅱ. 写出机器语言的计算过程

- 00000000 00000100 10000001  
00000010 00010001 00000001  
00000100 00001101 00001010  
00000110 00000101 10000000  
00001000 00000100 10000001  
00001010 00000000 10000000  
00001100 00000100 10000001  
00001110 00010001 00000001  
00010000 00000101 10000001  
00010010 00001100 00000000   
00010100 00001111 00000000

实验过程如下：

![](https://github.com/liuhz5/hz-homework/blob/master/7.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/8.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/9.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/10.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/11.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/12.png?raw=true)


![](https://github.com/liuhz5/hz-homework/blob/master/13.png?raw=true)



III. 用自己的语言，简单总结高级语言与机器语言的区别与联系。

答：
- 高级语言编译后转变为机械语言。  
区别：高级语言更接近自然语言，它的对象是人类，稍微了解编程的人就可以看懂;但机器语言是纯粹的二进制格式,它的对象是机器，只有具有专业知识的人才能看懂


# 三、 实验小结

在这次机器语言编程的实验中，我收获颇多。

① 我对冯·诺依曼计算机结构有了更清晰的认识，对机器语言的执行过程有了更深刻的理解。冯·诺依曼计算机主要由运算器、控制器、存储器和输入输出设备组成，它的特点是：程序以二进制代码的形式存放在存储器中；所有的指令都是由操作码和地址码组成；指令在其存储过程中按照执行的顺序进行存储；以运算器和控制器作为计算机结构的中心等。

② 机器指令起始、进行、结束的执行周期在我脑海里也更加明确、清晰。

③ 在用汇编语言编程的过程中，我明白ADD、SUB、MUL、DIV、LOD、STO、JMP、JMZ、HLT等语句的作用，并加深了它们在我脑海中的印象，也对机器语言存在的形态和它与高级语言的区别和联系理解更加深刻。










