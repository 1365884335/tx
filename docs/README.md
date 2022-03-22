# docsify 知识库
官方文档 [docsify](https://docsify.js.org/#/zh-cn/quickstart)
## 需要环境
> 安装 [nodejs](https://nodejs.org/en/)

## 打开命令行
> win+R打开运行窗，输入 [cmd](https://baike.baidu.com/item/%E5%91%BD%E4%BB%A4%E6%8F%90%E7%A4%BA%E7%AC%A6?fromtitle=CMD&fromid=1193011) 后 回车 

## 安装docsify
```
npm install -g docsify-cli
```
## 查看docsify版本
```
docsify -y
```
## 部署docsify
> - 创建文件夹 
> - cd 你创建的目录路径

## 初始化docsify
```
docsify init
```
> 输入 y 确
```
 index.html 入口文件
 README.md 会做为主页内容渲染
 .nojekyll 用于阻止 GitHub Pages 会忽略掉下划线开头的文件
```
## 启用docsify
```
docsify serve
```
## Github Pages
> - *请保留  **.nojekyll** 文件 （用于阻止 GitHub Pages 会忽略掉下划线开头的文件）
> - *详细参考 [docsify + Github Pages 教程](https://blog.csdn.net/m0_37965018/article/details/103841362)

#  一、Java初识

## 	1.Java是什么

​		一门高级的**计算机**编程**语言**

​		其他编程语言	C  C++  C#  Python  Go   JavaScript

​		Java是进入互联网领域非常好的语言



​		写给计算机看---指令

​		硬盘---计算机存储的位置



## 	2.第一个计算机指令

### 1）Java源文件

```java
public class Test{
	public static void main(String[] args){
		System.out.println("zzt很帅");
	}
}
```

​			创建文件		.java

​			class

​			名字------->

​					英文		26	字母  大小写区分开		大小写敏感		首字母大写TestOne

​					数字		0-9	不能开头		Test1

​					符号		$  _

​					其他文字		中文/日文-----强烈不推荐   当做**不**可以

### 2)	程序执行的原理

![编译执行原理](C:\Users\Duyi Education\Desktop\新版引流课笔记\编译执行原理.jpg)首先补充几个dos指令

​	切换盘符    盘符名   d: 回车

​	进入文件夹    cd 文件夹名字

​	编译文件		javac 文件全名     Test.java

​	执行指令		java  类名

​	输出语句中含有中文，可能会产生一个乱码的问题

​				如果有乱码问题，可以在编译时   javac Test.java -encoding UTF-8 / GBK

​				方式二，我们修改了记事本中自己的字符集(ANSI--->windows)

### 3）一个用于计算的小程序

```java
import java.util.*;

class Calculation{
	public static void main(String[] args){
		//让计算机帮我做一个数学运算  1+2	规定1+
		Scanner input = new Scanner(System.in);
		System.out.println("请您输入一个要计算的数字");
		int one = input.nextInt();//input小人开启一个通道，帮你读取输入的一个数字
		System.out.println("请您输入二个要计算的数字");
		int two = input.nextInt();//input小人开启一个通道，帮你读取输入的二个数字
		System.out.println("请您输入一个符号");
		int operator = input.nextInt();//input小人开启一个通道，帮你读取输入的符号
		//	规定1代表+ 2- 3* 4/	10
		if(operator==1){
			System.out.println("经过我精心的计算，得到一个结果");
			System.out.println(one + two);
		}else if(operator==2){
			System.out.println(one - two);
		}else if(operator==3){
			System.out.println(one * two);
		}else if(operator==4){
			System.out.println(one / two);
		}else{
			System.out.println("你丫有病啊，不要捣乱！！！");
		}
	}
}
```

### 4）基于窗口的计算器程序

```java
import javax.swing.*;

class TestFrame{
	public static void main(String[] args){
		//1.画一个窗口(桌子)
		JFrame frame = new JFrame("zzt's calculation");
		JPanel panel = new JPanel();
		//2.在窗口上画组件  文本框 one two
		JTextField oneField = new JTextField(10);
		JTextField twoField = new JTextField(10);
		JTextField resultField = new JTextField(10);
		//3.在窗口上画组件  按钮 + - * /
		JButton add = new JButton("+");
		JButton substract = new JButton("-");
		JButton multiply = new JButton("*");
		JButton divide = new JButton("/");
		//3.调整摆放组件位置
		panel.setLayout(null);
		oneField.setBounds(10,10,150,20);
		twoField.setBounds(10,40,150,20);
		add.setBounds(10,70,50,20);
		substract.setBounds(70,70,50,20);
		multiply.setBounds(10,130,50,20);
		divide.setBounds(10,160,50,20);
		resultField.setBounds(10,190,150,20);
		//4.将这些组件组合在一起
		panel.add(oneField);
		panel.add(twoField);
		panel.add(add);
		panel.add(substract);
		panel.add(multiply);
		panel.add(divide);
		panel.add(resultField);
		frame.add(panel);
		//5.添加一个功能
		add.addActionListener(e->{
			//获取文本框的文字
			int one = Integer.parseInt(oneField.getText());
			int two = Integer.parseInt(twoField.getText());
			//将结果再存回去
			resultField.setText(String.valueOf(one+two));
		});
		//6.让窗口展示出来
		frame.setBounds(500,260,300,260);
		frame.setVisible(true);
		frame.setDefaultCloseOperation(3);
	}
}
```



# 二、Java语法结构及各种概念

## 1.变量，常量

​	变量(空间)，容器(装东西)

​	空间里存储什么类型的东西？

​	**如何学会定义变量**

​	数据类型  变量名字;		class 类名 ---- 规约  英文 数字 $ _ 

​			就是英文  区分大小写   

​			类名字首字母大写，两个单词，两个都大写   Test   TestOne

​			变量名字 首字母小写，第二个单词之后的每一个单词首字母大写，  test    testOneTwoThreeFourFive

​			驼峰

​	数据类型

​			基本数据类型-----8个

​				整数-----  byte short int long

​				小数-----  float double

​				字符-----  char

​				布尔-----  boolean		true   false

​			引用数据类型----无限个(自己定义)

​				[] 数组

​				class  类				abstract class 抽象类

​				interface  接口

​				enum  枚举

​				@interface  注解



​		int a = 18;

​		char c = '郑';

​		String b = "zzt";

---------------------------------------------------------

数据类型，类型转换

语法结构，if，switch，for，while。。。

数组使用

面向对象



## 2.基本数据类型及转化问题

​		基本类型---8

​			整型----	byte   short   int   long			int

​							-128  127

​							-32768   32767

​							-2147483648	2147483647

​							2的64次方

​			浮点----  float   double		盒饭

-----------------

​			类型转化问题：		数据存储的空间发生转化

​						byte x = 10；

​						int y = x;		



​						int x = 10;

​						byte y = (byte)x;	

​						======================================

​						float x = 3.4f;

​						double y = x;



​						double x = 3.4;

​						float y = (float)x;

​						=======================================

​						int x = 10;

​						float y = x;

​			

​						float x = 3.4;

​						int y = (int)y;

----------------

​			字符		字   符号    '我'  'a'  '+'   '1'

​					'a'		0010010101010101010       97				ASCII    GBK   UTF-8

​				char x = 'a';

​				int y = x;		97



​				int x = 97;

​				char y = (char)x;		a

-----------------

​			布尔	boolean 		true   false

​				true---1



## 3.运算符号的问题

### 		1)**算术运算符**

​			+ - * / %(取余数)     ++自增1   --自减1      int x = 1;     ++x; 

### 		2)赋值运算符

​		变量空间	=   值		input.nextInt();

​			+=   -=  *=  /=  %=			int x = 1;	x+=5;		x+=1;

### 		3)比较运算符(关系)

​			元素==元素  ？boolean值

​			>   >=    <   <=   ==   3!=4

### 		4)逻辑运算符

​			&逻辑与  |逻辑或  ^逻辑异或   !逻辑非    

​			&&短路与    ||短路或

​			3>2  &   元素

​     	   boolean   &    boolean   =   boolean		与    和  并且  同时

​			3>2   &   3<4

​			true  &   true   =  true    

​			前后两个条件同时满足，最终结果才可以true，有一个条件不满足，最终就不行false

------------------------

​			|逻辑或		或   或者

​			3>4   |   3>2

​			false  |  true = true

​			前后两个条件，有一个满足，最终就可以true，两个条件都不满足，最终就不行false

------------------

​			^异或		异或----我不喜欢，专治强迫症

​			前后两个条件，只要两个条件长得不一样，最终就可以啦true，两个条件长得一样，最终不行false

​			3>2  ^  3<4

​			true ^  true  =  false

------------

​			!(3>4) = true

--------------

​			&&短路与		初中物理---电路		

​				1.到底短路的是什么?		计算过程

​				2.什么时候发生短路?

​			3>2  &&  3<4				与 两个条件都需要满足		狂风暴雨   如果第一个已经不满足啦，才会发生短路

​			true &&  true				短路的是第二个以后表达式的计算过程

​			= false

-------------

​			||短路或			有一个条件满足，最终就满足啦，如果第一个条件已经是true，后续所有就发生短路	

### 		5)位运算		

​			&按位与   |按位或   ^按位异或   ~按位取反   <<按位左位移   >>按位右位移    >>>无符号右位移

​			二进制



## 4.语法结构之if语句

### 		1）语法结构

​		if(boolean类型的结果)		true，3>2，3>2&&3<4

​			单行语句;	{多行语句}



​		if(){

​			System.out.println();

​		}

​		

​		if()

​			System.out.println();

​		System.out.println();

​				

​		int a = 1;

​		if(a>2){

​			执行

​		}



​		if(boolean结果)

​			执行

​		else

​			执行

------------------

​		学生的成绩   score

​		int score = 50;

​		if(score>=60){

​			System.out.print("及格");

​		}



​		int score = 9;

​		if(score>=60){

​			System.out.println("及格");

​		}else{

​			System.out.println("不及格");

​		}

----------------------------------------------------------------------------------------------------

​	着重强调一下下面这个写法

​		int score = 90;

​		if(score<60){		0---60  逻辑

​			挨揍啦

​		}else if(满分){//嵌套

​			奖励

​		}else if(80--100之间){

​			小小的奖励

​		}else{

​			再接再厉

​		}		

小任务：将刚才上述这个判断分数的小例子，用真正计算机的代码实现，Scanner

### 2）语法结构之if小练习

```java
import java.util.*;

class TestIf{
	public static void main(String[] args){
		//小任务
		//设计一个小程序，可以帮助我学习英文
		//	星期	1---Monday
		Scanner input = new Scanner(System.in);
		System.out.println("请您输入一个数字，我帮您输出对应的英文");
		int day = input.nextInt();
		if(day==1){
			System.out.println("Monday");
		}else if(day==2){
			System.out.println("Tuesday");
		}else if(day==3){
			System.out.println("Wednesday");
		}else if(day==4){
			System.out.println("Thursday");
		}else if(day==5){
			System.out.println("Firday");
		}else if(day==6){
			System.out.println("Saturday");
		}else if(day==7){
			System.out.println("Sunday");
		}else{
			System.out.println("你丫有病啊!!!");
		}

	}
}
```

扩展：学生成绩score，输入一个month（季度  345春天  678夏天 9 10 11秋天 12 1 2冬天  其他），逻辑 符号



## 5.语法结构之switch语句

### 	1）语法结构

switch(值){			值  byte short int  char    String  “”    enum枚举		10,10/2,  x+2-3/4

case 值1:

​		执行1;

case 值2:

​		执行;

default:

​		执行;

}								

​		分支结构    if单分支     switch多分支(穿透)

--------------------------

int x = 1;

switch(x){

case 1:

​	输出1;

​	break;//不是必须添加的   表示停止 终断于此					学习循环 break可以终止循环

case 2:

​	输出2;

case 3:

​	输出3;

default:

​	other;

}

### 	2）语法结构之switch小练习

```java
import java.util.*;

class TestSwitch{
	public static void main(String[] args){
		//利用switch实现一个判断季节的小案例？？？	345春 678夏 9 10 11秋 12 1 2冬天
		Scanner input = new Scanner(System.in);
		System.out.println("请您输入一个月份，我帮您做判断");
		int month = input.nextInt();//120
		//优化的问题	代码冗余  性能问题  内存占用
		switch(month){
			case 3:
			case 4:
			case 5:
				System.out.println("Spring");
				break;
			case 6:
			case 7:
			case 8:
				System.out.println("Summer");
				break;
			case 9:
			case 10:
			case 11:
				System.out.println("秋天");
				break;
			case 12:
			case 1:
			case 2:
				System.out.println("冬天");//Winter
				break;
			default:
				System.out.println("你丫有病啊!!!");
				break;
		}
		
	}
}
```



## 6.语法结构之循环结构

### 		1）语法结构

​		喝酒  5kg

​		减肥  跑圈

​		操场  400米    3圈1200

​		重复 周而复始     每一次重复  一件新的事情   之前事情长得一样



​		1.从哪儿开始         起点

​		2.3圈  1200  目标  终点

​		3.变化的过程        变化量

​		4.跑步					执行的过程

-----------------------

​		for(){

​		}



​		while(){

​		}



​		do{

​		}while();

----------------------------

​	循环的三要素   四要素

​	for( 1初始值 ; 258终点判定条件 ; 47变化量 ){

​			36执行体;

​	}

​	思考题：利用循环实现一个小学数学知识，乘法表，先写一个简单的循环，夸dmc三次

### 2）语法结构之for小练习

```java
class Test99{
	public static void main(String[] args){
		//实现一个9*9乘法表的打印
		for(int a=1;a<=9;a++){//目的是控制计算机，让它帮我们重复执行9次一样的事情(9行输出)
			//某一行的事情?? 打印	3行   表达式
			for(int b=1;b<=a;b++){//目的是控制计算机，让它帮我们重复 n 次一样的事情(一个表达式)
				//某一行的某一个表达式输出  表达式如何表示
				System.out.print(b+"*"+a+"="+(b*a)+"\t");//Tab  转义字符  \n \r
			}
			//这一行的所有表达式都输出完事啦，整体换一次行
			System.out.println();
		}
	}
}

	/*
		1*1=1
		1*2=2 2*2=4
		1*3=3 2*3=6 3*3=9
	     被乘数   乘数   积
		b + "*" + a + "=" + (b*a)
	*/
```

### 3）语法结构之while

​		1初始化;  

​		for( ; 258终点判定条件 ; ){

​			36执行;

​			 47变化量

​		}

---------------------

​		初始值

​		while(终点判定条件){			//不太知道最终执行的次数

​			执行

​			变化量;

​		}

### 4）语法结构之do...while

​		初始值;

​		do{

​			执行

​			变化量;

​		}while(终点判定条件);

------------------------

​		int x = 10;

​		while(x<=3){		跑步3次  判断4次   第四次没满足不再执行啦

​			跑步;

​			x++;

​		}

----------------------

​		int x = 10;

​		do{

​			跑步;				跑步3次   判断3次   

​			x++;

​		}while(x<=3);

### 5）非常重要的关键字 break & 标记

​		通过人为的一些干预，让原本可以正常执行的循环，终断

​		数3 + 数7

​		100开始 找		100---1000		找一个满足上述条件的数    不找啦    

```java
class TestBreak{
	public static void main(String[] args){
		//从100--1000之内，找第一个数
		//满足即被3 又被7整除的数
		for(int number=100;number<=999;number++){
			if(number%3==0 && number%7==0){
				System.out.println("作弊成功，找到啦，记住这个数是"+number);
				break;//注意，终断的是循环，不是if
			}
		}
	}
}
```

​		zzt:while(true){						标记

​			switch(每次找10个){

​			case 

​				break;

​			case 

​				break zzt;

​			}

​		}

--------------------------

​		over:for(){		100层

​			for(){	每层的100个房间

​				if(){

​					找到dmc

​					break over;

​				}

​			}

​		}

​		

# 三、数组的使用

## 1.数组的特点

​	数组：组 一堆 数 数据

​			是用来存储一组相同数据类型的容器

​	变量：容器

​			变量：只能存储一个数据		数组：可以存储多个数据(数据类型一致)



​	dmc:自己开一个 小摊---一张桌			变量

​			int x = 10;

​			int[] y = new int[]{10,20,30,40,50};

<img src="C:\Users\Duyi Education\Desktop\新版引流课笔记\数组的存储原理.jpg" alt="数组的存储原理" style="zoom:50%;" />

## 	2.数组的语法		

​		int x = 10;

​		int[] y = new int[]{10,20,30,40,50};

​		通过元素在数组中的位置来进行访问------索引位置		5个  0 1 2 3 4号

​		int v = y[0];

​		y[0] = 100;			y[5]	小异常  ArrayIndexOutOfBoundsException



​		数组的初始化

​			静态初始化		看见长度(几个)，看见元素(10,20,30)

​			动态初始化		int[] z = new int[10];		只有长度，没有元素(默认值)



​		将数组中的每一个位置元素都拉出来看一看???

## 3.数组的遍历

​	数组遍历的代码：

```java
public class TestArray{
	public static void main(String[] args){
		//1.创建一个数组----静态/动态
		String[] array;
		array = new String[]{"zzt1","zzt2","zzt3","zzt4","zzt5"};
		//2.将数组中的每一个元素拿出来看一看
		//想要找寻数组中的真实元素，  引导员-位置-元素		长度 array.length
		for(int index=0;index<array.length;index++){
			String value = array[index];
			System.out.println(value);
		}
		System.out.println("===华丽的分隔符===");
		//增强for	forEach
		for(String value : array){
			System.out.println(value);
		}
	}
}
```

## 4.数组的应用

​	dmc开店第一弹(循环向数组中插入数据--旧数组扩容)

```java
import java.util.Scanner;

public class DmcStore{
	public static void main(String[] args){
		//1.dmc开一个新的店	没有人
		String[] store = new String[5];		//创建之后长度是不能再次发生改变
		//记录该存储的位置
		int index = 0;
		//2.输入每一个新来的人	去
		Scanner input = new Scanner(System.in);
		while(true){
			System.out.println("贵宾一位，请出示手牌--名字");
			String name = input.nextLine();
			//判断name是不是zzt
			if(name.equals("zzt")){
				break;
			}
			//3.将新来的人存入店中
			//在存放之前，先做一个严谨的判断，店的容量够不够
			if(index >= store.length){//容量不够啦，该怎么办，扩容
				//店面升级，扩容(找了一个新的店铺)
				String[] newStore = new String[store.length*2];
				//将原来店中的人挨个拎出来，存入新店中
				for(int i=0;i<store.length;i++){
					newStore[i] = store[i];
				}
				store = newStore;
			}
			store[index++] = name;		//如果按照现在的情况，输入6个人，数组越界ArrayIndexOutOfBoundsExcetion
		}
		System.out.println("今天不接客啦，就这些人");
		//最终做一个小的验证，遍历所有数组元素看一看
		for(String v:store){
			System.out.println(v);
		}

	}
}
```

## 5.多维数组的特点

​	不要理解为是一个新的知识，其实就是一个数组，数组里面存储的元素发生了变化

​	数组中的数组，只不过我们在找寻元素的时候，元素不是直接存值的(还需要再次找寻)

​			数组创建，如何访问元素，如何遍历

<img src="C:\Users\Duyi Education\Desktop\新版引流课笔记\二维数组的存储原理.jpg" style="zoom:50%;" />

## 	6.多维数组的语法

​		1.定义，初始化

​				静态			 int[] [] array = new int[] []{{10,20,30},{20,40},{30,40,50,60,70,100}};

​				动态			 

​							int[] [] array = new int[3] [2];

​							                  <img src="C:\Users\Duyi Education\Desktop\新版引流课笔记\二维数组new[3][2].png" style="zoom:50%;" />

​							int[] [] array = new int[3] [];

<img src="C:\Users\Duyi Education\Desktop\新版引流课笔记\二维数组new[3][].png" style="zoom:50%;" />

​		2.如何访问元素----通过索引位置

​				int[] [] array = new int[] []{{10,20,30},{20,40},{30,40,50,60,70,100}};
​				int value = array[1] [1];

​				array[2] [5] =1000;

​		3.遍历轮询

```java
public class TestArray2{
	public static void main(String[] args){
		int[][] array = new int[][]{{10,20,30},{20,40},{30,40,50,60,70,100}};
		for(int i=0;i<array.length;i++){
			for(int j=0;j<array[i].length;j++){
				int value = array[i][j];
				System.out.print(value+" ");
			}
			System.out.println();
		}
		System.out.println("===分隔符===");
		for(int[] arr : array){
			//System.out.println(arr);	// [I @ 23e45f
			for(int value : arr){
				System.out.print(value+" ");
			}
			System.out.println();
		}
	}
}
```

## 	7.关于空指针问题

```java
public class TestArrayNull{
	public static void main(String[] args){
		//数组的动态初始化，只有长度，没有元素(其实是存在默认值)
		//int[] array = new int[3];	//int-0 float-0.0 boolean-false char0-字
		//做一个遍历			//其他的类型都是引用类型 null
		//for(int value:array){
		//	System.out.println(value);
		//}

		int[][] array = new int[3][];
		//array[0][0] = 100;	//int[]     NullPointerException	很多新的引用数据类型
	}
}
```

## 8.关于多维数组的练习(二维数组)

dmc开店第二弹(循环向数组中插入数据--新数组)

```java
import java.util.Scanner;

public class DmcStore2{
	public static void main(String[] args){
		//1.dmc开一个店
		String[][] store = new String[3][];
		//创建一个小分店
		store[0] = new String[5];
		//2.让新的贵宾进来
		Scanner input = new Scanner(System.in);
		int i = 0;//某一个店的位置
		int j = 0;//当前这个店中桌/屋的位置
		while(true){
			System.out.println("贵宾一位，请说出你的名字");
			String name = input.nextLine();
			if(name.equals("zzt")){
				break;
			}
			//严谨的判断，店的位置是否有足够的
			if(j >= store[i].length){
				//当前门店的下一个门店，创建一个新的数组
				store[i+1] = new String[3];
				//让店的位置向后移动一个
				i++;
				//让j的记录重新来
				j = 0;
			}
			//3.将这个贵宾存入店
			store[i][j++] = name;
		}
		System.out.println("开业大吉，最后看一看");
		for(int a=0;a<=i;a++){//当前开业的所有门店遍历一下
			for(int b=0;(a<i&&b<store[a].length)||(a==i&&b<j);b++){
				System.out.print(store[a][b]+" ");
			}
			System.out.println();
		}
	}
}
```



​		







