Java基础案例教程

## Java语言的历史及开发工具

### java的运行机制

+ 运行java程序，必须经过编译和运行文件。将 **`.java`源文件进行 编译** ，生成 `.class`**字节码** 文件
+ **java虚拟机** 首先将编译好的字节码文件加载到内存，这个过程叫做 **类加载** ，由 **类加载器** 完成
+ **虚拟机** 对类进行解释执行，可以看到运行结果

> **java程序** 是由虚拟机进行解释执行，非操作系统，这样即可实现跨平台，实现了 `Java语言` 具有的 write once,run anywhere.

![1551152063636](Java基础案例教程.assets/1551152063636.png)







### Eclipse开发工具

+ 集成开发工具可以提高程序的开发效率，并且容易排错。`IDE`(Integrated Development Environment)
+ `Eclipse` 是IBM开发的成熟且功能完整的IDE **集成开发环境**，**开源的，基于java的可扩展开发平台**，其强大的 **代码编排** 功能，可以帮助开发完成 **语法修正、代码修正、补全文字、信息提示** 等编码工作。
+ `Eclipse` 的设计思想是 **一切皆插件**， 它只是一个框架和一组服务，所有的功能是将 **插件** 加入到 `Eclipse框架` 实现



#### Eclipse软件使用

+ 安装软件
+ 设置工作区
+ `Eclipse`工作台主要由 **标题栏、菜单栏、工具栏、透视图** 4部分组成

![1551154822956](Java基础案例教程.assets/1551154822956.png)

+ 工作台的主要视图的作用：
  + Package Explorer（包资源管理区视图）：用来显示项目文件的组成结构
  + Editor（文本编辑器）：用来编写代码的区域
  + Problems（问题视图）：显示项目中的一些警告和错误
  + Console（控制台视图）：显示程序运行时的输出信息、异常和错误
  + Outline（大纲视图）：显示代码中类的结构

> ==视图==可以有自己独立的菜单和工具栏，既可单独出现，也可与其他视图叠放，并可以通过 **拖动** 随意改变布局的位置



#### Eclipse透视图

+ **透视图（Perspective）** 是比视图更大的一种概念，用于定义工作台窗口中视图的初始位置和布局，目的在于完成特定类型的任务或特定类型的资源
+ `Eclipse`开发环境提供几种常用的透视图：Java透视图，资源透视图、调试透视图、小组同步透视图

![1551156070803](Java基础案例教程.assets/1551156070803.png)

+ 如果不小心乱动了透视图，可使用 `Reset Perspective` 来重置**默认的透视图**





#### 使用Eclipse创建程序

1. 创建Java项目

![1551156540953](Java基础案例教程.assets/1551156540953.png)

2. 在项目下创建包

   在src文件夹下创建Package

![1551156664633](Java基础案例教程.assets/1551156664633.png)

3. 在包下创建java的类

![1551156709896](Java基础案例教程.assets/1551156709896.png)

4.编写代码，运行程序`Run As Java Application `

> :warning:Eclipse中提供显示行号的功能，鼠标右键单击文本编辑器左侧的空白，在弹出的窗口中选中 `Show Line Numbers`

##### 包的定义与使用

+ 在程序的开头，我们可能会使用其他其他包或者其他包里的某些类
  + `package cn.test.chapter01`,使用package关键字声明包
  + `import  chapter01.class`，导入包里的某些类
  + `import chapter01.*`,导入该包下的所有类







## Java语言编程基础

### java的基础语法

#### Java程序的基本框架

```java
//修饰符 class 类名{程序代码}
public class HelloWorld{
    public static void main(String[] args){
        System.out.println("这是第一个Java程序！")；
    }
}
```

+ Java程序中一句连续的字符串不能分开在两行书写，如果太长要连接，使用`+` 号

```java
System.out.println("这是一个"+
                  "java程序")；
```



#### Java注释

+ 单行注释  `// 这是单行注释`
+ 多行注释  `/*  这是多行注释*/`
+ 文档注释  `/** 这是文档注释  */`
  + 可以使用`Javadoc`命令将文档注释提取出来生成帮助文档



#### Java中的标识符

+ 标识符可以由 **字母、数字、下划线、美元符号** 组成，但是不能以 **数字** 开头，不能是Java中的关键字

```java
//合法的标识符
username
username123
user_name
_userName
$username

//非法的标识符
123username
class
98.3
Hello World
```

+ 为增加代码的可读性，在定义标识符时还应该遵循以下规范：
  + **包名** 所有字母一律小写		`cn.test.book`
  	 **类名和接口** 每个单词的首字母都要大写	`ArrayList`
  + **常用名** 所有字母都要大写，单词之间用下划线连接  `DAY_OF_MONTH`
  + **变量名和方法名** 的第一个单词首字母小写，之后首字母大写  `lineNumber`
  + 在程序中尽量使用 **有意义的英文单词** 来定义标识符 `password`



#### Java中的关键字

+ 关键字是编程语言里事先定义韩并赋予了特殊含义的单词

![1551160534150](Java基础案例教程.assets/1551160534150.png)

+ 使用**Java关键字**时，有几个值得注意的地方
  + 所有的关键字都是小写的
  + 程序中的标识符不能以关键字命名
  + `const`和`goto`是保留关键字，虽无任何意义，但是不能作为自定义的标识符
  + `true、 false、 null`不属于关键字，他们是一个单独标识类型，不能直接使用





#### Java中的常量

1. 整型常量

+ 有**二进制、八进制、十进制、和十六进制** 4种表现形式
+ 不同的进制有不同的标识：**八进制以0开头，十六进制以0x或0X开头，十进制数不能以0开头，0除外**



2. 浮点型常量

+ 有float **单精度** 和double **双精度** 两种
+ 单精度浮点数后面以f或F结尾，双精度浮点数以D或者d结尾，**也可不加后缀**

```java
2e3f		3.6d		0f		3.84d		5.02e+23f
```



3. 字符常量

+ 用于表示一个字符，一个字符常量用 **一对英文半角格式的 ==单引号==** 引起来
+ 可表示 **英文、数字、标点符号以及由转义字符** 来表示的特殊字符

```java
'a'		'1'		'&'		'\r'	'\n0000'
```

> `'\u0000'` 表示一个空白字符，即在单引号之间没有任何字符。
>
> 之所以可以用这样来表示，是因为 Java 采用的是 Unicode 字符集， ==Unicode字符== 以 \u开头



4. 字符串常量

+ 表示一串连续的字符，用 **一对英文半角格式的 ==双引号==** 引起来
+ 一个字符串可以 **包含一个字符或多个字符，也可以不包含任何字符** 

```java
"hello java"		"123"		"Welcome \n XXX"		""
```



5. 布尔常量

+ 只有两个值，true和 flase，用于区分事物的真于假



6. null常量

+ 只有**一个值 null**，表示对象的引用为空



#####十进制与二进制的转换

![1551272804458](Java基础案例教程.assets/1551272804458.png)







#### Java中的变量

变量的定义

+ 在程序在运行期间，产生的一些临时数据，应用程序会将这些数据保存在一些内存单元中，**每个内存单元都用一个标识符来标识** ，这些内存单元称为 **变量** ，定义的标识符称为 **变量名** 
+ 变量还可以分为 **静态变量(从属于类)、成员变量、局部变量**



#####1. 变量的数据类型

+ Java 是 **强类型** 的语言，对变量的数据类型有严格的限定
+ 在 Java 中，变量的数据类型分为两种，**基本数据类型和引用类型** 

![1551273356474](Java基础案例教程.assets/1551273356474.png)

+ 8种数据类型是 Java 语言内嵌的，在任何操作系统中都具有 **相同大小和属性** ，而引用数据类型是 Java 程序中由 **程序员自己定义的变量类型**





######1.1 整数类型

![1551273616144](Java基础案例教程.assets/1551273616144.png)

+ 变量的取值不能超过取值范围
+ 在long 类型的变量赋值时，所赋值的后面要加上一个字母 **L 或者 l **



###### 1.2 浮点数类型变量

![1551273872800](Java基础案例教程.assets/1551273872800.png)

+ double 型所表示的浮点数比 float 型更精确
+ 在 Java 中，一个小数会被默认为 double 类型的值，所以在为 float 类型的变量赋值时，要加 **F 或 f **
+ 可以为一个浮点数类型变量赋予整数数值



###### 1.3 字符类型变量

+ 存储单一字符，用 char 来定义
+ char 类型会占用 **2个字节**
+ 为 char 类型赋值的时候，可以用英文半角格式的 **单引号** 或者 `0~65535` 范围内的 **整数**



###### 1.4 布尔类型变量

+ 在 Java 中用 **boolean** 表示，只有两个值true 和 flase 



##### 2. 变量的类型转换

+ 在程序中，把一种数据类型的值赋值给另一种数据类型的变量时，需要进行数据类型转换
+ 分为 **自动类型转换和强制类型转换** 两种

> 1. 自动类型转换
>
> + 也称隐式类型转换，指两种数据类型在转换过程中 **不需要显式地进行声明**，需要满足两个条件
>   + 两种数据类型彼此兼容
>   + 目标类型的取值范围大于源类型的取值范围
>
> 2. 强制类型转换
>
> + 也称显式类型转换，指两种数据类型之间的转换需要进行显式的声明，应用范围
>   + 两种类型彼此不兼容
>   + 目标类型的取值范围小于源类型

```java
//	强制转换
public class Example01{
    public static void main(String[] args){
        int num = 4;
        byte b = (byte)num;		//强制转换格式 目标类型 变量 = (目标类型) 值
        System.out.println(b);
    }
}
```

+ 强制转换可能造成精度丢失的情况

![1551275628486](Java基础案例教程.assets/1551275628486.png)



###### 表达式类型自动提升

+ 表达式是由变量和运算符组成的一个算式
+ 变量在表达式中进行运算时，可能发生自动类型转换，**这就是表达式数据类型的自动提升**

```java
public class Example03{
    public static void main (String[] args){
        byte b1 = 3;
        byte b2 = 4;
        byte b3 =(byte) b1 + b2;
        System.out.print("b3")
    }
}
```





##### 3. 变量的作用域

+ 变量需要先定义后使用，但是并不意味着变量在定义之后一定可以使用该变量
+ 变量只有在它的 **作用范围内 ** 才可以被使用，这个范围称为 **作用域** 

![1551276291410](Java基础案例教程.assets/1551276291410.png)









####Java 中的运算符

:blonde_woman:	运算符用于对数据进行算术运算、赋值和比较等操作，运算符可以分为 **算术运算符、赋值运算符、比较运算符、逻辑运算符**

##### 1. 算术运算符

![1551276535750](Java基础案例教程.assets/1551276535750.png)

+ 自增和自减运算时，看清楚是 **先进行自增或自减运算还是后进行**
+ 在进行除法运算时，当被除数和除数都为整数时，得到的也是一个整数，**如果除法有除数小数参与，得到的结果也会是一个小数**
+ 在进行取模（%）运算时，运算结果的正负 **取决于被模数（%左边的数）的符号`(-5)%3=-2`





##### 2. 赋值运算符

:blonde_woman:	将常量、变量或表达式的值赋给某一个变量

![1551277047026](Java基础案例教程.assets/1551277047026.png)

+ 在赋值过程中，运算顺序 **从右往左** ，将右边表达式的结果赋给左边的变量
+ 在 Java 中可以通过一条赋值语句对多个变量进行赋值

```java
//这是正确的
int x,y,z;
x=y=z=3;

//这是错误的
int x=y=z=5;
```

+ 在使用 `+=、*=、-=、/=、%=` 运算符进行赋值时，强制类型转换会自动完成，不需要做任何显式地声明





##### 3. 比较运算符

:blonde_woman:	对两个数值或变量进行比较，其结果是一个布尔值

![1551277574219](Java基础案例教程.assets/1551277574219.png)





##### 4. 逻辑运算符

:blonde_woman:	用于对布尔型的数据进行操作，其结果仍是一个布尔型数据

![1551277727797](Java基础案例教程.assets/1551277727797.png)

> 在使用逻辑运算符的过程中，需要注意以下几个细节：
>
> + 逻辑运算符可以针对结果为布尔值的表达式进行运算
> + 运算符 `&和&&`都表示与操作
>   + `&`  进行运算时，不论左边为 true 和 flase，右边的表达式都会进行运算
>   + `&&`  进行运算时，当左边为 flase 时，右边的表达式则不会进行运算
> + 运算符 `| 和 ||` 都表示或操作
>   + `|` 两边表达式都会进行运算
>   + `||` 进行运算时，当左边的为 true 时，右边的表达式就不会进行运算
> + `^`表示异或操作
>   + 两边的布尔值相同时，结果为 flase
>   + 两边的布尔值不同时，结果为 true





#####5. 运算符的优先级

:blonde_woman:	在进行复杂的表达式运算时，要明确表达式中所有运算符参与运算的先后顺序，通常把这种顺序叫做优先级

![1551278681254](Java基础案例教程.assets/1551278681254.png)

+ 数字越小，优先级越高
+ 没有必要刻意记忆运算符的优先级，可以使用 `()` 来实现想要的运算顺序，以免产生歧义





#### 案例1 打印一个库存清单

+ 实现的结果如图

![1551328819773](Java基础案例教程.assets/1551328819773.png)

+ 实现的代码：

```java
package cn.test.chapter02.task01;
public class StoreList{
    public static void main(String[] args){
        //笔记本电脑
        String macBrand = "MacBookAir";
        double macSize = 13.3;
        double macPrice = 6988.88;
        String macConfig = "i5 处理器 4GB内存 128G固态硬盘";
        int macCount = 5;
        //联想笔记本
        String thinkpadBrand = "ThinkpadT450";
        double thinkpadSize = 14.0;
        double thinkpadPrice = 5999.99;
        String thinkpadConfig = "i5处理器 4GB内存 500G硬盘";
        int thinkpadCount = 18;
        //华硕ASUS笔记本电脑
        String ASUSBrand = "ASUS-FL5800";
        double ASUSSIze = 15.6;
        double ASUSPrice = 4999.5;
        String ASUSConfig = "i7处理器 4GB内存 128G固态硬盘";
        int ASUSCount = 18;
        //列表顶部
        System。out.println("--------------------------------商城库存清单"+"---------------------------------------------");
        System.out.println("品牌型号尺寸		价格		配置		库存数");
        //列表中部
        System.out.println(macBrand+"	"+macSize+"		"+macPrice+"	"+macConfig+"	"+macCount);
        System.out.println(thinkpadBrand+"		"+thinkpadSize+"		"+thinkpadPrice+"		"+thinkpadConfig+"	"+thinkpadCount);
        System.out.println(ASUSBrand+"		"+ASUSSize+"		"+ASUSPrice+"		"+ASUSConfig+"		"+ASUSCount);
        //统计总库存数，库存总金额
        int totalCount = macCount + thinkpadCount + ASUSCount;
        double totalMoney = (macCount * macPrice) + （thinkpadCount * thinkpadPrice) + (ASUSCount * ASUSPrice);
        //列表底部
        System.out.println("---------------------------------------------"+"----------------------------------");
        System.out.println("总库存数："+totalCount);
        System.out.println("库存商品总金额："+totalMoney);
    }
}
```









#### 选择语句

:blonde_woman:	Java 中有一种特殊的语句叫做 **选择语句** ，它对一些条件做出判断，从而决定执行哪一段代码。选择语句分为 **if 条件语句和 switch 条件语句两种 **



1. **if 语句**

![1551330845752](Java基础案例教程.assets/1551330845752.png)

```java
//简单的 if 条件语句
public class Example07 {
    public static void main (String[] args) {
        int x =5;
        if (x < 10) {
            x++;
        }
        System.out.println("x=" + x);
    }
}
```



2. **if...else 语句**

![1551331094731](Java基础案例教程.assets/1551331094731.png)

```java
public class Example08 {
    public static void main (String[] args) {
        int num = 19;
        if (num % 2 ==0) {
            //判断条件成立，num 被 2 整除
            System.out.println ("num 是一个偶数");
        } else {
            System.out.println("num 是一个奇数");
        }
    }
}
```



3. **三元运算符**

```java
	判断条件 ？ 表达式1  ：  表达式 2
```

+ 如果判断条件成立，则执行表达式 1 ，否则执行表达式 2

```java
//求两个数之间的较大数
int x = 0;
int y= 1;
int max;

//if...else实现
if (x > y) {
    max = x;
} else {
    max = y;
}

//三元运算实现
int max = x > y ? x : y;
```





4. **if...else if...else 语句**

![1551331688461](Java基础案例教程.assets/1551331688461.png)

```java
//对学生考试成绩进行等级划分
public class Example09 {
    public static void main (String[] args) {
        int grade = 75;	//定义学生成绩
        if (grade > 80) {
            //满足条件 grade > 80
            System.out.println("该成绩的等级为优");
        } else if (grade > 70) {
            //条件不满足 grade > 80 但满足条件 grade > 70
            System.out.prinln("该成绩的等级为良");
        } else if (grade > 60) {
            //不满足条件 grade > 70,但满足条件 grade > 60
            System.out.println("该成绩的等级未中");
        } else {
            //不满足条件 grade > 60 
            System.out.println("该成绩的等级为差");
        }
    }
}
```





5. **switch 语句**

+ switch 条件语句也是常用的选择语句，但是它只能针对 **某个表达式的值** 做出判断

```java
//Switch语句根据给出的数值来输出对应中文格式的星期
public class Example10 {
    public static void main (String[] args) {
        int week = 5;
        switch (week) {
            case 1:
                System.out.println("星期一");
                break;
            case 2:
                System.out.println("星期二");
                break;
            case 3 :
                System.out.println("星期三");
                break;
            case 4 :
                System.out.println("星期四");
                break;
            case 5:
                System.out.println("星期五");
                break;
            case 6 :
                System.out.println("星期六");
                break;
            case 7 :
                System.out.println("星期天");
                break;
            default :
                Systen.out.println("输入的数字不正确...")；
                break;
        }
    }
}




/*在执行 switch 语句的过程中，如果多个 case 条件后的执行语句是一样的，则该执行语句只需书写一次*/
int week = 2;
switch (week) {
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        //当 week 满足值 1、2、3、4、5中任意一个时，处理的方式相同
        System.out.println ("今天是工作日");
        break;
    case 6:
    case 7:
        //当 week 满足值 6、7 中任意一个时，处理方式相同
        System.out.println("今天是休息日");
        break;
}
```







#### 循环语句

+ **While循环语句** 当满足条件的时候，程序会循环执行直到不满足条件

![1551333532692](Java基础案例教程.assets/1551333532692.png)

```java
public class Example12 {
    public static void main (String[] args) {
        int x = 1;
        while (x <= 4) {
            System.out.println ("x = " + x);
            x++;
        }
    }
}
```





+ **do...while 循环语句** 会执行一次循环后再看判断条件

![1551333840414](Java基础案例教程.assets/1551333840414.png)

```java
public class Example13 {
    public static void main (String[] args){
        int x = 1;
        do {
            System.out.println ("x =" + x);
            x++
        } while (x <= 4);
    }
}
```





+ **for 循环语句** 是最常用的循环语句，一般在 **已知循环次数** 的情况下使用

![1551334097561](Java基础案例教程.assets/1551334097561.png)

```java
public class Example14 {
    public static void main (String[] args) {
        int sum = 0;//定义变量 sum，用于记住累加的和
        for (int i = 1;i <= 4; i++) {	//i的值会在 1~4之间变化
            sum += i;	//实现 sum 与 i 的累加
        }
        System.out.println("sum = "+ sum );	//打印累加的和
    }
}
```





+ **循环嵌套** 是指在一个循环语句的循环体中再定义一个循环语句的复杂语法结构

![1551334632347](Java基础案例教程.assets/1551334632347.png)

```java
//打印 * 号的直角三角形
public  class Example15 {
     public static void main (String[] args) {
        int i, j;
        for (i = 1;i <=9; i++) {
            for (j=1; j <= i；j++) {
                System.out.print("*");
           }
            System.out.print("\n")
        }
    }
}
```

> 循环嵌套比较复杂，i 为外层循环变量， j 为内层循环变量
>
> + 外层控制输出的行数，内层控制输出的个数
> + 适当增加换行，让输出更加清晰







#### 跳转语句

:blonde_woman:	**跳转语句** 用于实现循环执行过程中程序流程的跳转，又 `break 和 continue` 两种



+ **break 语句** 用于跳出循环语句，继续执行 **后面的代码** 

```java
public class Example17 {
    public static void main (String[] args) {
        int x = 1;
        while (x < 4) {
            System.out.println("x = " + x);  //循环条件成立，打印 x 的值
            if (x == 3) {
                break;		//跳出此循环，继续执行外面的语句
            }
            x++;
        }
    }
}
```

+ 当 break 语句出现在循环嵌套中的 **内层循环时**，它**只能跳出内层循环** ，如果想跳出**外层循环 **，则 **需要对外层循环添加标记**

```java
//只打印 4 行   * 号的直角三角形
public  class Example15 {
     public static void main (String[] args) {
        int i, j;
        mark:for (i = 1;i <=9; i++) {	//添加标记
            for (j=1; j <= i；j++) {
                if (i > 4) {
                    break mark;		//通过标记，跳出外层循环
                }
                System.out.print("*");
           }
            System.out.print("\n")
        }
    }
}
```





+ **continue语句** 作用是 **终止本次循环，执行下一次循环**

```java
// 计算 1~·00 内所有奇数的和
public class Example18 {
    public static void main (String [] args) {
        int sum = 0;
        for (int i = 1; i <= 100; i++) {
            if (i % 2 == 0) {
                continue ;		//当为偶数时跳出此次循环
            }
            sum += i;			//计算奇数的和
        }      
        System.out.println("sum = " + sum);
    }
}
```







#### 案例2 猜数字游戏

![1551336529223](Java基础案例教程.assets/1551336529223.png)

```java
//实现猜数字游戏的代码
package cn.test.chapter02.task02;
import java.util.Random;
import java.unil.Scanner;
public class GuessNumber {
    public static void main (String [] args) {
        // 1.通过 Random 类中的 nextInt(int n) 方法，生成一个 0~9 的随机数
        int randomNumber = new Random().nextInt(10);
        System.out.println ("随机数已生成！");
        // 2.输入猜的数字
        System.out.println ("-------请输入您猜测的数字--------");
        Scanner sc =new Scanner(System.in);
        int enterNumber =sc.nextInt ();
        // 3.通过 while 循环 ，进行猜数字的对错判断
        //猜对，跳出循环，游戏结束
        while (enterNumber != randomNumber) {
            //猜错了，根据结果，给出提示，接着猜数字，游戏继续
            if (enterNumber > randomNumber) {
                //如果数字猜大了，打印语句
                System.out.println("sorry ,你猜大了");
            } else {
                //如果猜小了，打印语句
                System.out.println("sorry ,你猜小了")；
            }
            //再次输入猜的数字
            System.out.println("-----请输入您猜的数字------");
            enterNumber = sc.nextInt ();
        }
        System.out.println ("恭喜你，猜对了！");
    } 
}
```









#### 方法

:blonde_woman:	**方法** 也称 **函数** ，是一段可以 **重复调用** 的代码



+ 演示方法对代码可读性的影响

```java
public class Example19 {
    public static void main (String[] args) {
        //打印一个宽度为 5、高度为 3 的矩形
        for (int i = 0; i < 3; i++) {
            for (int j = 0;j < 5; j++) {
                System.out.print("*")
            }
            System.out.print("\n");
        }
        System.out.print("\n");
        
        //再次打印一个宽为 4、高为 2 的矩形
        for (int i = 0; i < 2; i++) {
            for (int j = 0;j < 4; j++) {
                System.out.println("*")
            }
            System.out.println("\n");
        }
        System.out.println("\n");
        
        //再次打印一个宽为 10，高为 6 的矩形
        for (int i = 0; i < 6; i++) {
            for (int j = 0; j < 10; j++) {
                System.out.print("*")
            }
            System.out.print("\n");
        }
        System.out.print("\n");
    }
}
```

> 3个嵌套 for 循环完成了 3 个矩形的打印，但是这三个嵌套的代码是重复的，都在做一样的事情，因此可以把 **打印矩形功能** 定义为一个方法，**重复调用**

```java
// 改进版本的矩形打印
public class Example20 {
    public static void main (String[] args) {
        printRectangle (3, 5);
        printRectangle (2, 4);
        printRectangle (6, 10);
    }
    //定义一样个打印方法，接收两个参数，其中 height 为高， width 为宽
    public static void printRectangle (int height, int width) {
        for (int i =0; i < height; i++) {
            for (int j = 0; j < width; j++) {
                System.out.print ("*");
            }
            System.out.print("\n");
        }
        System.out.print("\n");
    }
}
```



+ 在 Java 中声明一个方法的格式如下：

![1551404279961](Java基础案例教程.assets/1551404279961.png)





##### 方法的重载

:blonde_woman:	在程序中，由于参与求和数字的个数和类型都不确定，所以要针对不同的情况去设计不同的方法。可以定义 **多个同名的方法** 通过传入不同的参数便可以确定调用哪个重载的方法。

```java
// 以后程序都省略掉包类定义
public static void main (String[] args) {
    //下面是针对求和方法的调用
    int sum1 = add (1,2);
    int sum2 = add (1,2,3);
    double sum3 =add (1.2, 2.3);
    //下面的代码是打印求和的结果
    System.out.println ("sum1 = " + sum1)；
    System.out.println ("sum2 = " + sum2)；
    System.out.println ("sum3 = " + sum3)；
}

// 下面的方法实现了两个数的相加
public static int add (int x,int y) {
    return x + y;
}
//下面的方法实现了三个数的相加
public static int add (int x, int y, int z) {
    return x + y + z;
}
//实现了两个小数相加
public static double add (double x, double y) {
    return x + y;
}
```

> **方法的重载与返回值类型无关，它需要满足两条件
>
> + 方法名相同
> + 参数个数或参数类型不相同







#### 数组

:blonde_woman:	**数组** 是用来存储数据的数据结构

```java
	int[] x;			//声明一个 int[]类型的变量
	x = new int[100];	//创建一个长度为 100 的数组
```

+ 在内存中的变化如图

![1551406940838](Java基础案例教程.assets/1551406940838.png)



+ 数组在定义的时候如果不赋值 **会使用默认值** 

![1551407071571](Java基础案例教程.assets/1551407071571.png)



+ 数组的初始化有两种，一种是 **动态初始化** ，一种是 ** 静态初始化**

```java
// 动态初始化
int []a = new int[100];

//静态初始化1
int []a = {1, 2, 3, 4};
```



+ 数组可能出现的两种错误情况 `ArrayIndexOutOfBoundsException`  和 `NullPointException`



##### 数组常见的操作

1. 数组遍历

```java
public static void main (String[] args) {
    int[] arr = {1, 2, 3, 4, 5 };		//定义数组
    //使用for循环遍历数组的元素
    for (int i = 0; i < arr.length; i++) {
        System.out.println (arr[i]);	//通过索引来访问元素
    }
}
```



2. 数组最值

```java
public static void main (String[] args) {
    int [] arr = {1, 4, 5, 10 ,-2 };
    int max = getMac (arr);
    System.out.println ("Max=" + max);
}
static int getMax (int[] arr) {
    int max = arr[0];	//定义变量 max 记住最大数，首先假设第一个元素为最大值
    //下面通过一个 for 循环遍历数组中的元素
    for (int x = 1; x < arr.length; x++) {
        if (arr[x] > max) {	//比较 arr[x] 的值是否大于 max
            max = arr[x];	//条件成立，将 arr[x] 的值赋给 max
        }
    }
    return max;		//返回最大值 max
}
```

> for 循环的变量一开始就从第二个元素开始比较，因为程序已经假设第一个元素为最大值，进而提高程序的效率



3. 数组排序

+ **冒泡排序** 算法在排序的过程中，不断地比较数组中相邻两个元素，较小者向上浮，较大者往下沉，整个过程像冒气泡一样

```java
public static void main (String[] args) {
    int [] arr = {9, 1, 2, 78, 0};
    System.out.print("冒泡排序前 ： ");
    printArray (arr);
    bubbleSort (arr);
    System.out.print("冒泡排序后 : ");
    printArray (arr);
}
//定义打印数组元素的方法
public static void printArray (int[] arr) {
    for (int i = 0; i < arr.length; i++) {
        System.out.print(arr[i] + " ");
    }
    System.out.print("\n");
}
//定义对数组排序的方法
public static void bubbleSort (int [] arr) {
    for (int i = 0; i < arr.length; i++) {
        for (int j = 0; j < arr.length - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr [j];
                arr[j] = arr[j+1];
                arr[j + 1] = temp;
            }
        }
        System.out.print("第" + (i + 1) + "轮排序后：");
        printArray (arr);
    }
}
```

![1551420556618](Java基础案例教程.assets/1551420556618.png)

![1551420651841](Java基础案例教程.assets/1551420651841.png)





##### 多维数组

:blonde_woman:	**多维数组** 可以简单理解为在数组中的嵌套



1. `int [][] arr = new int [3][4]` 

![1551421367174](Java基础案例教程.assets/1551421367174.png)

2. `int [][] arr = new int [3][];`

![1551421422442](Java基础案例教程.assets/1551421422442.png)

3. `int [][] arr = {{1, 2}, {3, 4, 5, 6} , {7,  8, 9}};`

![1551421578913](Java基础案例教程.assets/1551421578913.png)

```java
public static void main (String[] args) {
    int [][] arr = new int [3][];	//	定义一个长度为 3 的二维数组
    arr[0] = new int [] {11, 12};
    arr[1] = new int [] {21, 22, 23};
    arr[2] = new int [] {31, 32, 33, 34 };
    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        int groupSum = 0;
        //	遍历小组内每个人的销售额
        for (int j =0; j < arr [i].length; j++) {
            groupSum = groupSum + arr[i][j];
        }
        sum = sum + groupSum;
        System.out.println("第" + (i + 1) + "小组销售额为" + groupSum + "万元。");
    }
    System.out.println("总销售额为：" + sum + "万元");
}
```







#### 案例3 随机点名器

![1551422596147](Java基础案例教程.assets/1551422596147.png)

```java
    /**
    *1.存储全班同学的姓名
    *  创建一个储存多个同学姓名的容器 （数组）
    *  键盘输入每个同学的姓名，存储道容器中
    */
    public static void addStudentName (String [] students) {
        //	键盘输入多个同学姓名储存到容器中
        Scanner sc = new Scanner (System.in);
        for (int i =0; i < students.length; i++) {
            System.out.println("存储第" + (i + 1) + "个姓名： ");
            //	接收控制台录入的姓名字符串
            students[i] = sc.next ();
        }
    }
    
    //	总览全班同学的姓名
    public static void printStudentName (String [] students) {
        //遍历数组，得到每一个同学的姓名
        for (int i =0 ; i < students.length; i++) {
            String name = students[i];
            //打印同学姓名
            System.out.printLn ("第" + (i + 1) + "个同学姓名" + name );
        }
    }
    
    //	随机点名其中一人
    public static String randomStudentName (String[] students) {
        //根据数组长度，获取随机索引
        int index = new Random ().nextInt (students.length);
        //通过随机索引从数组中获取姓名
        String name = students [index];
        //返回随机点到的姓名
        return name;
    }
    
    public static void main (String[] args) {
        System.out.println("-------随机点名器--------");
        //	创建一个可以存储多个同学姓名的容器
        String[] students = new String[3];
        //	1.存储全班同学姓名
        addStudentName (students);
        //	2.总览全班同学
        printStudentName (students);
        //	3.随机点名
        String randomName=randomStudentName (students);
        System.out.println("被点明的同学姓名是：	" + randomName);
    }
```









### 面对对象（上）

:blonde_woman:	**面对对象** 是把构成问题的事物按照一定规则划分为多个独立的对象，然后通过调用对象的方法来解决问题

:blonde_woman:	**面对过程** 是分析出问题所需要的步骤，然后用函数把这些步骤逐一实现，使用时依次调用就可以了

```java
	面对过程适合简单、不需要协作的事物；但当面对需要协作才能完成的任务时，面对对象的思想更好。
	两种思维方式的总结：
	1. 都是解决问题的思维方式，都是代码组织的方式
	2. 解决简单的问题可以使用面向过程
	3. 解决复杂问题：宏观上使用面对对象（类）把握，微观处理上仍然是面向过程（方法）
```





+ 面对对象的特点主要概括为 **封装性、继承性、多态性**

1. **封装性**

```txt
	封装是面对对象的核心思想，将对象的属性和行为封装起来，不需要让外界知道具体实现细节，这就是封装思想。
```



2. **继承性**

```txt
	继承性主要描述的是类与类之间的关系，通过继承，可以在无需重新编写原有类的情况下，对原有类的功能进行扩展。
```



3. **多态性**

```txt
	多态性指的是在程序中允许出现重名现象，它指在一个类中定义的属性和方法被其他类继承后，它们可以具有不同的数据类型或表现出不同的行为，这使得同一个属性和方法在不同的类中具有不同的语义。
```





#### 类与对象

:blonde_woman:	**类是对某一类事物的抽象描述，而对象用于表示现实中该类事物的个体。**

![1551445253664](Java基础案例教程.assets/1551445253664.png)

+ 类用于描述多个对象的共同特征，它是对象的模版；而对象用于描述现实中的个体，它是类的实例。



##### 类的定义

:blonde_woman:	类中可以定义 **成员变量和成员方法** ，成员变量用于描述对象的特征，也称作属性；成员方法用于描述对象的行为，可简称方法

```java
//	定义一个人的类
class Person {
    int age =20;	//定义 int 类型的成员变量 age
    //	定义 speak() 方法
    void speak () {
        System.out.println("大家好，我今年" + age + "岁！");
    }
    
    //	用于区别 成员变量与局部变量
    void talk () {
        int age = 10;
        //	打印的值为 10 ，而不是 20
        System.out.print("我调用的 age 是只取局部变量的值" + age);
        //	在一个方法中定义的局部变量同名是允许的，但是在此方法中调用的是局部变			//    量，而非成员变量
    }
}
```





##### 对象的创建与使用

+ `Person p = new Person () `可以创建一个名为 `p `的 `Person` 类

![1551446740313](Java基础案例教程.assets/1551446740313.png)

+ 对象在创建后通过 **对象的引用** 来访问对象所有的成员

```java
public static void main (String[] args) {
    Person p1 = new Person;		// 创建第一个 Person 对象
    Person p2 = new Person;		// 创建第二个 Person 对象
    p1.age = 18;			   // 为age属性赋值		
    p2.speak();				   // 调用对象的方法
    p1.talk();
    
}
```

![1551449596401](Java基础案例教程.assets/1551449596401.png)

+ `Java`虚拟机会自动为成员变量进行初始化，针对不同的成员变量，会赋予不同的初始值

![1551496726322](Java基础案例教程.assets/1551496726322.png)



+ **垃圾对象** 对象被实例化后，在程序中可以通过对象的引用变量来访问对象的成员，但是 **当没有任何变量引用这个对象时** ，它将成为垃圾对象

```java
class Person {
    void say () {
        System.out.print("你好");
    }
}

class Example02 {
    public static void main (String[] args) {
        Person p2 = new Person ();
        p2.say ();
        p2 = null;
        p2.say ();
    }
}
//	在程序运行时，把变量 p2 置为 null， 那么被 p2 所引用的 Person 对象就会失去
//	引用，成为垃圾对象 
```

![1551497423253](Java基础案例教程.assets/1551497423253.png)



##### 类的设计

+ 任务：定义一个学生类，在这个类中定义两个属性 name 、age ，分别表示学生的姓名和年龄，定义一个方法 introduce() 表示学生做自我介绍

```java
public class Student {
    String name;	//定义一个姓名属性
    int age ;	//定义一个年龄属性
    public void introduce () {
        System.out.println ("大家好，我叫" + name + ",我今年" + age + "岁！");
    }
}
```



##### 类的封装

+ 针对上面设计的 Students 类创建对象，并访问该对象的成员

```java
public static void main (String[] args) {
    Student stu = new Student ();
    stu.name = "周小小";
    stu.age = -30;
    stu.introduce();
}
```

:warning:	上面输出的年龄明显在现实生活中是不合理的，为了解决这个问题，在设计一个类时，应该 **对成员变量的访问做出一些限定，不允许外界随意访问** ，这就需要实现类的封装

:tiger:	**类的封装** 是指在定义一个类时，将类中的属性私有化，私有属性只能在它所在的类中被访问，**如果外界想访问私有属性，需要提供一些使用 `public` 修饰的公有方法** 其中包括用于获取属性值的 get方法 和设置属性值的 Set方法

```java
package forTest;

class Student {
    private String name;
    private int age;
    public String getName () {
        return name;
    }
    public void setName (String stuName) {
        name = stuName;
    }
    public int getAge () {
        return age;
    }
    public void setAge (int stuAge) {
        //对传入的参数进行检查
        if (stuAge <= 0) {
            System.out.println("对不起，您输入的年龄不合法...");
        } else {
            age = stuAge;
        }
    }
    public void introduce () {
        System.out.println("大家好，我叫" + name + "，我今年" + age + "岁！");
    }
}
public class Example04 {
    public static void main (String[] args) {
        Student stu = new Student();
        stu.setAge(20);	//	程序会执行检查
        stu.setName("周天");
        stu.introduce();
    }
}
```







#### 案例4 超市购物程序设计

![1551500076729](Java基础案例教程.assets/1551500076729.png)

:one:	定义商品类 Product

```java
public class Product {
	private String proName;	//商品名
	public String getProName() {
		return proName;
	}
	public void setProName (String proName) {
		this.proName = proName;
	}
}
```

:two:	定义超市类 Market

```java
public class Market {
	private String markName;
	private Product[] productArr;//	超市的仓库，里面有若干商品
	public String getMarketName() {
		return markName;
	}
	public void setMarkName(String marketName) {
		this.markName = marketName;
	}
	public Product[] getProductArr() {
		return productArr;
	}
	public void setProductArr(Product[] productArr) {
		this.productArr = productArr;
	}
	Product sell(String name) {
		// 循环遍历仓库的每一个商品
		for (int i = 0; i < productArr.length; i++) {
			//如果商品名称和要买的商品一致
			if (productArr[i].getProName() == name) {
				return productArr[i];
			}
		}
		return null;	//循环结束后没有找到商品，返回 null 代表没找到
	}
}
```

:three:	定义购物者 Person

```java
public class Person {
	private String name;
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	// 购物，指定去哪个超市，商品名
	Product shopping (Market market, String name) {
		//调用超市的卖货方法，指定商品名，把卖出的结果返回
		return market.sell(name);
	}
}	
```

:four:	定义测试类 Shopping

```java
public class Shopping {
	public static void main (String[] args) {
		Product p1 = new Product();
		Product p2 = new Product();
		Product p3 = new Product();
		Product p4 = new Product();
		Product p5 = new Product();
		p1.setProName("电视机");
		p2.setProName("洗衣机");
		p3.setProName("豆浆机");
		p4.setProName("空调");
		p5.setProName("吹风机");
		//创建超市对象，给超市名字赋值，给仓库赋值
		Market m = new Market();
		m.setMarkName("家乐福");
		m.setProductArr(new Product[] {p1, p2, p3, p4, p5});
		//创建人对象，给名字赋值
		Person p= new Person();
		p.setName("小周");
		//	调用购物方法，指定超市和商品名，得到购物结果
		Product result = p.shopping(m, "空调");
		//根据结果进行判断
		if (result != null) {
			System.out.println(p.getName() + "在"
					+ m.getMarketName() + "买到了"
					+ result.getProName());
		} else {
			System.out.println(p.getName() + "白跑了一趟，在"
					+ m.getMarketName() + "什么都没买到");
		}
	}
}
```







#### 构造方法

:warning:	实例化一个类的对象后，如果要为这个对象中的属性赋值，则必须通过直接访问对象的属性或者调用 set 方法；**如果要在实例化对象的同时就为这个对象的属性进行赋值，可以通过构造方法来实现** ，构造方法是类的一个特殊成员，它会在类实例化对象时被自动调用。



:red_car:	一个类中定义的方法如果同时满足以下三个条件：则该方法称为构造方法

1. **方法名与类名相同**
2. **在方法名的前面没有返回值类型的声明**
3. **在方法中不能使用 return 语句返回一个值，但是可以 ==单独写 `return` 语句==来作为方法的结束**

```java
class Person {
    public Person () {
        System.out.println("无参的构造方法被调用了...");
    }
}

public class Example04 {
    public static void main (String[] args) {
        Person p1 = new Person();
    }
}
```

:warning:	在一个类中除了定义无参的构造函数，还可以定义 **有参的构造函数** ，通过有参的构造函数，可以在 **实例化的同时，对属性进行赋值**

```java
class Person {
    int age;
    public Person (int a) {
        age = a;
    }
    public void speak () {
        System.out.println("今年我已经" + age + "岁了");
    }
}

public class Example06 {
    public static void main (String[] args) {
        Person p1 = new Person(20);
        p1.speak();
    }
}
```





##### 构造方法的重载

:blonde_woman:	一个类中可以定义多个构造方法，只要每个构造方法的参数类型或参数个数不同即可

```java
class Person {
    String name;
    int age;
    //定义两个参数的构造方法
    public Person(String con_name, int con_age) {
        name = con_name;
        age = con_age;
    }
    //定义一个参数的构造方法
    public Person(String con_name) {
        name = con_name;
    }
    public void speak() {
        System.out.println("大家好，我叫" + name + "，我今年" + age + "岁");
    }
}
public class Example07 {
    public static void main (String[] args) {
        Person p1 = new Person("王艺锦");
        Person p2 = new Person("周万家",18);
        p1.speak();
        p2.speak();
    }
}
```



#####  构造方法的注意问题

:warning:	在 Java 中的每个类都至少有一个构造方法，**如果没有**，系统会自动为这个类创建一个默认的构造方法；**默认的构造方法没有参数，在其方法体中没有任何代码，即什么也不做**

```java
class Person {
    int age;
    public Person (int x) {		
        age = x;
    }
    //当类中定义了一个有参方法，使用 Person p =new Person () 时就会报错，
    //因为该类中系统不再提供默认的无参构造方法,最好再手动定义一个无参的构造方法
    public Person {
    }
}
```

> 构造方法通常使用 `public` 来修饰，这样才可以方便进行对象实例化；
>
> 当使用 `private` 修饰时，会报错 `The constructor Person() is not visible`





#### This 关键字

:warning:	This 关键字用来指代当前对象，用于在方法中访问对象的其他成员

:one:	通过 this 关键字可以明确地去访问一个类的成员变量，**解决与局部变量名称冲突的问题**

```java
class Person {
    int age;
    public Person (int age) {
        this.age = age;
    }
    public int getAge(){
        return this.age;
    }
    //在构造方法中使用 age,则是访问局部变量，但如果使用 this.age 则是访问成员变量
}
```

:two:	通过 this 关键字调用成员方法

```java
class Person {
    public void openMouth () {
        ...
    }
    public void speak () {
        this.openMouth();	//	其中 this 关键字也可省略
    }
}
```

:three:	构造方法是在实例化对象时被 Java 虚拟机自动调用的，在程序中不能像调用其他方法那样调用构造方法，但可以在一个构造方法中使用 `this([参数一，参数二....])`	的形式来调用其他构造方法

```java
class Person {
    public Person () {
        System.out.println("无参的构造方法被调用了");
    }
    public Person (String name) {
        this ();		//	调用无参的构造方法
        System.out.println("有参的构造方法被调用了...");
    }
}

public class Example {
    public static void main(String[] args) {
        Person p = new Person("周");
    }
}
```

+ 在使用 `this ` 调用类的构造方法时，==注意：==
  + 只能在构造方法中使用 this 调用其他的构造方法，不能在成员方法中使用
  + 在构造方法中，使用 this 调用构造方法的语句 **必须位于第一行，且只能出现一次**
  + 不能在一个类的两个构造方法中使用 this 互相调用
+ `this` 不能在 `static` 方法中调用





#### 垃圾回收（Garbage Collection)

:warning:	当程序的运行产生的垃圾堆积到一定程度时， Java 虚拟机就会启动垃圾回收器将这些垃圾对象从内存中释放，从而使程序获得更多可用的内存空间

+ `System.gc()` 可通知 Java 虚拟机立即进行垃圾回收
+ `finalize()` 可观察对象何时被释放

```java
class Person {
    // 下面定义的方法 finalize 方法会在垃圾回收前被调用
    public void finalize () {
        System.out.println("对象将被作为垃圾回收...");
    }
}
public class Example {
    public static void main (String[] args) {
        Person p1 = new Person();
        Person p2 = new Person();
        //	将变量置为 null ,让对象成为垃圾
        System.gc();
        for (int i = 0; i < 100000; i++) {
            //	为了延长程序运行的时间
        }
    }
}
//	Java 虚拟机的垃圾回收操作是在后台完成的，程序结束时，垃圾回收的操作也将终止
```

+ 在底层调优上，多数是对 `JVM` 垃圾回收进行





#### static关键字

:art:	用于修饰了类的成员，如 **成员变量、成员方法以及代码快等** ，被 static 定义后具有一些特殊性

:warning:	static 关键字只能用于 **修饰成员变量**， 不能修饰局部变量，否则编译会报错

1. 静态变量

```java
//	使用 static 关键字来修饰成员变量，该变量就称为静态变量。
//	静态变量被所有实例共享
class Studet {
    static String schoolName;	//定义一个静态变量
}
public class Example {
    public static void main (String[] args) {
        Student stu1 = new Student();
        Student stu2 = new Student();
        Student.schoolName = "大学";
        System.out.println("我的学校是" + stu1.schoolName);
        System.out.println("我的学校是" + stu2.schoolName);
    }
}
```

![1551675825439](Java基础案例教程.assets/1551675825439.png)



2. 静态方法

+ 在实际开发中， 开发人员有时会希望 **在不创建对象地情况下就可以调用某个方法**（该方法不必和对象绑在一起），这样的方法就称作为 **静态方法**

```java
class Person {
    public static void sayHello () {	//定义静态方法
        System.out.println("你好");
    }
}
class Example {
    public static void main (String[] args) {
        Person.sayHello();		// 通过 类名.方法 的方式调用静态方法
        Person p = new Person();
        p.sayHello();			// 实例化对象的方式来调用静态方法
    }
}
```

:warning:	静态方法中只能访问用 static 修饰的成员， 原因在于 **没有被 static 修饰的成员需要先创建对象才能访问，而静态方法在被调用时可以不创建任何对象**



3. 静态代码块

+ 使用一对大括号围起来的若干行代码被称为一个代码块，**用 static 修饰的代码块称为静态代码块**
+ 当类加载时，静态代码块就会执行；**由于类只加载一次，因此静态代码块只执行一次**
+ 在程序中，通常会使用静态代码来对类的 **成员变量进行初始化**

```java
class Example {
    //静态代码块
    static {
        System.out.println("测试类的静态代码块执行了");
    }
    public static void main (String[] args) {
        Person p1 = new Person();
        Person p2 = new Person();
    }
}
class Person {
    static {
        System.out.println("Person 类中的静态代码块执行了");
    }
}
// 在两次实例化对象的过程中，静态代码块只会在类加载的时候执行一次
```





#### 成员内部类

+ 在 Java 中，允许一个类的内部定义类，这个类叫 **内部类**，这个内部类所在的类称作 **外部类**
+ 根据内部类的 **位置、修饰符和定义的方式** 可分为 **成员内部类、静态内部类、方法内部类**

```java
class Outer {
    private int num = 4;	
    // 代码定义了一个成员方法，方法中访问内部类
    public void test () {
        Inner inner = new Inner;
        inner.show();
    }
    //	定义了一个成员内部类
    class Inner {
        void show() {
            // 在成员内部类的方法中访问外部类的成员变量
            System.out.println("num = " + num);
        }
    }
}
public class Example {
    public static void main (String[] args) {
        Outer outer = new Outer();	//创建外部类对象
        outer.test();		//调用 test 方法
    }
}
```

+ 如果像通过外部类去访问内部类，需要通过外部类对象去创建内部类对象
  + `外部类名.内部类名 变量名 = new 外部类名(). new 内部类名();`
  + `Outer.Inner inner = new Outer().new Inner();`





#### 案例5 银行新用户现金业务办理

![1551678319572](Java基础案例教程.assets/1551678319572.png)

+ 定义银行类


```java
package cn.baidu.bank;
public class Bank {
static String bankName;		//	定义静态变量银行名称
private String name;	//	储户姓名
private String password;
private double balance;	//账户余额
private double turnover;//交易额
	//静态方法，打印出银行欢迎语句
    static void welcome () {
        System.out.println("欢迎来到" + bankName + "-----------");
    }
    //	构造方法 开户
    public Bank (String name , String password, double turnover) {
        //	将变量赋值给成员变量
        this.name = name;
        this.password = password;
        this.turnover = turnover;
        this.balance = turnover - 10;
        System.out.println(name + "开户成功，账户余额" + balance);
    }
    //存款
    public void deposit (double turnover) {
    	balance = balance + turnover;
    	System.out.println(name + ",您好，您的账户已存入" + turnover + "元，" 
    	+ "当前余额" + balance + "元");
    }
    //取款
    public void withdrawal (String password, double turnover) {
    	//根据传入的变量与成员变量比对，判断密码是否正确
        if (this.password != password) {
        	System.out.println("您输入的密码错误");
        	return;
        	}
        if (balance - turnover > 0) {
            balance = balance - turnover;
            System.out.println(name + ",您好，您的账户已取出" + turnover + "元，" + "当前余额 " + balance + "元");
            } else {
            	System.out.println("对不起，账户余额不足！");
            }
    }
    //静态方法，打印出银行欢迎下次光临语句
    static void welcomeNext() {
    	System.out.println("请携带好随身财物，欢迎下次光临" + bankName + "-------");
    }
}
```

+ 定义用户交易类 Trade 

```java
package cn.baidu.bank;
public class Trade {
    public static void main (String[] args) {
		//定义一家银行(给静态变量赋值，可以直接使用类名访问)
		Bank.bankName = "招商银行";
		//调用静态方法，打印欢迎语句
		Bank.welcome();
		//通过构造方法进行开户操作
		Bank bank = new Bank("皮卡丘", "123456",100.9);
		//进行存款操作
		bank.deposit(500);
		//取款时密码输入错误，取款失败
		bank.withdrawal("124356",200.0);
		//取款时余额不足，取款失败
		bank.withdrawal("123456", 1000.0);
		//取款时密码正确，余额充足，取款成功
		bank.withdrawal("123456",200.0);
		//调用静态方法，打印道别语句
		Bank.welcomeNext();
    }
}
```





### 面对对象（下）

#### 类的继承

:art:	在程序中， **继承** 描述的是事物之间的所属关系，通过继承可以使多种事物之间形成一种关系体系。类的继承是指在 **现有类的基础上去构建一个新的类**，构建出来的新类被称作子类，现有类称作父类，**子类会自动拥有父类所有可继承的属性和方法**

![1551710974697](Java基础案例教程.assets/1551710974697.png)

```java
//	定义一个 Animal 类
class Animal {
    String name;
    void shot() {
        System.out.println("发出叫声");
    }
}
//	定义 Dog 类继承 Animal 类
class Dog extends Animal {
    public void  printName() {
        System.out.println("name = " + name);
    }
}


//	@TEST
public class Example {
    public static void main (String[] args) {
        Dog dog = new Dog ();	//	创建一个 Dog 类的实例对象
        dog.name = "沙皮狗";	//	为 Dog 类的 name 属性赋值
        dog.printName();	//	调用 dog 类的 getInfo() 方法
        dog.shot();			//调用 dog 类继承来的 shot() 方法
    }
}
```

:warning:	**类的继承** 需要注意的问题：

+ 在 Java 中，类 **只支持单继承，不允许多重继承**，一个类只有一个直接父类
+ **多个类可以继承一个父类**
+ 在 Java 中，**多层继承是可以的**，即一个类的父类可以再去继承另外的父类

```java
//	演示多层继承
	class A {};
	class B extends A{};	//类 B 是类 A 的子类
	class C extends B{};	//类 C 是类 B 的子类，同时也是类A的子类
```





###### 重写父类方法

+ 在继承关系中，子类会 **自动继承父类中定义的方法**，但有时在子类中需要对继承的方法进行一些修改，即 **重写父类方法**
+ 重写方法时，**要有相同的方法名、参数列表以及返回值类型**

```java
//	定义 Animal 类
class Animal {
    //	定义动物叫的方法
    void shout {
        System.out.println("动物发出叫声");
    }
}
//	定义 Dog类继承动物类
class Dog extends Animal {
    //	定义狗叫的方法
    void shout() {
        System.out.println("汪汪汪...");
    }
}

//	@TEST
public class Example {
    public static void main(String[] args) {
        Dog dog = new Dog();	//	调用 Dog类的实例对象
        dog.shout();	//	调用 dog重写的 shout()方法
    }
}
```

:warning:	**子类重写父类时**，不能使用比 **父类中被重写的方法更严格的访问权限**，如父类中方法是 `public` 修饰，子类的方法就不能是 `privata`





###### super关键字

+ 当子类重写父类的方法后，**子类对象将无法访问父类被重写的方法**，为了解决这个问题，Java 专门提供了一个 super 关键字用于 **访问父类的成员(成员变量、成员方法和构造方法)**
	 `super.成员变量`		`super.成员方法([参数1， 参数2，.....])`

```java
//	定义 Animal 类
class Animal {
    String name = "动物";
    //	定义动物叫的方法
    void shout() {
        System.out.println("动物发出叫声");
    }
}
//	定义 Dog 类继承动物类
class Dog extends Animal {
    String name = "犬吠";
    //重写父类的 shout() 方法
    void shout () {
        super.shout();	//	访问父类的成员方法
    }
    void printName() {
        System.out.println("name = " + super.name);	//	访问父类的成员变量
    }
}
//	@TEST
public class Example {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.shout();
        dog.printName();
    }
}
```

+ 使用 `super` 访问父类的构造方法	`super(参数1，参数2)`

```java
//	定义 Animal类
class Animal {
    //	定义 Animal类的有参构造方法
    public Animal(String name) {
        System.out.println("我是一只" + name);
    }
}
//	定义 Dog类继承 Animal类
class Dog extends Animal {
    public Dog() {
        super("小猪猪");	//	子类的构造方法 调用父类有参的构造方法
    }
}
//	@TEST
public class Example {
    public static void main(String[] args) {
        Dog dog = new Dog();	//	实例化子类的 Dog对象
    }
}
```

:warning:	`super` 调用父类的构造方法必须位于子类构造方法的 **第一行，并且只能出现一次**

+ 在定义一个类的时候，如果没有特殊需求，尽量在类中定义一个无参的构造方法，避免被继承时出现错误



###### final关键字

+ `final` 关键字可用于 **修饰类、变量和方法**，被修饰后有这样的特性：
  + 类不能被继承
  + 方法不能被子类重写
  + 变量（成员变量和局部变量）是常量，只能赋值一次

```java
//	定义student 类
class Student {
    final String name = "周";	// 使用final 关键字修饰的变量要初始化，不然报错
    public void introduce() {
        System.out.println("我叫" + name + "，是学校的学生");
    }
}
//	@TEST
public class Example {
    public static void main(String[] args) {
        Student stu = new Student();
        stu.introduce();
    }
}
```





#### 抽象类和接口

##### 抽象类

:art:	定义类时，常需要定义一些方法来描述该类的行为特征，但有时这些方法的实现方式是无法确定的。这时候就需要 **抽象类**

+ Java **允许在定义方法时不写方法体**，不包含方法体的方法为抽象方法，抽象方法用 `abstract` 修饰

```java
	abstract woid shout ();
```

+ 抽象类

```java
abstract class Animal {
    abstract int shout();
}
```

+ **抽象方法的类必须声明为抽象类**，但抽象类可以不包含任何抽象方法。**抽象类是不可以被实例化的**，因为抽象类中有可能包含抽象方法，**抽象方法是没有方法体的，不可以被调用**
+ 如果想调用抽象类中定义的方法，则需要 **创建一个子类，在子类中将抽象类中的抽象方法进行实现**

```java
//	定义抽象类 Animal
abstract class Animal {
    //	定义抽象方法 shout()
    abstract void shout();
}
//	定义 Dog类继承抽象类的 Animal
class Dog extends Animal {
    //	实现抽象方法 shout()
    void shout () {
        System.out.println("汪汪汪...");
    }
}

//	@TEST
public class Example {
    public static void main(String[] args) {
        Dog dog = new Dog();	//子类继承父类的抽象方法后，可以正常进行实例化
        dog.shout();			//并通过实例化对象调用方法
    }
}
```





##### 接口

:art:	如果一个抽象类中的 **所有方法都是抽象的**，则可以将这个类用另一种方式来定义，即**接口**。接口是 **由常量和抽象方法组成的特殊类**，是对抽象类的进一步抽象。

+ 定义接口需要 `interface` 关键字来声明，其语法格式

```java
[public] interface 接口名 [extends 接口1，接口2] {
    [public] [static] [final] 数据类型 常量名 = 常量值;
    [public] [abstract] 返回值 抽象方法名（参数列表）;
}
```

> 一个接口可以有很多父接口，它们之间用逗号隔开。Java 使用接口的目的是为了克服单继承的限制。
>
> + 接口中的变量默认使用 `public static final` 修饰，即全局变量
> + 接口中的方法默认使用 `public abstract` 修饰，即抽象方法
> + 如果接口声明为 `public` ，则接口中的变量和方法全部为 `public`



+ 接口中的方法都是 **抽象方法**，不能通过实例化对象的方式调用接口中的方法
+ 需要定义一个类，并使用 `implements` 关键字实现接口中所有的方法
+ 一个类可以在继承另一个类的同时实现多个接口

```java
//接口实现类声明
//	[<修饰符>] class <类名> [extends <超类名>] [implements <接口1>,<接口2>,..]
```

```java
//定义 Animal接口
interface Animal {
    //定义全局变量，其默认修饰符为 public static final
    String ANIMAL_BEHAVIOR = "动物的行为";
    //定义抽象方法 breathe(),其默认修饰为 public abstract
    void breathe();
    //定义抽象方法 run()
    void ran();
}
//Dog 类实现了 Animal 接口
class Dog implements Animal {
    //实现 breathe() 方法
    public void breathe() {
        System.out.println(ANIMAL_BEHAVIOR + ":"+"狗在呼吸");
    }
    public void run () {
        System.out.println(ANIMAL_BEHAVIOR + ":" + "狗在奔跑");
    }
}
// @TEST
public class Example {
    public static void main (String[] args) {
        Dog dog = new Dog();
        dog.breathe();
        dog.run();
    }
}
```



+ 演示接口之间的继承关系

```java
//定义 Animal接口
interface Animal {
    //定义全局变量，其默认修饰符为 public static final
    String ANIMAL_BEHAVIOR = "动物的行为";
    //定义抽象方法 breathe(),其默认修饰为 public abstract
    void breathe();
    //定义抽象方法 run()
    void ran();
}
//定义 LandAnmial接口
interface LandAnimal extends Animal {
    void liveOnland();
}
//Dog 类实现了 Animal 接口
class Dog implements LandAnimal {
    //实现 breathe() 方法
    public void breathe() {
        System.out.println(ANIMAL_BEHAVIOR + ":"+"狗在呼吸");
    }
    //实现 run()方法
    public void run () {
        System.out.println(ANIMAL_BEHAVIOR + ":" + "狗在奔跑");
    }
    //实现 liveOnLand() 方法
    public void liveOnLand() {
        System.out.println("狗是陆地上的动物");
    }
}
// @TEST
public class Example {
    public static void main (String[] args) {
        Dog dog = new Dog();
        //使用 <对象名.常量名> 的方式输出接口中的常量
        System.out.println(dog.ANIMAL_BEHAVIOR);
        //使用 <接口名.常量名> 的方式输出接口中的常量
        System.out.println(Animal.ANIMAL_BEHAVIOR);
        dog.breathe();
        dog.run();
        dog.liveOnLand();
    }
}
```

:warning:	接口特点的归纳：

+ 接口中的方法都是抽象的，不能实例化对象
+ 接口中的属性只能是 **常量**
+ 当一个类实现接口时，如果这个类是抽象类，则实现接口中的部分方法即可，否则需要实现接口中的所有方法
+ 一个类可以通过 `class Bird implements Run,Fly `方式实现多个接口
+ 一个接口可以通过 `interface Eating extend Running,Flying {}` 继承多个接口
+ 一个类在继承另一个类的同时还可以实现接口，此时 `extends` 关键字必须位于`implements` 之前，示例  `class Dog extends Ganidae implements Animal{}`





#### 案例6 USB接口程序设计

![1551779902449](Java基础案例教程.assets/1551779902449.png)

+ 定义 `USB` 接口

```java
package cn.test;
public interface USB {
    void turnOn();
    void turnOff();
}
```

+ 编写鼠标、键盘和麦克风类，作为 USB接口的实现类，分别对 `turnOn()` 和`turnOff` 方法进行实现

1. 鼠标类的实现代码

```java
package cn.test
//鼠标
public class Mouse implements USB {
    public void turnOn() {
    	System.out.println("鼠标启动了");
    }
    public void turnOff() {
    	System.out.println("鼠标关闭了");
    }
}
```

2. 键盘类的实现代码

```java
package cn.test;
//键盘
public class KeyBoard implements USB {
    public void turnOn() {
		System.out.println("键盘启动了");
    }
    public void turnOff() {
    	System.out.println("键盘关闭了");
    }
}
```

3. 麦克风类的实现代码

```java
package cn.test;
//麦克风
public class Mic implements USB {
    public void turnOn() {
		System.out.println("麦克风启动了");
    }
    public void turnOff() {
    	System.out.println("键盘关闭了");
    }
}
```

4. 计算机类 Computer 实现代码

```java
package cn.test;
//计算机
public class Computer {
	//计算机上的 USB插槽
	private USB[] usbArr = new USB[4];
	//向计算机上连接一个 USB设备
    public void add(USB usb) {
    	//循环遍历所有插槽
        for (int i = 0; i < usbArr.length; i++) {
        	//如果发现一个空的
            if (usbArr[i] == null) {
            	//将 usb设备连接到这个插槽上
            	usbArr[i] = usb;
            	//连接上之后结束循环
            	break;
            }
        }
    }
    //计算机的开机功能
    public void powerOn() {
    	//循环遍历所有插槽
        for (int i =0; i < usbArr.length; i++) {
        	//如果发现有设备
            if (usbArr[i] != null) {
            	//将 USB设备启动
            	usbArr[i].turnOn();
            }
        }
        System.out.println("计算机开机成功");
    }
    //计算机关机功能
    public void powerOff() {
        for (int i = 0; i < usbArr.length; i++) {
            if(usbArr[i] != null) {
				usbArr[i].turnOff();
            }
        }
        System.out.println("计算机关机成功");
    }
}
```

4. 编写测试类

```java
package cn.test
//	@TEST
class Example {
    public static void main(String[] args) {
		//实例化计算机对象
		Computer c = new Computer();
		//向计算机中添加鼠标、麦克风和键盘设备
		c.add(new Mouse());
		c.add(new Mic());
		c.add(new KeyBoard());
		c.powerOn();	//启动计算机
		System.out.println("计算机运作中");
		c.powerOff();	//关闭计算机
    }
}
```





#### 多态

##### 多态概述

+ 在设计一个方法时，通常希望该方法具备一定的通用性。在同一个方法中，**传入的参数类型不同，而导致执行效果各异的现象就是多态**
+ 多态满足三个条件：**继承，重写，父类引用子类对象**

```java
//定义接口 Animal
interface Animal {
    void shout();	//定义抽象 shout()方法
}
//定义 Cat类实现 Animal 接口
class Cat implements Animal {
    //实现 shout()方法
    public void shout() {
        System.out.println("喵喵.....");
    }
}
//定义 Dog类实现 Animal接口
class Dog implements Animal {
    public void shout() {
        System.out.println("汪汪....");
    }
}
//	@TEST
public class Example {
    public static void main(String[] args) {
        Animal an1 = new Cat();	//创建 Cat对象，使用 Animal类型的变量 an1引用
        Animal an2 = new Dog();	//创建 Dog对象，使用 Animal类型的变量 an2引用
        animalShout(an1);	//调用 animalShout()方法，将 an1作为参数传入
        animalShout(an2);	//调用 animalShout()方法，将 an2作为参数传入
    }
    //定义静态的 animalShout()方法，接收一个 Animal类型的参数传入
    public static void animalShout(Animal an) {
        an.shout();	//调用实际参数的 shout()方法
    }
}
```

> + 多态实现了父类类型变量引用不同的子类对象，产生不同结果
> + 多态解决了方法同名的问题，还使程序变化更加灵活，从而有效地提高了程序的可扩展性和可维护性



###### 对象的类型转换

+ 向上造型

```java
	Animal an1 = new Cat();	//将 Cat对象当作 Animal类型来使用
	Animal an2 = new Dog();	
```

> + 将子类对象当作父类使用时不需要任何显式地声明，但此时不能通过父类变量去调用子类中的特有方法

```java
//定义 Animal接口
interface Animal {
    void shout();
}
//定义 Cat类实现 Animal方法
class Cat implements Animal {
    //实现抽象方法 shout()
    public void shout() {
        System.out.println("喵喵...");
    }
    //定义 sleep()方法
    void sleep() {
        System.out.println("猫睡觉......");
    }
}
//	@TEST
public class Example {
    public static void main(String[] args) {
        Cat cat = new Cat();	//创建 Cat类的实例对象
        animalShout(Cat);	//调用animalShout()方法，将 Cat作为参数传入
    }
    //定义静态方法 animalShout(),接收一个 Animal类型的参数
    public static void animalShout(Animal animal) {
    // 需要将 animal对象强行转化未 Cat类型，因为 animal对象中没有 sleep()方法
        Cat cat = (Cat) animal;
        animal.shout();	//调用传入参数 animal的 shout()方法
        animal.sleep();	//调用传入参数 animal的 sleep()方法
    }
}
```

+ 上面将父类型当作子类型使用的情况，在 Java里称 **向下造型**

:warning:   针对类型是否传入正确， Java提供了关键字 `instanceof` ，判断一个对象是否为某个类（接口）的实例或者子类实例



###### Object类

+ 在 JDK 中提供了一个 `Object`类，它是 **类层次结构的根类，每个类都直接或间接继承自该类**，所有对象（包括数组）都实现了这个类的方法

![1551802460209](Java基础案例教程.assets/1551802460209.png)

+ Object 中的 toString() 方法中的代码

![1551802604776](Java基础案例教程.assets/1551802604776.png)

```java
//在实际开发中，希望对象的 toString()方法返回的不仅是基本信息，还有特有的信息
//重写 Object的 toString() 方法
class Animal {
    //开始重写
    public String toString() {
        return "这是一个动物。。。";
    }
}
//	@TEST
public class Example {
    public static void main (String[] args) {
        Animal animal = new Animal();	//创建 Animal类对象
        System.out.println(animal.toString());	//调用重写的方法并打印
    }
}
```



###### 匿名内部类

+ 在类里面定义的类称为内部类（inner Class),内部类是外部类的一个成员
+ 内部类可分为 **成员内部类、方法内部类、匿名内部类等
  + 在接口的实现中出来定义外部类继承，还可使用 **匿名内部类来实现**

```java
//	使用内部类的方式实现
interface Animal {
    void shout();
}
//	@TEST
public class Example {
    public static void main (String[] args) {
        //定义一个内部类 Cat 实现 Animal 接口
        class Cat implements Animal {
            public void shout() {
                System.out.println("喵喵....");
            }
        }
        animalShout(new Cat());	//调用 animalShout() 方法并传入 Cat 对象
    }
    //定义静态方法 animalShout()
    public static void animalShout(Animal an) {
        an.shout();
    }
}
```

```java
//	使用匿名内部类的方式实现
interface Animal {
    void shout();
}
//	@TEST
public class Example {
    public static void main (String[] args) {
		//定义一个匿名内部类作为参数传递给 animalShout() 方法
        animalShout(new Animal() {
            //实现 shout()
            public void shout() {
                System.out.println("喵喵.....");
            }
        })
    //定义静态方法 animalShout()
    public static void animalShout(Animal an) {
        an.shout();
    }
}
```





#### 案例7 模拟物流快递系统程序设计

![1551840278791](Java基础案例教程.assets/1551840278791.png)

+ 定义一个交通工具类 Transportation,该类是一个抽象类，包含交通工具信息和运输方法

```java
package cn.transport;
//交通工具类
public abstract class Transportation {
    private String number;	//编号
    private String model;	//型号
    private String admin;	//运货负责人
    public Transportation() {
        super();	//可省略
    }
    public Transportation(String number, String model, String admin) {
        this.number = number;
        this.model = model;
        this.admin = admin;
    }
    //运输方法
    public abstract void transport();
    //编号
    public void setNumber(String number) {
        this.number = number;
    }
    public String getNumber() {
        return number;
    }
    //型号
    public void setModel(String model) {
        this.model = model;
    }
    public String getModel() {
        return model;
    }
    //负责人
    public void setAdmin(String admin) {
        this.admin = admin;
    }
    public String getAdmin() {
        return admin;
    }
}
//定义了车的编号、车辆类型和负责人，还提供了各自的 set和get 方法
```

+ 定义交通工具保养接口 Careable,该接口包含车辆保养的方法

```java
package cn.transport;
//定义保养接口，具备保养功能
public interface Careable {
    //保养方法
    public abstract void upKeep();
}
```

+ 定义专用运输车类 Ztransportation,继承于交通工具类，并实现保养接口

```java
package cn.transport;
//专用运输车类
public class ZTransportation extends Transportation implements Careable {
    //无参构造
    public ZTansportation () {
        super();
    }
    //有参构造（车辆编号、型号、负责人）
    public ZTransportation(String number, String model, String admin) {
        super(number, model, admin);
    }
    //运输方法
    public void transport() {
        System.out.println("运输进行中");
    }
    //重写车辆保养方法
    public void upKeep() {
        System.out.println("货物运输车辆保养完毕！");
    }
}
```

+ 定义快递任务类 SendTask

```java
package cn.transport;
//快递任务类
public class SendTask {
	private String number;	//快递单号
	private double goodsWeight;//货物重量
    public SendTask() {
    	super();
    }
    public SendTask(String number, double goodsWeight) {
    	this.number = number;
    	this.goodsWeight = goodsWeight;
    }
    //送前准备
    public void sendBefore () {
    	System.out.println("订单开始处理，仓库验货中.....");
    	System.out.println("货物重量:" + this.getGoodsWeight() + "kg");
    	System.out.println("货物检验完毕！");
    	System.out.println("货物装填完毕");
    	System.out.println("运货人已通知");
    	System.out.println("快递单号：" + this.getNumber());
    }
    //发送货物
    public void send(Transportation t, GPS tool) {
    	System.out.println("运货人" + t.getAdmin()
    	+"正在驾驶编号为" + t.getNumber() + "的" 
    	+ t.getModel() + "发送货物!");
    	t.transport();
    	String showCoordinate = tool.showCoordinate();
    	System.out.println("货物当前的坐标为：" + showCoordinate);
    }
    //送后操作
    public void sendAfter(Transportation t) {
    	System.out.println("货物运输任务已完成");
    	System.out.println("运货人" + t.getAdmin() + "所驾驶的编号为"
    	+ t.getNumber() + "的" + t.getModel() + "已归还！");
    }
    public String getNumber() {
    	return number;
    }
    public void setNumber(String number) {
    	this.number = number;
    }
    public double getGoodsWeight() {
    	return goodsWeight;
    }
    public void setGoodsWeight(double goodsWeight) {
    	this.goodsWeight = goodsWeight;
    }
}
```

+ 定义包含显示位置功能的 GPS接口和实现类 Phone

```java
package cn.transport;
//定义 GPS接口，具备 GPS定位功能
public interface GPS {
    //显示坐标的方法
    public String showCoordinate();
}
```

+ 定义手机类实现 GPS接口

```java
package cn.transport;
//定义一个手机类，实现 GPS接口，拥有定位功能
class Phone implements GPS {
    public Phone() {	//空参构造
        super();
    }
    //定位方法
    public String showCoordinate () {
        String location = "193,485";
        return location;
    }
}
```

+ 定义测试类

```java
package cn.transport;
//	@TEST
public class Example {
    public static void main(String[] args) {
        //快递任务类对象
        SendTask task = new SendTask("HB",78.2);
        //调用送前准备方法
        task.sendBefore();
        System.out.println("====================");
        //创建交通工具对象
        ZTransportation t = new ZTransportation("Z025","奔驰","宝马");
        //创建GPS工具对象
        Phone p = new Phone();
        //将交通工具与 GPS工具传入送货方法
        task.send(t,p);
        System.out.println("===================");
        //调用送后操作方法
        task.sendAfter(t);
        t.upKeep();
    }
}
```







#### 异常

+ 在计算机的使用过程中，我们可能遇到蓝屏、死机、网络连接中断，磁盘空间不足等各种问题。**针对这种情况，Java 语言引入了异常处理机制**，**以异常类的形式对这些非正常情况进行封装**
+ Java 中提供了大量的异常类，这些类都继承自 `java.lang.Throwable`

![1552031352509](Java基础案例教程.assets/1552031352509.png)

+ `Throwable` 有两个直接子类 `Error(程序中产生的错误)` 和 `Exception(产生的异常)` 

![1552031539959](Java基础案例教程.assets/1552031539959.png)



+ Throwable 类中的常用方法罗列

![1552031633487](Java基础案例教程.assets/1552031633487.png)





##### try...catch 和 finally

+ 由于发生了异常导致终止的程序无法运行，为了解决这样的问题，提供了**对异常进行特殊处理的方式—异常捕获**

```java
public class Example {
    public static void main (String[] args) {
        //下面定义一个 try...catch 语句用于捕获异常
        try {
            int result = divide(4,0);
            System.out.println(result);
        } catch (Exception e) {	//对异常进行处理
            System.out.println("捕获的异常信息为:" + e.getMessage());
        }
        System.out.println("程序继续向下执行...");
    }
    //定义的方法实现两个数相除
    public static int divide(int x, int y) {
        int result = x / y;
        return result;
    }
}
```

+ 在程序中， **有时候会希望有些语句无论程序是否发生异常都要执行，这是就可以在 `try ...catch ` 后面加上一个 `finally` 代码块**

```java
public class Example {
    public static void main (String[] args) {
        //下面定义一个 try...catch 语句用于捕获异常
        try {
            int result = divide(4,0);
            System.out.println(result);
        } catch (Exception e) {	//对异常进行处理
            System.out.println("捕获的异常信息为:" + e.getMessage());
            return;	//用于结束当前语句
        } finally {
            System.out.println("进入 finally代码块");
        }
        System.out.println("程序继续向下执行...");	// 未被执行
    }
    //定义的方法实现两个数相除
    public static int divide(int x, int y) {
        int result = x / y;
        return result;
    }
}
```

+ 无论程序是否发生异常，`finally` 中的语句都会执行。**由于这种特殊性，在程序设计时，经常会在 `try...catch` 后使用 `finally` 来完成必须做的事情（释放系统资源）**
+ `finally` 在一种情况下执行不了，就是在 `try...catch` 中执行了 `System.exit(0)`（提前退出虚拟机，任何代码都不会执行）





##### throws关键字

+ 调用别人方法时可能不知道可能会发生什么异常，针对这种情况，**Java 中允许在方法的后面使用 `throws`  关键字对外声明该方法有可能发生的异常**，调用者必须自行处理，否则编译不会通过

![1552033258723](Java基础案例教程.assets/1552033258723.png)

+ 在调用方法的时候，如果不知道如何处理声明抛出的异常，也可以使用** throws继续将异常抛出，这样程序也能编译通过**
+ 但是程序一旦发生异常，如果没有被处理，程序就会非正常终止

```java
public class Example {
    public static void main(String[] args) throws Exception {
        int result = divide(4,0);
        System.out.println(result);
    }
    //实现两个整数相除，并使用 throws 关键字声明抛出异常 
    public static int divide(int x, int y) throws Exception {
        int result = x / y;
        return result;
    }
}
```







##### 运行时异常与编译时异常

+ 运行时异常是 **程序在运行时产生的，即使不编写异常处理代码，依然可以通过编译**
+ 编译时异常是 **程序编译时产生的一些异常，这些异常必须要处理**

> 1. 编译时异常
>
> + Exception 类中除了 RuntimeException 类及其子类外都是编译时异常
> + 处理编译时异常的方式
>   + 使用 try...catch语句对异常进行捕获
>   + 使用 throws 关键字声明抛出异常，调用者对其处理
>
> 2. 运行时异常
>
> + RuntimeException类及其子类都是运行时异常
> + 编译器不会报错，程序可以编译通过
> + 一般是由程序中的逻辑错误引起的，在程序运行时无法恢复





##### 自定义异常

+ Java 中虽然提供了大量的异常类，但是在实际开发中，有时可能需要描述程序中特有的异常情况
+ 自定义的异常类必须继承自 `Exception` 或者其子类

```java
//下面的代码是自定义一个异常类继承自 Exception
public class DivideByMinusException extends Exception {
    public DivideByMinusException() {
        super();//调用Exception 无参构造方法
    }
    public DivideByMinusException (String message) {
        super(message);//调用Exception有参的构造方法
    }
}
//在实际开发中，如果没有特殊要求，只需继承类，然后在构造方法中使用 super()调用 Exception的构造方法
```

+ 使用自定义异常处理类
+ 使用 `throws` 关键字抛出异常对象时，需要有 `try...catch` 语句对抛出的异常进行处理，或者在 divide()方法上使用 throws 声明继续抛出异常，**由该方法的调用者负责处理**

```java
public class Example {
    public static void main(String[] args) {
        try {
            int result = divide (4,-2);
        	System.out.println(result);
        } catch (DivideByMinusException) {
            System.out.println(e.getMessage());
        }
    }
    public static int divide (int x, int y) {
        if (y < 0) {
            //使用throws 关键字声明异常对象
            throws new DivideByMinusException("除数是负数");
        }
        int result = x / y;
        return result;
    }
}
```







#### 访问控制

:art:	在 Java中，针对类、成员方法和属性提供了 4种访问级别，分别是 `private、default、protected、public` 

![1552035889147](Java基础案例教程.assets/1552035889147.png)

![1552035922087](Java基础案例教程.assets/1552035922087.png)

![1552035952549](Java基础案例教程.assets/1552035952549.png)





### Java API

***

#### String 类 和 StringBuffer 类

:art:	在  Java语言中，提供了这两个类来封装字符串，并提供了一系列操作字符串的方法

 

##### String类的初始化

1. 使用字符串常量直接初始化

```java
String str1 = "abc";
```

2. 使用 String的构造方法初始化

![1552036567963](Java基础案例教程.assets/1552036567963.png)

```java
public class Example {
    public static void main(String[] args) throws Exception {
        //创建一个空的字符串
        String str1 = new String();
        //创建一个内容为abcd的字符串
        String str2 = new String("abcd");
        //创建一个内容为字符数组的字符串
        char[] charArr = new char[] {'d','e','f'};
        String str3 = new String(charArr); 
        System.out.println("a" + str1 + "b");
        System.out.println(str2);
        System.out.println(str3);
    }
}
```



##### String类的常见操作

![1552102604537](Java基础案例教程.assets/1552102604537.png)

![1552102664923](Java基础案例教程.assets/1552102664923.png)



###### 字符串的基本操作

```java
public class Example {
    public static void main(String[] args) {
        String s = "abadadjlajdlab";	//声明字符串
        System.out.println("字符串的长度为:" + s.length());
        System.out.println("字符串中的第一个字符:" + s.charAt(0));
        System.out.println("字符串c第一次出现的位置:" + s.indexOf('c'));
        System.out.println("字符串c最后一次出现的位置: " + s.lastIndexOf('c'));
        System.out.println("子字符串第一次出现的位置: " + s.indexOf("ab"));
        System.out.println("子字符串最后一次出现的位置: " 
                           + s.lastIndexOf("ab"));
    }
}
```



###### 字符串的转换操作

```java
public class Example {
    public static void main(String[] args) {
        String str = "abcd";
        System.out.println("将字符串转换为字符数组后的结果：");
        char[] charArray = str.toCharArray();	//转化为字符数组
        for (int i = 0; i < charArray.length; i++) {
            if (i != charArray.length - 1) {
                //如果不是数组的最后一个元素，在元素后面加逗号
                System.out.println(charArray[i] + ",");
            } else {
                //数组的最后一个元素不加逗号
                System.out.println(charArray[i]);
            }
        }
        System.out.println("将 int值转换为 String类型之后的结果：" + 
                          String.valueOf(12));
        System.out.println("将字符串转换为大写之后的结果："  +
                           str.toUpperCase());
     }
}
```



###### 字符串的替换和去除空格操作

```java
public class Example {
    public static void main(String[] args) {
        String s = "itcast";
        //字符串替换操作
        System.out.println("将 it 替换成 cn.it 的结果：" + 
                           s.replace("it", "cn.it"));
        //字符串去除空格操作
        String s1 = "     i t c a st   ";
        System.out.println("去除字符串两端空格后的结果：" + s1.trim());
        System.out.println("去除字符串中所有空格后的结果：" + 
                           s1.replace(" ",""));
    }
}
```



###### 字符串的判断操作

```java
public class Example {
    public static void main(String[] args) {
        String s1 = "String";
        String s2 = "Str";
        System.out.println("判断是否以字符串 Str开头:" + s1.startsWith("str"));
        System.out.println("判断是否以字符串ng结尾：" + s1.endWith("ng"));
        System.out.println("判断是否包含字符串 tri:" + s1.contains("tri"));
        System.out.println("判断字符串是否为空：" + s1.isEmpty());
        System.out.println("判断两个字符串是否相等:" + s1.equals(s2));
    }
}
```

> 在程序中可以通过 "=="   和   equals()	 两种方式对字符串进行比较
>
> + `==` 是判断两个字符串对象的地址是否相同
> + `equals()` 判断两个字符串内容是否相同



###### 字符串的截取和分割

```java
public class Example {
    public static void main(String[] args) {
        String str = "羽毛球-篮球-网球";
        //下面是字符串截取操作
        System.out.println("从第 5个字符截取到末尾的结果：" + 
                           str.substring(4));
        System.out.println("从第5个字符截取到第6个字符的结果：" + 
                          str.substring(4,6));
        //下面是字符串分割操作
        System.out.println("分割后的字符串数组中的元素依次为：");
        String[] strArray = str.split("-");
        for (int i = 0; i < strArray.length; i++) {
            if (i != strArray.length - 1) {
                //如果不是数组的最后一个元素，在元素后面加逗号
                System.out.println(strArray[i] + ",");
            } else {
                System.out.println(strArray[i]);
            }
        }
     }
}
```

![1552105596324](Java基础案例教程.assets/1552105596324.png)





##### StringBuffer类

:art:	由于字符串是常量，一旦创建不能修改。为了便于对字符串进行修改，在 JDK中提供了 `StringBuffer` 类（字符串缓冲区）。这两个类最大的区别在于**内容和长度是否可以修改**

，**StringBuffer 类似一个字符容器，当在其中添加或删除字符时，并不会产生新的 StringBuffer 对象**

![1552106450926](Java基础案例教程.assets/1552106450926.png)

```java
public class Example {
    public static void main(String[] args) {
        System.out.println("1、添加-----------");
        add();
        System.out.println("2、删除------------");
        remove();
        System.out.println("3、修改------------");
        alter();
    }
    public static void add() {
        StringBuffer sb = new StringBuffer();	//定义一个字符串缓冲区
        sb.append("dwadawdakjdwkjd");
        System.out.println("append添加结果：" + sb);
        sb.insert(2,"123");	//在指定位置插入字符串
        System.out.println("insert添加结果：" + sb);
    }
    public static void remove() {
        StringBuffer sb = new StringBuffer("abcdefg");
        sb.delete(1,5);
        System.out.println("删除指定位置结果：" + sb);
        sb.deleteCharAt(2);
        System.out.println("删除指定位置结果：" + sb);
        sb.delete(0, sb.length());
        System.out.println("清空缓冲区结果：" + sb);
    }
    public static void alter() {
        StringBuffer sb = new StringBuffer("abcdef");
        sb.setCharAt(1, 'p');
        System.out.println("修改指定位置字符结果：" + sb);
        sb.replace(1, 3, "qq");
        System.out.println("替换指定位置字符串结果：" + sb);
        System.out.println("字符串反转结果：" + sb.reverse());
    }
}
```



##### String类和StringBuffer类的不同

![1552189833834](Java基础案例教程.assets/1552189833834.png)

![1552189978905](Java基础案例教程.assets/1552189978905.png)







#### 案例8  记录一个子串在整串中中出现的次数

![1552190108412](Java基础案例教程.assets/1552190108412.png)

```java
public class Example {
    public static void main(String[] args) {
        String str = "dakdsjdkajdkwajdkwuir";
        String key = "aj";
        int count = getKeyStringCount(str,key);
        System.out.println("count =" + count);
    }
    //获取子串出现的次数
    public static int getKeyStringCount(String str, String key) {
        //定义计数器，记录出现次数
        int count = 0;
        //如果整串不包含子串，则直接返回 count
        if (! str.contains(key)) {
            return count;
        }
        //定义变量记录 key出现的位置
        int index = 0;
        while ((index = str.indexOf(key)) != -1) {
            str = str.substring(index + key.length());
            count++;
        }
        return count;
    }
}
```







#### System类和Runtime类

+++

##### System类

+ 该类定义了一些 **与系统相关的属性和方法，它所提供的属性和方法都是静态的。可以直接调用**

![1552190930885](Java基础案例教程.assets/1552190930885.png)



+ `getProperties()` 方法 **用于获取当前系统的全部属性，会返回一个 Properties对象。封装的系统属性以键值对形式存在**

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        //获取当前系统属性
        Properties properties = System.getProperties();
        System.out.println(properties);
        //获取所有系统属性的 key（属性名），返回 set对象
        Set<String> propertyNames = properties.stringPropertyNames();
        for (String key : propertyNames) {
            //获取当前键 key （属性名）所对应的值（属性值）
            String value = System.getProperty(key);
            System.out.println(key + "--------->" + key);
        }
    }
}
```

![1552191658619](Java基础案例教程.assets/1552191658619.png)



+ `currentTimeMillis()` 返回一个long类型的值，该值表示当前时间与**1970年1月1日0点0分0秒之间的时间差**，也称时间戳

```java
public class Example {
    public static void main(String[] args) {
        long startTime = System.currentTimeMillis();
        int sum = 0;
        for (int i = 0; i < 10000000; i++) {
            sum += i;
        }
        long endTime = System.currentTimeMillis();
        System.out.println("程序运行的时间为：" + (endTime - startTime) + "毫秒");
    }
}
```



+ `arraycopy(Object src, int srcPos, Object desk, int deskPos, int length)`
+ 该方法用于将一个数组中的元素快速拷贝到另一个数组

![1552192401293](Java基础案例教程.assets/1552192401293.png)

```java
public static Example {
    public static void main(String[] args) {
        int [] fromArray = {101, 102, 103, 104, 105, 106};
        int [] toArray = {201, 202, 203, 204, 205, 206, 207};
        System.arraycopy(fromArray, 2, toArray, 3, 4);
        //打印目标数组的元素
        for (int i = 0; i <toArray.length; i++) {
            System.out.println(i + ":" + toArray[i]);
        }
    }
}
```





##### Runtime类

+ Runtime类表示虚拟机运行时的状态，用于封装 JVM虚拟机进程。**每次使用 java命令启动虚拟机都对应一个 Runtime实例，且只有一个实例**
+ Runtime 类 **采用单例模式进行设计，对象不可以直接实例化**

```java
public class Example {
    public static void main(String[] args) {
        Runtime rt = Runtime.getRuntime();	//获取实例
        System.out.println("处理器的个数：" + rt.availableProcessors() +　"个");
       	System.out.println("空闲内存数量:" + rt.ferrMemory()/1024/1024 + "M");
        System.out.println("最大可用内存数量：" + rt.maxMemory()/1024/1024 + "M");
    }
}
```



+ Runtime类中提供一个 `exec()`方法，**可执行一个 dos命令，实现与命令行中输入 dos命令相同的结果**

```java
import java.io.IOException;
public class Example {
    public static void main(String[] args) throws IOException {
        Runtime rt = Runtime.getRuntime();
        Process process = rt.exec("qq.exe");//获取进程的对象
        Thread.sleep(3000);	//休眠3秒
        process.destroy();//杀掉进程
    }
}
```





#### Math类与Random类

---

##### Math类

+ 数学操作类，提供一些列用于数学计算的静态方法（绝对值、三角函数）
+ 其中有两个静态常量 PI 和 E

```java
public class Example {
    public static void main(String[] args) {
        System.out.println("计算绝对值的结果：" + Math.abs(-1));
        System.out.println("求大于参数的最小整数：" + Math.ceil(5.6));
        System.out.println("求小于参数的最大整数：" + Math.floor(-4.2));
        System.out.println("求小数进行四舍五入后的结果：" + Math.round(-4.6));
        System.out.println("求两个数的较大值：" + Math.max(2.1,-2.1));
        System.out.println("求两个数的较小值：" + Math.min(2.1,-2.1));
        System.out.println("生成一个大于0小于1的随机值：" + Math.random());
    }
}
```

> + round()方法用于对小数进行四舍五入，会将小数后面的数字全部忽略，返回一个 int类型的数
> + ceil() 和 floor() 返回的都是 double类型的数。这个数在数值上等于一个整数



##### Random类

+ 随机产生两个数字，在此类里提供了两个构造方法

![1552317126533](Java基础案例教程.assets/1552317126533.png)

```java
import java.util.Random;
public class Example {
    public static void main(String[] args) {
        Random r = new Random();//不传入种子
        //随机产生10个[0,100]之间的整数
        for (int x = 0; x < 10; x++) {
            System.out.println(r.nextInt(100));
        }
        Random r2 = new Random(13);	//当传入相同的种子时，第二次产生的随机数将相同
        for (int i = 0; i < 10; i++) {
            System.out.println(r2.nextInt(100));
        }
    }
}
```

![1552317174924](Java基础案例教程.assets/1552317174924.png)

```java
import java.util.Random;
public class Example {
    public static void main(String[] args) {
        Random r1 = new Random();//创建Random实例对象
        System.out.println("产生float类型随机数：" + r1.nextFloat());
        System.out.println("产生0~100之间的int 类型的随机数：" + r1.nextInt(100));
        System.out.println("产生double类型的随机数：" + r1.nextDouble());
    }
}
```





#### 包装类

+ 在 Java中，很多类的方法都需要接收引用类型的对象，此时无法将一个基本数据类型的值传入。在JDK中提供了一系列的包装类，将 **基本数据类型的值包装为引用数据类型的对象**



+ 装箱是指基本数据类型的值转为引用数据类型，拆箱是指将引用数据类型的对象转为基本数据类型

![1552317224894](Java基础案例教程.assets/1552317224894.png)

![1552317270668](Java基础案例教程.assets/1552317270668.png)

```java
//演示拆箱方法
public class Example {
    public static void main(String[] args) {
        Integer num = new Integer(20);
        int a = 10;
        int sum = num.intValue() + a;
        System.out.println("sum = " + sum);
    }
}
```

```java
//演示 parseInt用法
public class Example {
    public static void main(String[] args) {
        int w = Integer.parseInt("20");
        int h = Integer.parseInt("10");
        for (int i = 0; i < h; i++) {
            StringBuffer sb = new StringBuffer();
            for (int j = 0; j < w; j++) {
                sb.append("*");
            }
            System.out.println(sb.toString());
        }
    }
}
```



##### 包装类注意的事项

+ 包装类都重写了 `Object` 类中的 `toString()` 方法，以 **字符串的形式返回被包装的基本数据类型的值**
+ 除了 `Character` 外，包装类都有 `valueOf(String s)` 方法，参数字符串不能为空，不能带有非法字符

```java
Integer i = Integer.valueOf("123");		//合法
Integer i = Integer.valueOf("123a");	//非法
```

+ 除了 `Character` 外，包装类都有 `parseXXX（String s）` 的静态方法，将字符串转换为对应的数据类型，参数不能为空，不能含有其他非法数据
+ `JDK 5新特性` 自动拆箱和自动装箱,有了这个特性，程序可以进行混合数学运算

```java
int num = 20;
Integer number = num;	//自动装箱
//相当于之前的	Integer number = new Integer(num)
Integer number = new Integer(19);
int num = number;
//相当于之前的	int num = number.intValue()
public static Integer add(Integer a, Integer b) {
    return a + b;
}
```





#### 案例9 字符串排序程序设计

![1552317333856](Java基础案例教程.assets/1552317333856.png)

```java
import java.util.Arrays;
public class Example {
    private static final String SPACE_SEPARATOR = " ";//这里的字符若没有空格，将运行出错
    public static void main(String[] args) {
        String numStr = "20 78 9 -7 88 36 29";
        System.out.println(numStr);
        numStr = sortStringNumber(numStr);
        System.out.println(numStr.toString());
    }
    public static String sortStringNumber(String numStr) {
        //1.将字符串变成字符串数组
        String[] str_arr = stringToArray(numStr);
        //2.将字符串数组变成 int 数组
        int [] num_arr = toIntArray(str_arr);
        //3.对 int数组排序
        mySortArray(num_arr);
        //2.将排序后的 int数组变成字符串
        String temp = arrayToString(num_arr);
        return temp;
    }
    public static String arrayToString(int[] num_arr) {
        StringBuffer sb = new StringBuffer();
        for(int i = 0; i < num_arr.length; i++) {
            if(i != num_arr.length - 1) {
                sb.append(num_arr[i] + SPACE_SEPARATOR);
            } else {
                sb.append(num_arr[i]);
            }
        }
        return sb.toString();
    }
    public static void mySortArray(int[] num_arr) {
        Arrays.sort(num_arr);
    }
    public static int[] toIntArray(String[] str_arr) {
        int[] arr = new int[str_arr.length];
        for(int i = 0; i < arr.length; i++) {
            arr[i] = Integer.parseInt(str_arr[i]);
        }
        return arr;
    }
    public static String[] stringToArray(String numStr) {
        String[] str_arr = numStr.split(SPACE_SEPARATOR);
        return str_arr;
    }
}
```





##### switch语句支持字符串类型（JDK7.0）

```java
public class Example {
    public static void main(String[] args) {
        String week = "Friday";
        switch(week) {
            case "Monday":
                System.out.println("星期一");
                break;
            case "Tuesday":
                System.out.println("星期二");
                break;
            case "Wednesday":
                System.out.println("星期三");
                break;
            case "Thursday":
                System.out.println("星期四");
                break;
            case "Friday":
                System.out.println("星期五");
                break;
            case "Saturday":
                System.out.println("星期六");
                break;
            case "Sunday":
                System.out.println("星期日");
                break;
            default:
                System.out.println("星期您输入有误");
        }
    }
}
```







### 集合类

---

+ 在程序中通过数组来保存多个对象，但在某些情况下开发人员无法预先确定需要保存对象的个数，这时候就需要一系列特殊的类
+ **集合**可以存储任意类型的对象，并且长度可变

![1552352467356](Java基础案例教程.assets\1552352467356.png)

![1552352526000](Java基础案例教程.assets\1552352526000.png)

+ 虚线框里填写的都是**接口类型**，而实线框都是**具体的实现类**



#### Collection接口

+ `Collection` 是所有单列集合的父接口，这个接口定义了可以操作所有的单列集合

![1552352863196](Java基础案例教程.assets\1552352863196.png)



#### List接口

+ 继承自 Collection接口，习惯性将实现了List接口的对象称为 List集合
+ 在 List集合中允许出现重复的元素，所有的元素是以一种**线性方式进行存储，可通过索引来访问集合中的指定元素**

![1552353084802](Java基础案例教程.assets\1552353084802.png)



##### ArrayList集合

+ ArrayList 内部封装了一个**长度可变的数组对象，当存入的元素超过数组长度时，ArrayList 会在内存中自动分配一个更大的数组**

```java
import java.util.*;
public static void main(String[] args) {
    ArrayList list = new ArrayList();//创建集合
    list.add("stu1");
    list.add("stu2");
    list.add("stu3");
    System.out.println("集合的长度:" + list.size());
    System.out.println("第2个元素是：" + list.get());
}
```

+ 由于 ArrayList集合的底层是使用一个数组来保存元素的，在增加或删除指定位置的元素时，会创建新的数组，效率比较低。**不适合做大量的增删操作**
+ 这种数组的结构允许程序通过**索引的方式来访问元素，因此使用ArrayList集合查找元素很便捷**

![1552354114871](Java基础案例教程.assets\1552354114871.png)



##### LinkedList集合

+ 为了克服 ArrayList集合查找快速，但是增删效率低的问题，**可使用 List接口的另一个实现类 LinkedList**
+ 该集合内部维护了一个双向循环链表，实现效果图

![1552354322898](Java基础案例教程.assets/1552354322898.png)

+ 原理：新增一个元素的时候，只是让元素1记住它后面的元素是新元素，让元素2记住它前面的元素为新元素

![1552354961876](assets/1552354961876.png)

```java
import java.util.*;
public class EXample {
    public static void main(String[] args) {
        LinkedList link = new LinkedList();	//创建LinkedList集合
        link.add("stu1");
        link.add("stu2");
        link.add("stu3");
        link.add("stu4");
        System.out.println(link.toString());//打印该集合的元素
        link.add(3,"Student");//向该集合中指定位置插入元素
        link.addFirst("First");//向该集合第一个位置插入元素
        System.out.println(link);
        System.out.println(link.getFirst());//取出该集合的第一个元素
        link.remove(3);//移除该集合指定位置的元素
        link.removeFirst(3);
        System.out.println(link);
    }
}
```





##### Iterator接口

+ 实际开发中，经常需要遍历集合中的元素，这时候就需要用到 迭代器
+ Collection接口与 Map接口主要用于存储元素，而 **Iterator主要用于迭代访问（遍历）Collection**

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        ArrayList list = new ArrayList();
        list.add("data-1");
        list.add("data-2");
        list.add("data-3");
        list.add("data-4");
        Iterator it = list.iterator();	//获取 Iteration对象
        whihe(it.hasNext()) {	//判断 ArrayList中是否存在下一个元素
            Object obj = it.next();//取出 ArrayList集合中的元素
            System.out.println(obj);
        }
    }
}
```

+ Iterator 遍历集合的整个过程：
  + 调用 ArrayList集合的 `Iterator()` 方法获得迭代器对象
  + 使用 `hasNext()` 判断集合中是否存在下一个元素
  + 存在则通过 `next()` 方法获取元素，否则说明到达集合末尾，停止遍历元素
+ 需要注意的是使用 `next()` 方法获取元素时，必须保证要获取的元素存在，否则抛出 `NoSuchElementException` 异常
+ 通过 Iterator获取 ArrayList集合中的元素时，会把这些元素当作 Objectl类型来看待，如果想得到特定类型的元素，则需要进行强制类型转换

![1552357212992](F:\Coding\Habit\BookNote\Java基础程序案例\Java基础案例教程.assets\1552357212992.png)





##### foreach循环(JDK 5.0)

+ Iterator 可以用来遍历集合中的元素，但是写法繁琐，为了简化就提供了 foreach循环

```java
for (容器中元素类型 临时变量 ： 容量变量)  {
    执行语句；
}
```

+ foreach 循环不需要获得**容器的长度，也不需要根据索引访问容器中的元素，它会自动遍历容器中的每个元素**

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        ArrayList list = new ArrayList();
        list.add("Jack");
        list.add("Rose");
        list.add("Tom");
        for (Object obj : list) {
            System.out.println(obj);
        }
    }
}
```

+ foreach 循环虽然书写简洁，但是在遍历集合和数组时，**只能访问集合中的元素，不能对其中的元素进行修改**

```java
public class Example {
    static String[] strs = {"aaa", "bbb", "ccc"};
    public static void mian(String[] args) {
        //foreach循环遍历数组
        for (String str : strs) {
            str = "ddd";
        }
        System.out.println("foreach循环修改后的数组："  + strs[0] + "," + strs[1] + "," + strs[2]);
        //for循环遍历数组
        for(int i = 0; i < strs.length; i++) {
            strs[i] = "ddd"
        }
        System.out.println("普通for循环修改后的数组："  + strs[0] + "," + strs[1] + "," + strs[2]);
    }
}
```

+ 在使用 Iterator 迭代器对集合进行迭代时，如果调用了 `remove()` 方法去删除元素之后，继续使用迭代器遍历元素，会出现异常

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        ArrayList list = new ArrayList();
        list.add("Jack");
        list.add("Annie");
        list.add("Rose");
        list.add("Tom");
        Iterator it = list.iterator();
        while(it.hasNext()) {	//判断是否有下一个元素
            Object obj = it.next();//获取元素
            if ("Annie".equals(obj)) {
                list.remove(obj);	
                //会抛出错误，在删除之后会到导致迭代器预期的迭代次数发生改变
            }
        }
        System.out.println(list);
    }
}
```

+ 两种处理方式：

1. 找到该学生后跳出循环不再迭代，意味着退出迭代的过程

```java
if ("Annie".equals(obj)) {
    list.remove(obj);
    break;
}
```

2. 使用迭代器本身的删除方法

```java
if ("Annie".equals(obj)) {
    it.remove();
}
```





#### 案例10 模拟KTV点歌

![1552360300348](assets/1552360300348.png)

```java
//使用 LinkedList集合模拟点歌系统
import java.util.LinkedList;
import java.util.Scanner;
public class KTVByLinkedList {
    public static void main(String[] args) {
        System.out.println("------------欢迎来到点歌系统--------");
        System.out.println("0.添加歌曲至列表");
        System.out.println("1.将歌曲置顶");
        System.out.println("2.将歌曲前移一位");
        System.out.println("3.退出");
        LinkedList lineUpList = new LinkedList();//创建一个歌曲列表
        addMusicList(lineUpList);//添加一部分歌曲至歌曲列表
        while(true) {
            System.out.print("请输入要执行的操作序号：");
            Scanner scan = new Scanner(System.in);
            int command = scan.nextInt();//接收键盘输入的功能选项序号
            //执行序列号对应的功能
            switch (command) {
                case 0:
                    addMusic(lineUpList);
                    break;
                case 1:
                    setTop(lineUpList);
                    break;
                case 2:
                    setBefore(lineUpList);
                    break;
                case 3:
                    exit();
                    break;
                default:
                    System.out.println("--------------");
                    System.out.println("此功能选择有误，请输入正确的功能序号！")；
                    break;
            }
            System.out.println("当前歌曲列表：" + lineUplist);
        }
    }
    //初始时添加歌曲名称
	private static void addMusicList(LinkedList lineUpList) {
    lineUpList.add("稻香");
    lineUpList.add("夜曲");
    lineUpList.add("夜的第七章");
    lineUpList.add("听妈妈的话");
    lineUpList.add("龙卷风");
    System.out.println("初始歌曲列表:" + lineUpList);
	}
	//执行添加歌曲
	private static void addMusic(LinkedList lineUpList) {
    	System.out.print("请输入要添加的歌曲名称：");
        String musicName = new Scanner(System.in).nextLine();
        lineUpList.addLast(musicName);//添加歌曲到列表的最后
        System.out.println("已添加歌曲：" + musicName);
	}
    //执行将歌曲置顶
    private static void setTop(linkedList lineUpList) {
        System.out.print("请输入要置顶的歌曲名称：");
        String musicName = new Scanner(System.in).nextLine();
        int position = lineUpList.indexOf(musicName);//查找指定歌曲的位置
        if (position < 0) {	//判断输入歌曲是否存在
            System.out.println("当前列表中没有输入的歌曲！");
        } else if (position == 0) {//判断歌曲是否已在第一位
            System.out.println("当前歌曲已在最顶部！")；
        } else {
            lineUpList.remove(musicName);//移除指定的歌曲
            lineUpList.add(position - 1, musicName);//将指定歌曲放到前一位
        }
        System.out.println("已将歌曲" + musicName + "置前一位");
    }
    //退出
    private static void exit() {
        System.out.println("-------------------退出----------------");
        System.out.println("您已退出系统");
        System.exit(0);
    }
}
```

```java
//使用ArrayList集合模拟点歌系统
import java.util.LinkedList;
import java.util.Scanner;
public class KTVByArrayList {
    public static void main(String[] args) {
        System.out.println("------------欢迎来到点歌系统--------");
        System.out.println("0.添加歌曲至列表");
        System.out.println("1.将歌曲置顶");
        System.out.println("2.将歌曲前移一位");
        System.out.println("3.退出");
        ArrayList lineUpList = new ArrayList();//创建歌曲列表
    }
}
```





#### Set接口

+ Set接口 和 List接口一样，都继承与Collection接口
+ 与 Collection接口中的方法基本，并没有功能上的扩充，而是更加严格
+ 与 List接口不同的是，Set接口中元素**无序且都会以某种规则保证存入的元素不出现重复

----

+ Set 接口主要有两个实现类，分别是 `HashSet` 和 `TreeSet`
  + `HashSet` **根据对象的哈希值来确定元素在集合中的存储位置**
  + `TreeSet` **以二叉树的方式来存储元素，实现对集合中的元素进行排序**

---

##### HashSet集合

+ Set接口的实现类
+ 存储的元素不可重复，无序
+ 当向 HashSet集合中添加一个对象时
  + 首先调用该对象的 hashCode()方法来计算对象的哈希值，确定存储位置
  + 如果此时的哈希值相同，再调用对象的 equals()方法来确保该位置没有重复的元素

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        HashSet set = new HashSet();	//创建 HashSet集合
        set.add("Jack");
        set.add("Eve");
        set.add("Rose");
        set.add("Rose");
        Iterator it = set.iterator();//获取 Iterator对象
        while(it.hasNext()) {
            Object obj = it.next();
            System.out.println(obj);
        }
    }
}
```

![1552380895916](assets/1552380895916.png)

+ 当向集合中存入元素时，为了保证 HashSet正常工作，要求在存入对象时，重写 Object类中的 hashCode() 和 equals() 

```java
import java.util.*;
class student {
    String id;
    String name;
    public Student(String id, String name) {
        this.id = id;
        this.name = name;
    }
    public String toString() {
        return id + ":" + name;
    }
}
public class Example {
    public static void main(String[] args) {
        HashSet hs = new HashSet();	//创建 HashSet集合
        Student stu1 = new Student("1","Jack");
        Student stu2 = new Student("2","Rose");
        Student stu3 = new Student("3","Rose");
        hs.add(stu1);
        hs.add(stu2);
        hs.add(stu3);
        System.out.println(hs);
    }
}
//没有重写 hashCode() 和 equals()方法，产生一个重复元素
```

```java
//重写两个方法，不产生重复元素
import java.util.*;
class student {
    private String id;
    private String name;
    public Student(String id, String name) {
        this.id = id;
        this.name = name;
    }
    //重写 toString()方法
    public String toString() {
        return id + ":" + name;
    }
    //重写 hashCode方法
    public int hashCode() {
        return id.hashCode();	//返回id属性的哈希值
    }
    //重写equals方法
    public boolean equals(Object obj) {
        if (this == obj) {	//判断是否是同一个对象
            return true;	//如果是，直接返回 true
        }
        if (!(obj instanceof Student)) {//判断对象是否为 Student类型
            return false;	//如果对象不是 Student类型,返回 false
        }
        Student stu = (Student) obj;	//将对象强转为 Student类型
        boolean b = this.id.equals(stu.id);//判断 id值是否相同
        return b;	//返回判断结果
    }
}
public class Example {
    public static void main(String[] args) {
        HashSet hs = new HashSet();
        Student stu1 = new Student("1","Jack");
        Student stu2 = new Student("2","Rose");
        Student stu3 = new Student("3","Rose");
        hs.add(stu1);
        hs.add(stu2);
        hs.add(stu3);
        System.out.println(hs);
    }
}
```





#### 案例10 模拟新浪微博用户注册

![1552458620002](assets/1552458620002.png)

1. 创建用户类，并重写其 HashCode() 和 equals()方法

```java
package cn.xinlang;
import java.util.Date;
//用户信息
public class User {
    private String userName;
    private String password;
    private Date birthday;
    private String telNumber;
    private String email;
    public User {} 
    public User(String userName, String password, Date birthday, String telNumber, String email) {
        this.userName = userName;
        this.password = password;
        this.birthday = birthday;
        this.telNumber = telNumber;
        this.email = email;
    }
    //重写 hashCode 与 equals方法
    @Override
    public int hashCode() {
        //重写 hashCode方法，以用户名作为是否重复的依据
        return userName.hashCode();
    }
    @Override
    public boolean equals(Object obj) {
        if (this == obj) {
            return true;
        }
        if (obj == null) {
            return false;
        }
        if (getClass() != obj.getClass()) {//判断这个对象是否是 User类型
            return false;
        }
        User other = (User) obj;//将对象强转为 User类型
        if (UserName == null) {//判断集合中用户名是否为空
            if(other.userName != null) {//判断对象中的用户名是否为空
                return false;//集合中用户名为空且对象中用户名不为空，则返回false
            }
        } else if (!userName.equals(Other.userName)) {//判断用户名是否为空
            return false;//如果不同，返回 false
        }
        return true;
    }
}
```

2. 创建用户注册类，模拟注册

```java
package cn.xinlang;
import java.util.Date;
import java.util.HashSet;
import java.util.Scanner;
public class UserRegister {
    public static HashSet<User> USER_DATA = new HashSet<User>();//用户数据
    public static void main(String[] args) {
        initData();//初始化人员信息
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入用户名：");
        String userName = sc.nextLine();
        System.out.print("请输入密码：");
        String password = sc.nextLine();
        System.out.print("请重复密码：");
        String repassword = sc.nextLine();
        System.out.print("出生日期：");
        String birthday = sc.nextLine();
        System.out.print("手机号码：");
        String telNumber = sc.nextLine();
        System.out.print("电子邮箱：");
        String email = sc.nextLine();
        //校验用户信息，返回登录状态信息
        CheckInfo checkInfo = new CheckInfo(USER_DATA);
        String result = checkInfo.checkAction(userName, password, repassword, birthday, telNumber, email);
        System.out.println("注册结果：" + result);
    }
    //初始化数据，创建两个已存在的用户信息
    private static void initData() {
        User user = new User{"张正","zz,123", new Date(), "1319031930", "zhangzheng@163.com"};
        User user = new User{"小吴","xw,345", new Date(), "1319031930", "zhangzheng@163.com"};
        USER_DATA.add(user);
        USER_DATA.add(user2);
    }
}
```

3. 创建校验信息类

```java
package cn.xinglang;
import java.util.*;
import java.text.*;
public class CheckInfo {
    public static HashSet<User> USER_DATA = new HashSet<User>();//用户数据
    public CheckInfo(HashSet<User> USER_DATA) {
        this.USER_DATA = USER_DATA;
    }
    //校验用户信息，返回登录状态
    public String checkAction(String userName, String password, String rePassword, String birthday, String phone, String email) {
        StringBuilder result = new StringBuilder();
        //1.代表成功  2.代表失败
        int state = 1;
        //密码判断
        if(!password.equals(rePassword)) {//判断密码和重复密码是否相同
            result.append("两次输入的密码不一致!\r\n");
            state = 2;
        }
        //生日判断
        if (birthday.length() != 10) {
            result.append("生日格式不正确！\r\n");
            state = 2;
        } else {
            for(int i = 0; i < birthday.length(); i++) {
                Character thisChar = birthday.charAt(i);
                if (i == 4 || i == 7) {
                    if (!(thisChar == '-')) {//验证第四位和第七位是否是符号"-"
                        result.append("生日格式不正确！\r\n");
                        state = 2;
                    }
                } else {//判断除了第四位和第七位的字符是否是 0~9的数字
                    if(!(Character.isDigit(thisChar))) {
                        result.append("生日格式不正确！\r\n");
                        state = 2;
                    }
                }
            }
        }
        //手机号判断
        if(phone.length() != 11) {//判断手机号是否无效
        	result.append("手机号码不正确！\r\n");
            state = 2;
            //默认有效手机号为13、15、17、18开头的手机号
        } else if (!(phone.startsWith("13") || phone.startsWith("15") || phone.startsWith("17") || phone.startsWith("18"))) {
            result.append("手机号码不正确！\r\n");
            state = 2;
        }
        //邮箱判断
        if (!email.contains("@")) {
            result.append("邮箱不正确！\r\n");
            state = 2;
        }
        //如果以上信息校验无误，则将新用户加入到集合
        if (satte == 1) {
            //格式化日期返回 Date对象
            DateFormat format = new SimpleDateFormat("yyyy-MM-dd");
            Date dateBirthday = null;
            try {
                dateBirthday = format.parse(birthday);
            } catch (ParseException e) {
                e.printStackTrace();
            }
            User newUser = new User(userName, rePassword, dateBirthday, phone, email);
            //将用户添加到列表里，同时根据 HashSet 判断出用户名有没有重复
            if (!USER_DATA.add(newUser)) {
                result.append("用户重复！");
                state = 2;
            }
            if (state == 1) {
                result.append("注册成功！");
            }
        }
        return result.toString();
    }
}
/*校验信息通过后，将信息创建成 User对象，再判断用户名的哈希值是否相等，相等则添加失败，反之则成功*/
```





#### Map接口

+ 现实生活中，通过身份证号可以查询个人信息，这是一种**一对一的关系**。在程序中要存储这种具有对应数据关系的数据，需要使用**JDK中提供的 Map接口**
+ Map接口是一种**双列集合**，每个元素都包含 **键对象 Key和 值对象 Value**，这种对应功能称为映射
+ 指定了 Key就能找到对应的 Value

![1553064570715](assets/1553064570715.png)



##### HashMap集合

+ 是 Map接口的一个实现类，用于存储键值映射关系，但必须保证不出现重复的键
+ 如果存储了相同的键，后存储的会覆盖原有的值

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        Map map = new HashMap();//创建 Map对象
        map.put("1", "Rose");
        map.put("2", "Jack");
        map.put("3", "Lucy");
        System.out.println("1:" + map.get("1"));//根据键获取值
        System.out.println("2:" + map.get("2"));
        System.out.println("3:" + map.get("3"));
    }
}
```

+ 演示获取所有的键和值

```java
//先遍历Map集合中所有的键，再根据键获取值
import java.util*;
public class Example {
    public static void main(String[] args) {
        Map map = new HashMap();
        map.put("1", "Rose");
        map.put("2", "Jack");
        map.put("3", "Lucy");
        Set keySet = map.keySet();	//获取键的集合
        Iterator it = keySet.iterator();//迭代键的集合
        while(it.hasNext()) {
            Object key = it.next();
            Object value = map.get(key);//根据每个键所对应的值
            System.out.println(key + ":" + value);
        }
    }
}
```

```java
//先获取集合中的所有的映射关系，从映射关系中取出键和值
import java.util.*;
public class Example {
    public static void main(String[] args) {
        Map map = new HashMap();
        map.put("1", "Rose");
        map.put("2", "Jack");
        map.put("3", "Lucy");
        Set entrySet = map.entrySet();
        Iterator it = entrySet.iterator();
        while(it.hasNext()) {
            Map.Entry entry = (Map.Entry)(it.next());
			Object key = entry.getKey();
            Object value = entry.getValue();
            System.out.println(key + ":" + value);
        }
    }
}
```

![1553066136139](assets/1553066136139.png)



+ 获取Map 中存储所有值得 Collection集合

```java
import java.util.*;
public class Example {
    Map map = new HashMap();
    map.put("1", "Rose");
    map.put("2", "Jack");
    map.put("3", "Lucy");
    Collection values = map.values();
    Iterator it = values.iterator();
    while (it.hasNext()) {
        Object value = it.next();
        System.out.println(value);
    }
}
```

+ HasMap 迭代取出的元素顺序和存入的顺序是不一致的，如果想要一致，需要使用 **HashMap 的子类 LinkedHashMap类**
+ 这个类像 LinkedList一样，**使用双向链表来维护内部元素的关系，使用Map 元素迭代的顺序与存入的顺序一致**

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        Map map = new LinkedHashMap();
        map.put("1", "Rose");
    	map.put("2", "Jack");
    	map.put("3", "Lucy");
        Set keySet = map.keySet();
        Iterator it = keySet.iterator();
        while (it.hasNext()) {
            Object key = it.next();
            Object value = map.get(key);
            System.out.println(key + ":" + value);
        }
    }
}
//	元素迭代出来的顺序与存入的顺序一致
```



##### Properties集合

![1553068067468](assets/1553068067468.png)

```java
	Backgroup-color = red;
	Font-size = 14px;
	Language = chinese
```

+ 在实际开发中可以使用 Properties 集合对这些配置项进行存取

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        Properties p = new Properties();
        p.setProperties("Backgroup-color","red");
        p.setProperties("Font-size","14px");
        p.setProperties("Language","chinese");
        Enumeration names = p.propertyNames();
        while(name.hasMoreElements()) {
            String key = (String) names.nextElement();
            String value = p.getProperty(key);
            System.out.println(key + "=" + value);
        }
    }
}
```

![1553068669082](assets/1553068669082.png)



#### 案例11 斗地主小游戏之洗牌发牌

![1553068811417](assets/1553068811417.png)

![1553068823464](assets/1553068823464.png)

![1553071856279](assets/1553071856279.png)

```java
import java.util.Collections;
import java.util.HashMap;
public class PokerShuffleCards {
    public static void main(String[] args) {
        //准备花色
        ArrayList<String> color = new ArrayList<String>();
        color.add("♠");
        color.add("♥");
        color.add("♦");
        color.add("♣");
        //准备数字，用 ArrayList将纸牌由小到大排序
        ArrayList<String> number = new ArrayList<String>();
        for (int i = 3; i <= 10; i++) {
            number.add(i + "");
        }
        number.add("J");
        number.add("Q");
        number.add("K");
        number.add("A");
        number.add("2");
        //定义一个 map集合，用来将数字与每一张牌进行对应
        HashMap<Integer,String> map = new HashMap<Integer, String>();
        int index = 0;//纸牌编号
        for(String thisNumber : number) {//循环纸牌数字
            for(String thisColor : color) {//循环纸牌花色
                //将花色与数字组合，形成52张纸牌，并赋予其编号
                map.put(index++,thisColor + thisNumber);
            }
        }
        //加入大小王
        map.put(index++, "小☽");
        map.put(index++, "大☀");
        //创建内容为 0~53的数字集合，代表着 54张牌
        ArrayList<Integer> cards = new ArrayList<Integer>();
        for (int i = 0; i <= 53; i++) {
            cards.add(i);//此时的 cards顺序为 0~53
        }
        //洗牌，使用 Collection工具类中的 shuffle（）方法
        Collections.shuffle(cards);//此时的 cards顺序已被打乱
        // 创建三个玩家和底牌
        ArrayList<Integer> iPlayer = new ArrayList<Integer>();
        ArrayList<Integer> iPlayer2 = new ArrayList<Integer>();
        ArrayList<Integer> iPlayer3 = new ArrayList<Integer>();
        ArrayList<Integer> iSecretCards = new ArrayList<Integer>();
        //遍历这幅洗好的牌，遍历过程中，将牌发到 3个玩家手中和底牌中
        for (int i = 0; i < cards.size(); i++) {
            if (i >= 51) {
                iSecretCards.add(cards.get(i));//留取三张底牌
            } else {
                if (i % 3 == 0) {
                    iPlayer.add(cards.get(i));//三张牌一发
                } else if (i % == 1) {
                    iPlayer2.add(cards.get(i));
                } else {
                    iPlayer3.add(cards.get(i));
                }
            }
        }
        //对每个人手中的牌进行排序，使用 Collection 工具类中的 sort()方法
        Collection.sort(iPlayer);
        Collection.sort(iPlayer2);
        Collection.sort(iPlayer3);
        //对应数字形式的每个人手中的牌，定义字符串形式的牌
 		ArrayList<String> sPlayer = new ArrayList<String>();
        ArrayList<String> sPlayer2 = new ArrayList<String>();
        ArrayList<String> sPlayer3 = new ArrayList<String>();
        ArrayList<String> sSecretCards = new ArrayList<String>();
        //循环主键，从 map中获取纸牌
        for (Integer key : iPlayer) {
            sPlayer.add(map.get(key));
        }
        for (Integer key : iPlayer2) {
            sPlayer2.add(map.get(key))
        }
        for (Integer key : iPlayer3) {
            sPlayer3.add(map.get(key))
        }
        for (Integer key : iSecretCards) {
            sSecretCards.add(map.get(key))
        }
        //看牌
        System.out.println("玩家1：" + sPlayer);
        System.out.println("玩家2：" + sPlayer2);
        System.out.println("玩家3：" + sPlayer3);
        System.out.println("底牌：" + sSecretCards);
    }
}
```









#### JDK5.0新特性---泛型

+ 集合可以存储任何类型的对象，但是当一个对象存入集合后，集合会忘记这个对象的类型，**将这个对象取出时，这个对象的编译就变成了 Object类型**
+ 程序中无法确定一个集合中的元素到底是什么类型，这样在取出时，如果进行**强制类型转换就很容易出错**

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        ArrayList list = new ArrayList();//创建 ArrayList集合
        list.add("String");
        list.add("Collection");
        list.add(1);
        for (Object obj : list) {
            String str = (String) obj;	//强制转换为 Stringl类型
        }
    }
}
//由于 integer对象无法转换为 String类型，因此报错
```

+ 为了解决强制转换报错的问题，**在 JAVA中引入了 “参数化类型“，即泛型**
+ 泛型可以**限定方法操作的数据类型，在定义集合类时，使用<参数化类型>的方式**指定该类中方法操作的数据类型

```java
ArrayList<参数化类型> list = new ArrayList<参数化类型>();
```

```java
import java.util.*;
public class Example {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();//创建 ArrayList集合
        list.add("String");
        list.add("Collection");
    //    list.add(1);  限定了只能是 String类型
        for (String obj : list) {//遍历元素时，可以指定元素类型为 String了
            System.out.println(str);	//强制转换为 Stringl类型
        }
    }
}
```







### IO(输入输出)

---

+ 在 Java中，**将通过不同输入输出设备（键盘、内存、显示器、网络等）之间的数据传输抽象表述为“流”**，程序允许通过流的方式与输入输出设备进行数据传输
+ IO流的划分
  + 操作数据的不同：**字节流、字符流**
  + 数据传输方向的不同：**输入流、输出流**
+ 程序从输入流中读取数据，向输出流中写入数据

![1553309864494](assets/1553309864494.png)



#### 字节流的概念

+ 计算机中，无论是文本、图片、音频和视频，所有文件都是以二进制（字节）形式存在的
+ 所有的字节输入流都继承自 `InputStream`,所有的字节输出流都继承自 `OutputStream`

![1553310195092](assets/1553310195092.png)

+ 字节输入流的常见方法

![1553311187686](assets/1553311187686.png)

+ 字节输出流的常见方法

![1553311269619](assets/1553311269619.png)

+ `InputStream` 和 `OutputStream` 虽然提供了一系列的读写数据的方法，但**这两个类是抽象类，不能被实例化**，所以要使用子类进行重写

![1553311990881](assets/1553311990881.png)



##### 字节流的读写

+ `FileInputStream` 操作文件的字节输入流，专门用于读取文件中的数据，**由于从文件读取数据是重复的操作，因此需要通过循环来实现数据的持续读取**

```java
import java.io.*;
public class Example {
    public static void main(String[] args) {
        //创建一个文件字节输入流
        FileInputStream in = new FileInputStream("test.txt");
        int b = 0;	//定义一个int类型的变量，记住每次读取的一个字节
        while(true) {
            b = in.read();	//变量b记住读取的一个字节
            if (b == -1) {//如果读取的字节为 -1，跳出while循环
                break;
            }
            System.out.println(b);
			//输出的是字节所对应的十进制数字
        }
        in.close();
    }
}

```

> + 在读取文件数据时，必须保证文件**在相应的目录存在并且是可读的**，否则会抛出文件找不到的异常

```java
//数据写入文件
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        //创建一个文件字节输入流
        FileOutputStream out = new FileOutputStream("example.txt");
        String str = "周周";
        byte[] b = str.getBytes();
        for(int i == 0; i < b.length; i++) {
            out.write(b[i]);
        }
        out.close();
    }
}
```

+ ==提示==：使用 `FileOutputSteam` 向一个已存在的文件中写入数据时，那**数据可能被清空**，可以使用其构造函数 `FileOutputStream(String fileName, boolean append) `来避免这种情况

```java
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        OutputStream out = new FileOutputStream("example.txt", true);
        String str = "想你";
        byte[] b = str.getBytes();
        for (int i = 0; i < b.length; i++) {
            out.write(b[i]);
        }
        out.close();
    }
}
```

+ ==注意==：由于在 IO流进行数据读写操作时会出现异常，为了保证 IO流的 close()方法必须执行，通常将关闭流的操作写在 finally 代码块中

```java
finally {
    try {
        if (in != null)	//如果in不为空，关闭输入流
            in.close();
    } catch (Exception e) {
        e.printStackTrace();
    }
    try {
        if (out !=null)	//如果 out不为空，关闭输出流
            out.close();
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```





##### 文件的拷贝

+ IO流通常是成对存在的，即输入流和输出流一起使用

```java
//不同文件夹下的文件拷贝
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        //创建一个字节输入流，用于读取当前目录下 source文件夹中的 mp3文件
        InputStream in = new FileInputStream("source\\2.mp3");
        //创建一个文件字节输出流，用于将读取的数据写入 target目录下的文件中
        OutputStream out = new FileOutputStream("target\\2.mp3");
        int len;//定义一个 int类型的变量 len，记住每次读取的一个字节
        long begintime = System.currentTimeMillis();//获取拷贝文件前的系统时间
        while((len = in.read()) != -1) {
            //读取一个字节并判断是否读取到文件末尾
            out.write(len);	//将读到的字节写入文件
        }
        long endtime = System.currentTimeMills();//获取文件拷贝结束时的时间
        System.out.println("拷贝文件所消耗的时间是：" + (endtime - begintime) + "毫秒");
        in.close();
        out.close();
    }
}
```

+ ==注意==:转义字符的运用

![1553327428478](assets/1553327428478.png)





##### 字节流的缓冲区

+ 运用临时缓冲区，通过流的方式拷贝文件时，**为了提高效率也可以定义一个字节数组作为缓冲区**

```java
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        //创建一个字节流输入流，用于读取当前目录下 source文件夹下的文件
        InputStream in = new FileInputStream("source\\2.mp3");
        //创建一个文件字节输出流，用于将读取的数据写入当前目录的 target文件中
        OutputStream out = new FileOutputStream("target\\2.mp3");
        //以下是用缓冲区读写文件
        byte[] buff = new byte[1024];//定义一个字节数组，作为缓冲区
        //定义一个 int类型的变量 len记住读取读入缓冲区的字节数
        int len;
        long begintime = System.currentTimeMills();
        while((len = in.read(buff)) != -1) {
            out.write(buff, 0, len);//	从第一个字节开始，向文件写入 len个字节
        }
        long endtime = System.currentTimeMills();
   		System.out.println("拷贝文件所消耗的时间是：" + (endtime - begintime) + "毫秒");
        in.close();
        in.close();
    }
}
//使用缓冲区拷贝文件所消耗的时间明显减少了，这说明使用缓冲区读写文件可以有效地提高程序的效率，原因在于使用缓冲区减少了对文件的操作次数，提高了读写数据的效率
```





##### 字节缓冲流

+ 在 IO包中提高了两个带缓冲的字节流，分别是 `BufferedInputStream` 和 `BufferedOutputStream`，他们的构造方法分别接收 InputStream 和 OutputStream 类型的参数作为对象

![1553329055401](assets/1553329055401.png)

```java
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
    	//创建一个带缓冲区的输入流
    	BufferedInputStream bis = new BufferedInputStream(new 		FileInputStream("src.txt"));
    	//创建一个带缓冲区的输出流
    	BufferedOutputStream bos = new BufferedOutputStream(new FileInputStream("des.txt"));
    	int len;
        while((len = bis.read()) != -1) {
            bos.write(len);
        }
        bis.close();
        bos.close();
	}
}
```





#### 案例12 保存书店每日交易记录程序设计

![1553329816454](assets/1553329816454.png)

```java
package cn.test.chapter.task;
public class Books {
    int id;
    String name;//图书名称
    double price;//图书单价
    int number;//图书数量
    double money;//总价
    String Publish;//出版社
    public Books(int id, String name, double price, int number, double money, String Publish) {
        this.id = id;
        this.name = name;
        this.price = price;
        this.number = number;
        this.money = money;
        this.Publish = Publish;
    }
    @Override
    public String toString() {
        String message = "图书编号:" + id + " 图书名称：" + name + " 出版社:" + Publish + " 单价：" +　price + " 库存数量：" + number;
        return message;
    }
    public void setNumber(int number) {
        this.number = number;
    }
}
```

+ 定义 RecordBooksOrder 类来记录和操作图书信息

```java
package cn.test.chapter.task;
import java.util.ArrayList;
import java.util.Scanner;
public class RecordBooksOrder {
    static ArrayList<Books> booksList = new ArrayList<Books>();//创建书架
    publish static void main(String[] args) {
        init();//初始化书架
        //将书架上所有图书信息打印出来
        for(int i = 0; i < booksList.size(); i++) {
            System.out.println(booksList.get(i));
        }
        while(true) {
            //获取控制台输入的信息
            Scanner sc = new Scanner(System.in);
            System.out.print("请输出图书编号：");
            int bookId = sc.nextInt();
            Books stockBooks = getBooksById(bookId);
            if (stockBooks != null) {//判断是否存在此图书
                System.out.println("当前图书信息:" + stockBooks);
                System.out.println("请输入购买数量：");
                int bookNumber = scan.nextInt();
                if (bookNumber <= stockBooks.number) {//判断库存是否足够
                	//将输入信息封装成 Books对象
                    Books boos = new Books(stockBooks.id, stockBooks.name, stockBooks.price, bookNumber, stockBooks.price*bookNumber, stockBooks.Publish);
                    FileUtil.saveBooks(books);//将本条数据保存至本地文件
                    //修改库存
                    stockBooks.setNumber(stockBooks.number - bookNumber);
                } else {
                    System.out.println("库存不足!");
                }
            } else {
                System.out.println("图书编号输入错误!");
            }
        }
    }
    /**
    *初始化书架上图书的信息，将图书放在书架上
    */
    private static void init() {
        Books goods1 = new Books(101, "Java基础入门", 44.50, 100, 4450.00, "清华大学出版社");
        Books goods2 = new Books(102, "Java编程思想", 108.00, 50, 5200.00, "机械工业出版社");
        Books goods3 = new Books(103, "疯狂Java讲义", 99.00, 100, 990.00, "电子工业出版社");
        booksList.add(goods1);
        booksList.add(goods2);
        booksList.add(goods3);
    }
    /**
     *根据输入的图书编号查找图书信息 循环遍历书架中图书信息，找到图书编号相等的取出
     */
    private static Books getBooksById(int bookId) {
        for (int i = 0; i < booksList.size(); i++) {
            Books thisBooks = booksList.get(i);
            if (bookId == thisBooks.id) {
                return thisBooks;
            }
        }
        return null;
    }
}
```

+ 定义工具类 FileUtil 保存图书信息

```java
package cn.test.chapter
import java.io.BufferedOutputStream;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
public class FileUtil {
    public static final String SEPARATE_FIELD = ",";//字段分隔 英文逗号
    public static final String SEPARATE_LINE = "\r\n";//行分隔
    /**
     *保存图书信息
     */
    public static void saveBooks(Books books) {
        //判断本地是否存在此文件
        Date date = new Date();
        DateFormat format = new SimpleDateFormat("yyyyMMdd");//定义日期格式
        String name = "销售记录" + format.format(date) + ".csv";//拼接文件名
        InputStream in = null;
        try {
            in = new FileInputStream(name);//判断本地是否存在此文件
            if (in != null) {
                in.close();//关闭输入流
                createFile(name, true, books);//存在文件，采取修改文件方式
            }
        } catch (FileNotFoundException e) {
            createFile(name, false, books);//不存在文件，采取新建新文件方式
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    /**
     *将图书的售出信息保存到本地，可通过 label标识来判断是修改文件还是新建文件
     *
     *@param name 文件名
     *@param label 文件已存在的标识 true: 已存在则修改 false; 不存在则新建
     *@param books 图书信息
     */
    public static void createFile(String name, boolean label, Books books) {
        BufferedOutputStream out = null;
        StringBuffer sbf = new StringBuffer();//拼接内容
        try {
            if (label) {//当已存在当天的文件，则在文件内容后追加
            	//创建输出流,用于追加文件
                out = new BufferedOutputStream(new FileOutputStream(name, true));
            } else {//不存在当天文件，则新建文件
                //创建输出流，用于保存文件
                out = new BufferedOutputStream(new FileOutputStream(name));
                String[] fieldSort = new String[] {
                    "图书编号","图书名称","购买数量","单价","总价","出版社"
                };
                //创建表头
                for (String fieldKye : fieldSort) {
                    //新建时，将表头存入本地文件
                    sbf.append(fieldKye).append(SEPARATE_FIELD);
                }
            }
            sbf.append(SEPARATE_LINE);//追加换行符号
            sbf.append(books.id).append(SEPARATE_FIELD);
            sbf.append(books.name).append(SEPARATE_FIELD);
            sbf.append(books.number).append(SEPARATE_FIELD);
            sbf.append((double) books.price).append(SEPARATE_FIELD);
            sbf.append((double) books.money).append(SEPARATE_FIELD);
            sbf.append(books.Publish).append(SEPARATE_FIELD);
            String str = sbf.toString();
            byte[] b = str.getBytes();
            for (int i = 0; i < b.length; i++) {
                out.write(b[i]);//将内容写入本地文件
            }
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            try {
                if (out != null) {
                    out.close();//关闭输出流
                }
            } catch (Exception e2) {
                e2.printStackTrace();
            } 
        }
    }
}
```









#### 字符流

---

##### 字符流定义及基本用法

+ 操作字符可以使用字符流
+ 字符流的两个顶级父类 `Reader` 和 `Write`

![1553670310711](assets/1553670310711.png)



##### 字符流操作文件

+ 在程序开发中，经常需要对文本文件的内容进行读取，如果想从文件中直接读取字符，**可以使用字符输入流 FileReader**
+ 字符输入流的 read()方法返回的是 int 类型的值，**想获取字符就要强制转换**

```java
//在当前项目目录下新建文本文件 “reader.txt",输入一些字符
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        //创建一个 FileReader 对象用来读取文件中的字符
        FileReader reader = new FileReader("reader.txt");
        int ch;//定义一个变量用于记录读取的字符
        while ((ch == reader.read()) != -1) {//循环判断是否读取到文件的末尾
        	System.out.println((char) ch);//不是字符流末尾就转为字符打印
        }
        reader.close();//关闭文件读取流，释放资源
    }
}
```

+ File Write 可以写入字符，**如果文件不存在，就先创建文件，如果文件存在，则会清空文件内容再写入**
+ 追加要调用重载的构造方法 `FileWrite write = new FileWrite("write.txt", true)`

```java
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        //创建一个 FileWriter对象用于向文件中写入数据
        FileWriter write = new FileWrite("write.txt");
        String str = "你好";
        writer.write(str);//将字符数据写入到文本文件中
        writer.write("\r\n")；//换行
        writer.close();//关闭写入流，释放资源
    }
}
```

+ **包装流可以有效地提高读写数据的效率**
+ 字符流提供带缓冲区的包装流，`BufferedReader` 和 `BufferedWrite`

```java
//演示 readLine()方法，一次读取一行文本
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        FileReader reader = new FileReader("src.txt");
        //创建一个 BufferedReader缓冲对象
        BufferedReader br = new BufferedReader(reader);
        FileWriter writer = new FileWriter("des.txt");
        //创建一个 BufferedWriter缓冲对象
        BufferWriter bw = new BufferWriter(Writer);
        String str;
        while ((str = br.readLine()) != null) {
            bw.write(str);
            bw.newLine();
        }
        br.close();
        bw.close();
    }
}
```

> 字符缓冲流内部使用了缓冲区，**只有在缓冲区写满时或调用 close()方法时**，缓冲区的字符才会被写入目标文件





##### 转换流

+ 实现字节流和字符流之间的相互转换
+ 只能针对操作文本文件的字节流进行转换，**如果字节流操作的是一张图片，此时转换为字符流就会造成数据丢失**

![1553673003063](assets/1553673003063.png)

```java
import java.io.*;
public class Example {
    public static void main(String[] args) throws Exception {
        FileInputStream in = new FileInputStream("src.txt");//创建字节输入流
        //将字节流输入转换成字符输入流
        InputStreamReader isr = new InputStreamReader(in);
        BufferedReader br = new BufferedReader(isr);//赋予字符输入流对象缓冲区
        FileOutputStream out = new FileOutoutStream("des.txt");
        //将字节输出流转换成字符输出流
        OutputStreamWriter osw = new OutputStreamWriter(out);
        BufferedWriter bw = new BufferedWriter(osw);//赋予字符输出流对象缓冲区
        String line;
        while ((line = br.readLine()) != null) {//判断是否读取到文件末尾
        	bw.write(line);//输出读取到的文件
        }
        br.close();
        bw.close();
    }
}
```





#### 案例13 模拟记事本

![1553674996067](assets/1553674996067.png)

+ 创建记事本类，在类中编写执行程序的 main方法

```java
package cn.note;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;
public class Notepad {
    private static String filePath;
    private static String message = "";
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(System.in);
        System.out.println("--1：新建文件	2:打开文件	3:修改文件	4:保存	5:退出--");
        while(true) {
            System.out.print("请输入操作指令：");
            int cmd = sc.nextInt();
            switch (cmd) {
                case 1:
                    createFile();
                    break;
                case 2:
                    openFile();
                    break;
                case 3:
                    editFile();
                    break;
                case 4:
                    saveFile();
                    break;
                case 5:
                    exit();
                    break;
                default:
                    System.out.println("您输入的指令错误！");
                    break;
            }
        }
    }
}
```

+ 在 Notepad 中编写新建文件方法

```java
//新建文件，从控制台获取内容
private static void createFile() {
    message = "";//新建文件时，暂存文件的内容为空
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入内容，停止编写请输入\"stop\":");
    StringBuffer stb = new StringBuffer();//用于后期输入内容的拼接
    String inputMessage = "";
    while (!inputMessage.equal("stop")) {
        if (stb.length() > 0) {
            stb.append("\r\n");//追加换行符
        }
        stb.append(inputMessage);//拼接输入信息
        inputMessage = sc.nextLine();
    }
    message = stb.toString();//将输入内容暂存
}
```

+ 在 Notepad 中编写打开文件方法

```java
private static void openFile() throws Exception {
    message = "";//打开文件时，将暂存内容清空
    Scanner sc = new Scanner(System.in);
    System.out.print("请输入打开文件的位置:");
    filePath = sc.next();//获取打开文件的路径
    //控制只能输入 txt 格式的文件路径
    if (filePath != null && !filePath.endWith(".txt")) {
        System.out.print("请选择文本文件！");
        return;
    }
    FileReader in = new FileReader(filePath);//实例化一个 FileReader对象
    char[] charArray = new char[1024];//缓冲数组
    int len = 0;
    StringBuffer sb = new StringBuffer();
    //循环读取，一次读取一个字符数组
    while ((len = in.read(charArray)) != -1) {
        sb.append(charArray);
    }
    message = sb.toString();//将打开文件内容暂存
    System.out.println("打开文件内容：" + "\r\n" + message);
    in.close();
}
```

+ 在 Notepad中编写修改文件方法

```java
//修改文件内容 通过字符串替换的形式
private static void editFile() {
    if(message == "" && filePath == null) {
        System.out.println("请先新建文件或者打开文件");
        return;
    }
        Scanner sc =new Scanner(System.in);
        System.out.println("请输入要修改的内容（以\"修改的目标文字：修改之后的文字\"格式），" + "停止修改请输入\"stop\":");
        String inputMessage = "";
        while (!inputMessage.equal("stop")) {
            //当输入stop时停止修改
            inputMessage = sc.nextLine();
            if (inputMessage != null && inputMessage.length() > 0) {
                //将输入的文字根据： 拆成数组
                String[] editMessage = inputMessage.split(":");
                if (editMessage != null && editMessage.length > 1) {
                    //根据输入的信息将文件中的内容替换
                    message = message.replace(editMessage[0],editMessage[1]);
                }
            }
        }
        System.out.println("修改后的内容：" + "\r\n" + message);
    }
```

+ 编写保存文件的方法

```java
//新建文件存在用户输入的路径 打开的文件将覆盖源文件
private static void saveFile() throws IOException {
    Scanner sc = new Scanner(System.in);
    FileWriter out = null;
    if (filePath != null) {
        //文件是由“打开”载入的
        out = new FileWriter(filePath);//将原文件覆盖
    } else {
        System.out.print("请输入文件保存的绝对路径：");
        String path = sc.next();//获取文件保存路径
        filePath = path;
        //将输入路径中大写字母替换成小写字母后判断是不是文本格式
        if (!filePath.toLowerCase().endsWith(".txt")) {
            filePath += ".txt";
        }
        out = new FileWriter(filePath);//构造输出流
    }
    out.write(message);//写入暂存的内容
    out.close();
    message = "";//修改文件前将写入内容清空
    filePath = null;//将文件路径置null
}
```

+ 编写退出程序的方法

```java
//退出功能
private static void exit() {
    System.out.println("您已退出系统，谢谢使用！");
    System.exit(0);
}
```







#### File类

---

+ IO可以对文件的内容进行读写，**但是在使用程序时，我们还需要对文件本身进行操作（创建一个文件、删除或者重命名文件，判断某个文件是否存在、查询文件的最后修改时间）**
+ File类封装了一个路径，并提供了一系列的方法用于操作该路径所指向的文件



##### File 类的常用方法

+ 封装的路径：
  + 系统盘的绝对路径
  + 相对于当前目录而言的相对路径

![1553743814443](assets/1553743814443.png)

+ 常用的使用方法

![1553743970928](assets/1553743970928.png)

![1553743991311](assets/1553743991311.png)

```java
//准备工作：当前目录下创建一个文件“example.txt”，并输入"www.baidu.com"
import java.io.File;
import java.io.IOException;
public class Example {
    public static void main(String[] args) {
        //创建File文件对象，表示一个文件
        File file = new File("example.txt");
        //获取文件名
        System.out.println("文件名称:" + file.getName());
        //获取文件的相对路径
        System.out.println("文件的相对路径：" + file.getPath());
        //获取文件的绝对路径
        System.out.println("文件的绝对路径：" + file.getAbsolutePath());
        //获取文件的父路径
        System.out.println("文件的父路径：" + file.getParent());
        //判断文件是否可读
        System.out.println(file.canRead() ? "文件可读" : "文件不可读");
        //判断文件是否可写
        System.out.println(file.canWrite() ? "文件可写" : "文件不可写");
        //判断是否是一个文件
        System.out.println(file.isFile() ? "是一个文件" : "不是一个文件");
        //判断是否是一个目录
        System.out.println(file.isDirectory() ? "是一个目录" : "不是一个目录");
        //判断是否是一个绝对路径
        System.out.println(file.isAbsolute() ? "是绝对路径" : "不是绝对路径");
        //得到文件最后修改时间
        System.out.println("最后修改时间是：" + file.lastModified());
        //得到文件的大小
        System.out.println("文件大小为：" + file.length() + " bytes");
        //是否成功删除文件
        System.out.println("是否成功删除文件" + file.delete());
    }
}
```





##### 遍历目录下的文件

+ list() 方法**用于遍历某个指定目录下的所有文件的名称**

```java
import java.io.File;
public class Example {
    public static void main(String[] args) {
        //创建 File对象
        File file = new File("D:\\Java");
        if (file.isDirectory()) {
            //获取该目录下的所有文件的文件名
            String[] names = file.list();
            for (String name : names) {
                System.out.println(name);//输出文件名
            }
        }
    }
}
```

+ 特定文件的过滤

![1553753915382](assets/1553753915382.png)

```java
import java.io.File;
import java.io.FilenameFileter;
public class Example {
    public static void main(String[] args) throws Exception {
        //创建 File对象
   		File file = new File("D:\\Java")；
        //创建过滤器对象
        FilenameFileter fileter = new FilenameFileter() {
            //实现 accept()方法
            public boolean accept(File dir, String name) {
                File currFile = new File(dir, name);
                //如果文件名以 .txt结尾 返回 true，否则返回 false
                if (currFile.isFile() && name.endsWith(".txt")) {
                    return true;
                } else {
                    return false;
                }
            }   
        };
        //判断 File对象对应的目录是否存在
        if (file.exists()) {
         //获取过滤够的所有文件名数组
        	String[] lists = file.list(filter);
            for (String name : lists) {
                    System.out.println(name);
            }
        }
    }
}
```

+ 如果遍历的目录下还有目录，list() 方法显然是不能满足的，这时就需要使用 listFile()，进行**递归**

```java
import java.io.File;
public class Example {
    public static void main(String[] args) {
        //创建一个代表目录的 File对象
        File file = new File("D:\\Java");
        fileDir(file);//调用 fileDir()方法
    }
    public static void fileDir(File dir) {
        //获取表示目录下的所有文件的数组
        File[] files = dir.listFiles();
        //遍历所有子目录和文件
        for (File file : files) {
            if (file.isDirectory()) {
                //递归调用自己
                fileDir(file);
            }
            System.out.println(file.getAbsolutePath());
        }
    }
}
```





##### 删除文件及目录

+ 不能用 delete方法直接删除，需要通过递归的方式一个个删除

```java
import java.io.*;
public class Example {
    public static void main(String[] args) {
        File file = new File("D:\\Java");
        deleteDir(file);
    }
    public static void deleteDir(File dir) {
        if (dir.exists()) {
            File[] files = dir.listFiles();
            for (File file : files) {
                if (file.isDirectory()) {
                    deleteDir(file);
                } else {
                    file.delete();
                }
            }
            //删除完一个目录里的所有文件后，就删除这个目录
            dir.delete();
        }
    }
}
```

> 在 Java中删除目录是**从虚拟机直接删除的而不走回收站的**，文件一旦删除就无法恢复







#### 案例13 模拟文件管理器

![1553756831242](assets/1553756831242.png)

1. 定义 DocumentManager类

```java
package cn.test;
import java.io.File;
import java.util.ArrayList;
import java.util.Scanner;
public class DocumentManager {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("--1:指定关键字检索文件 2:指定后缀名检索文件" + "3:复制文件、目录  4:退出--");
        while(true) {
            System.out.print("请输入指令:");
            int cmd = sc.nextInt();
            switch(cmd) {
                case 1:
                    searchByKeyWord();//指定关键字检索文件
                    break;
                case 2:
                    searchBySuffix();//指定后缀名检索文件
                    break;
                case 3:
                    copyDirectory();//复制文件/目录
                    break;
                case 4:
                    exit();
                    break;
                default:
                    System.out.println("您输入的指令错误！");
                    break;
            }
        }
    }
    // **********1.指定关键字检索文件**************
    private static void searchBykeyWord() {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入要检索的目录:");
        String path =sc.next();//从控制台获取路径
        File file = new File(path);
        if(!file.exists() || !file.isDirectory()) {
            System.out.println(path + "(不是有效目录)");
            return;
        }
        System.out.print("请输入搜索关键字：");
        Stirng key = sc.next();//获取关键字
        //在输入目录下获取所有包含关键字的文件路径
        ArrayList<String> list = FileUtils.listFiles(file,key);
        for (Objetc obj : list) {
            System.out.println(obj);//将路劲打印到控制台
        }
    }
    // **********2.指定后缀名检索文件**************
    private static void searchBySuffix() {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入要检索的目录位置：");
        String path = sc.next();
        File file = new File(path);
        if (!file.exists() || !file.isDirectory()) {
            System.out.print(path + "(不是有效目录)");
            return;
        }
        System.out.print("请输入搜索后缀:");
        String suffix = sc.next();
        String[] suffixArray = suffix.split(",")；//获取后缀字符串
        //在输入目录下获取所有指定后缀名的文件路径
            ArrayList<String> list = FileUtils.listFiles(file, suffixArray);
        for (Object obj : list) {
            System.out.println(obj);//将路径打印到控制台
        }
    }
    // **********3.复制文件/目录**************
    private static void copyDirectory() throws Exception {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入源目录：");
        String srcDirectory = sc.next();
        File srcFile = new File(srcDirectoy);
        if (!srcFile.exists() || !srcFile.isDirectory()) {
            System.out.println("无效目录!");
            return;
        }
        System.out.print("请输入目标位置：");
        String destDirectory = sc.next();
        File destFile = new File(destDirectory);
        if (!destFile.exists() || !destFile.isDirectory()) {
            System.out.pringln("无效位置!");
            return;
        }
        //将源路径中的内容复制到目标路径下
        FileUtils.copySrcPathToDestPath(srcFile, destFile);
    }
    //********4.退出*********
    private static void exit() {
        System.out.println("您已退出系统，谢谢使用！");
        System.exit(0);
    }
}
```

+ 定义 FileUtils类

```java
package cn.test;
import java.io.*;
import java.util.ArrayList;
public class FileUtils {
    /**
     *指定关键字搜索
     *@param file File对象
     *@param key 关键字
     *@return 包含关键字的文件路径
     */
    public static ArrayList<String> listFiles(File file, final String[] suffixArray) {
        FilenameFilter filter = new FilenameFilter() {
            public boolean accept(File dir, String name) {
                File currFile = new File(dir, name);
                if (currFile.isFile()) {
                    for (String suffix : suffixArray) {
                        if (name.endsWith("." + suffix)) {
                            return true;
                        }
                    }
                }
                return false;
            }
        };
        //递归方式获取规定的路径
        ArrayList<String> arrayList = fileDir(file, filter);
        return arrayList;
    }
    /**
     *递归方式获取规定的路径
     *@param dir File对象
     *@param filter 关键字
     *@return 过滤器过滤后的文件路径
     */
    public static ArrayList<String> fileDir (File dir, FilenameFilter filter) {
        ArrayList<String> arraylist = new ArrayList<String>();
        File[] lists = dir.listFiles(filter);//获得过滤后的所有文件数组
        for (File list : lists) {
            //将文件的绝对路径放到集合中
            arraylist.add(list.getAbsolutePath());
        }
        //获取当前目录下所有文件的数组
        File[] files = dir.listFiles();
        //遍历所有的子目录和文件
        for(File file : files) {
            if (file.isDirectory()) {
            //如果是目录，递归调用 fileDir()
            ArrayList<String> every = filter(file, filter);
            arraylist.addAll(every);//将文件夹下的文件路径添加到集合中
        	}
    	}//此时的集合中有当前目录下的文件路径，和当前目录下的子目录下的文件路径
    	return arraylist
     }
    /**
     *复制文件/目录
     *@param srcFile 源目录
     *@param destFile 目标目录
     */
    public static void copySrcPathToDestPath(File srcDir, File destDir) throws Exception {
        File[] files = srcDir.listFiles();//子文件目录
        for (int i = 0; i < files.length(); i++) {
            File copiedFile = new File(destDir, files[i].getName());
            if (files[i].isDirectory()) {
                if(!copiedFile.mkdirs()) {
                    System.out.println("无法创建:" + copiedFile);
                    return;
                }
                //调用递归,获取子文件夹下的文件路径
                copySrcPathToDestPath(files[i], copiedFile);
            } else {//复制文件
                FileInputStream input = new FileInputStream(files[i]);
                FileOutputStream output = new FileOutputStream(copiedFile);//获取输出流
              byte[] buffer = new byte[1024];//创建缓冲区
                int n = 0;
                //循环读取字节
                while ((n = input.read(buffer)) != -1) {
                    output.write(buffer, 0, n);
                }
                input.close();
                output.close();
            }
        }
    }
}
```







### GUI(图形用户界面)

---

> GUI 的全称是 Graphical User Interface,即图形化用户界面。Java 针对GUI设计提供了丰富的类库，这些类库位于 java.awt 和 java.swing 包中，简称 AWT 和 Swing 。
>
> + AWT 是 SUN公司最早推出的一套 API：
>   + 使用本地操作系统所提供的图形库
>   + 重量级组件
>   + 不跨平台，组件种类有限
> + Swing 是 SUN公司对 AWT的改进，提供了更加丰富的功能和组件，足以满足 GUI 设计的一切需求



#### AWT概述

---

+ AWT 用于创建图形用户界面的一个工具包，提供了一系列实现图形界面的组件（窗口、按钮、文本框、对话框）

![1554168147271](assets/1554168147271.png)

+ AWT 分为两大基类：
  + `Component`  除菜单外其他 AWT组件的父类表示一个能力图形化方式显示出来并可以用户交互的对象
  + `MenuComponent`  是所有与菜单相关组件的父类
+ `Component` 类通常被称为组件，根据不同作用，可分为：
  + 基本组件类( 按钮、文本框之类的图形界面元素)
  + 容器类(Component的子类 Container 实例化的对象)

+ `Container` 类表示容器，它是一种特殊的组件，可以容纳其他组件
  + Window类型
  + Panel类型



##### Window

+ 不依赖其他容器而独立存在的容器，有两个子类
  + `Feame` 类（创建一个具有标题栏的框架窗口）
  + `Dialog` 类 （创建一个对话框，实现与用户的信息交互）

![1554169277873](assets/1554169277873.png)



##### Panel

+ 不能单独存在，只能存在于其他容器（Window 或其子类）中
+ 一个 Panel对象代表了一个长方形的区域，在区域内可以容纳其他组件
+ 在程序中，**用 Panel来实现一些特殊的布局**

```java
import java.awt.*;
public class Example {
    public static void main(String[] args) {
        //建立新窗体对象
        Frame f = new Frame("我的窗体！");
        //设置窗体的宽和高
        f.setSize(400,300);
        //设置窗体在屏幕中所处的位置（参数是左上角坐标）
        f.setLocation(300,200);
        //设置窗体可见
        f.setVisible(true);
    }
}
```





#### 布局管理器

+ 组件不能单独存在，必须放置在容器中，而组件在容器中的位置和尺寸是由布局管理器来决定的
+ Java.awt 提供了5种布局管理器
  + `FlowLayout ` (流式布局管理器)
  + `Border Layout` (边界布局管理器)
  + `GirdLayout` (网格布局管理器)
  + `GirdBagLayout` (网格包布局管理器)
  + `CardLayout` (卡片布局管理器)
+ 通过调用对象的 setLayout()方法设置布局器

```java
	Frame frame = new Frame();
	frame.setLayout(new FlowLayout());
```





##### 1. FlowLayout

+ **最简单的布局管理器**，在这种布局下，**容器会将组件按照添加顺序从左向右放置**。当到达容器的边界时，会自动将组件放到下一行的开始位置
+ 组件可以左对齐、居中对齐（**默认对齐**）或右对齐

![1554172048890](assets/1554172048890.png)

```java
import java.awt.*;
public class Example {
    public static void main(String[] args) {
        //创建名为 Flowlayout的窗体
        final Frame f = new Frame("Flowlayout");
        //设置布局管理器为 FlowLayout，所有组件左对齐，水平距离为20，垂直间距为 30
        f.setLayout(new FlowLayout(FlowLayout.LEFT,20,30));
        f.setSize(300,200);//设置窗体大小
        f.setLocation(300,200);//设置窗体显示的位置
        f.add(new Button("第1个按钮"));//把“第一个按钮”添加到 f窗口
        f.add(new Button("第2个按钮"));
        f.add(new Button("第3个按钮"));
        f.add(new Button("第4个按钮"));
        f.add(new Button("第5个按钮"));
        f.setVisible(true);//设置窗体可见
    }
}
```

+ FlowLayout 布局管理器的特点就是可以**将所有组件像流水一样依次进行排列，不需要用户明确的确定，但是在灵活性上偏差**
+ 窗体拉伸时，按钮的大小和间距将保持不变，但按钮相对于容器边界的距离会发生变化

![1554172799732](assets/1554172799732.png)



##### 2. BorderLayout

+ 一种较为复杂的布局方式，将容器划分为 5个区域（东、南、西、北、中）
+ 组件可以被放置在这 5个区域中的任意一个

![1554172955069](assets/1554172955069.png)

> + 箭头是指**改变容器大小时各个区域需要改变的方向**
>   + NORTH 和 SOUTH区域高度不变，==宽度调整==
>   + WEST 和 EAST 区域宽度不变，==高度调整==

```java
// add(Component comp, Object constraints)方法，向 borderLayOut的容器添加组件
import java.awt.*;
public class Example {
    public static void main(String[] args) {
        final Frame f = new Frame("BorderLayout");
        f.setLayout(new BorderLayout());
        f.setSize(300,300);
        f.setLocation(300,200);
        f.setVisible(true);
        //以下代码是创建 5个按钮，分别用于填充 BorderLayout的5个区域
        Button but1 = new Button("东部");//创建新按钮
        Button but2 = new Button("西部")；
        Button but2 = new Button("南部")；
        Button but2 = new Button("北部")；
        Button but2 = new Button("中部")；
        //以下代码是将创建好的按钮添加到窗体中，并设置按钮所在的区域
        f.add(but1,BorderLayout.EAST);
        f.add(but1,BorderLayout.WEST);
        f.add(but1,BorderLayout.SOUTH);
        f.add(but1,BorderLayout.NORTH);
        f.add(but1,BorderLayout.CENTER);
    }
}
```

![1554174006503](assets/1554174006503.png)

+ Frame默认使用 BorderLayout布局管理器
+ 添加组件时，**如果不指定添加到哪个区域，则默认添加到 CENTER区域，并且每个区域只能放置一个组件**
+ 如果向一个区域添加多个组件，那么后面的组件会覆盖前面的组件





##### 3. GirdLayout

+ 使用纵横线将容器分成 n行m列大小相等的网格，每个网格中放置一个组件
+ GirdLayout将自动占据网格的整个区域

![1554174506575](assets/1554174506575.png)

```java
import java.awt.*;
public class Example {
    public static void main(String[] args) {
        Frame f = new Frame("GirdLayout");//创建一个名为 GirdLayout的窗体
        f.setLayout(new GridLayout(3,3));//创建该窗体为 3*3的网格
        f.setSize(300,300);
        f.setLocation(400,300);
        //以下代码是循环添加 9个按钮到 GirdLayout中
        for (int i = 1; i <= 9; i++) {
            Button btn = new Button("btn" + i);
            f.add(btn);//向窗体添加按钮
        }
        f.setVisible(true);
    }
}
```

![1554174975885](assets/1554174975885.png)





##### 4. GirdBagLayout

+ **最灵活、最复杂的布局管理器**，与 GirdLayout 布局管理器类似，但是**允许网格中的组件大小各部相同，而且允许一个组件跨越一个或者多个网格

```java
---***使用网格包布局管理器的步骤如下***---
    (1)创建 GirdBagLayout布局管理器，并使容器采用该布局管理器
        GirdBagLayout layout = new GridBagLayout();
        container.setLayout(layout);
	(2)创建 GirdBagConstraints对象（布局约束条件），并设置该对象的相关属性
        GirdBagConstraints constraints = new GirdBagConstraints();
        constraints.gridx = 1;//设置网格的左上角横向索引
        constraints.gridy = 1;//设置网格的左上角纵向索引
        constraints.gridwidth = 1;//设置组件横向跨越的网格
        constraints.gridheight = 1;//设置组件纵向跨越的网格
	(3)调用 GirdBagLayout对象的 setConstraints()方法建立 GirdBagConstraints对象和受控组件之间的关联
		layout.setConstraints(component, constraints);
	(4)向容器中添加组件
		container.add(component);
//  1.GirdBagConstraints对象可以重复使用，只需要改变其属性即可
//	2.如果要添加多个组件，则重复步骤(2)(3)(4)
```

+ `GirdBagConstraints` **对象才是控制容器中每个组件布局的核心类**

![1554176201114](assets/1554176201114.png)

> + gridx 和 gridy 用于设置组件左上角所在网格的横向和纵向索引
> + gridwidth 和 gridheight 用于设置组件横向、纵向跨越几个网格
> + fill 用于设置是否及如何改变组件大小
> + weightx 和 weighty 用于设置组件在容器的水平方向和垂直方向的权重
>
> ==提醒==：如果希望组件的大小随着容器的增大而增大，必须同时设置 GirdBagConstraints 对象的 fill属性和 weightx、weighty属性

```java
import java.awt.*;
class Layout extends Frame {
    public Layout(String title) {
        GridBagLayout layout = new GridBagLayout();
  		GridBagConstraints c = new GridBagConstraints();
        this.setLayout(layout);
        c.fill = GridBagConstraints.BOTH;//设置组件横向和纵向可以拉伸
        c.weightx = 1;//设置横向权重为1
        c.weighty = 1;//设置纵向权重为1
        this.addComponent("btn1", layout, c);
        this.addComponent("btn2", layout, c);
        this.addComponent("btn3", layout, c);
        //添加的组件是本行最后一个组件
        c.gridwidth = GridBagConstraints.REMAINDER;
        this.addComponent("btn4", layout, c);
        c.weithtx = 0;
        c.weighty = 0;
        addComponent("btn5", layout, c);
        c.gridwidth = 1;//设置组件跨一个网格（默认值）
        this.addComponent("btn6", layout, c);
        //添加的组件是本行的最后一个组件
        c.gridwidth = GridBagConstraints.REMAINDER;
        this.addComponent("btn7", layout, c);
        c.gridheight = 2;
        c.gridwidth = 1;
        c.weightx = 2;
        c.weighty = 2;
        this.addComponent("btn8", layout, c);
        c.gridwidth = GridBagConstraints.REMAINDER;
        c.gridheight = 1;
        this.addComponent("btn9", layout, c);
        this.addComponent("btn10", layout, c);
        this.setTitle(title);
        this.pack();
        this.setVisible(true);
    }
    //增加组件的方法
    private void addComponent(String name, GridBagLayout layout, GridBagConstraints c) {
        Button bt = new Button(name);//创建一个名为 name的按钮
        layout.setConstraints(bt, c);//设置 GridBagConstraints和按钮的关联
        this.add(bt);//增加按钮
    }
}

//程序入口
public class Example {
    public static void main(String[] args) {
        new Layout("GridBagLayout");
    }
}
```

![1554186766673](assets/1554186766673.png)





##### 5. CardLayout

+ 界面上的选项卡，管理这些卡片的就是 CardLayout
+ **在任何时候只要其中一张卡片是可见的，这张卡片占据容器的整个区域**

![1554192226342](assets/1554192226342.png)

```java
import java.awt.*;
import java.awt.event.*;
//定义 Cardlayout 继承 Frame类，实现 ActionListener接口
class Cardlayout extends Frame implements ActionListener {
    Panel cardPanel = new Panel();//定义 Panel面板放置卡片
    Panel controlpaPanel = new Panel();//定义 Panel面板放置按钮
    Button nextbutton,preButton;
    CardLayout cardLayout = new CardLayout();//定义卡片布局对象
    //定义构造方法，设置卡片布局管理器的属性
    public Cardlayout() {
        setSize(300,200);
        setVisible(true);
        //为窗口添加关闭事件监听器
        this.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                Cardlayout.this.dispose();
            }
        });
        cardPanel.setLayout(cardLayout);
        //在 cardPanel面板对象中添加 3个文本标签
        cardPanel.add(new Label("第1个界面", label.CENTER));
        cardPanel.add(new Label("第2个界面", label.CENTER));
        cardPanel.add(new Label("第3个界面", label.CENTER));
        //创建两个按钮对象
        nextbutton = new Button("下一张卡片");
        preButton = new Button("上一张卡片");
        //为按钮对象注册监听器
        nextbutton.addActionListener(this);
        preButton.addActionListener(this);
        //将按钮添加到 controlpaPanel中
        controlpaPanel.add(preButton);
        controlpaPanel.add(nextbutton);
        //将 cardPanel面板放置在窗口边界布局的中间，窗口默认为边界布局
        this.add(CardPanel, BorderLayout.CENTER);
        //将 controlpaPanel面板放置在窗口边界布局的南区
        this.add(controlpaPanel, BorderLayout.SOUTH);
    }
    //以下代码实现了按钮的监听触发，并对触发事件做出相应的处理
    public void actionPerformed(ActionEvent e) {
        //如果用户单击 nextbutto，执行语句
        if (e.getSource() == nextButton) {
            //切换面板中的组件。若当前组件为最后一个组件，则显示第一个组件
            cardLayout.next(cardPanel);
        }
        if (e.getSource() == preButton) {
            //切换面板中的组件。若当前组件为最后一个组件，则显示第一个组件
            cardLayout.previous(cardPanel);
        }
    }
}
//程序的入口
public class Example {
    public static void main(String[] args) {
        Cardlayout cardlayout = new Cardlayout();
    }
}
```

![1554194106193](assets/1554194106193.png)





##### 6. 不使用布局管理器

+ 当一个容器被创建后，都会有一个默认的布局管理器
  + `Window、Frame、Dialog` 默认布局管理器是**BorderLayout**
  + `Panel`  默认布局管理器是**FlowLayout**
+ 取消布局管理器 `setLayout(null)`，取消后必须调用方法来为组件在容器中定位
  + **调用容器中每个组件的 `setSize()`和 `setLocation()`方法**
  + 或者 `setBounds()`方法【4个参数，分别是左上角的 x,y坐标和组件的长、宽】

```java
import java.awt.*;
public class Example {
    public static void main(String[] args) {
        Frame f = new Frame("hello");
    	f.setLayout(null);//取消 frame的布局管理器
        f.setSize(300,150);
        Button btn1 = new Button("press");
        Button btn2 = new Button("pop");
        btn1.setBounds(40, 60, 100, 30);
        btn2.setBounds(140, 90, 100, 30);
        //在窗口中添加按钮
        f.add(btn1);
        f.add(btn2);
        f.setVisible(true);
    }
}
```

![1554195111056](assets/1554195111056.png)







#### AWT事件处理

---

##### 事件处理机制

+ 事件处理机制专门**用于响应用户的操作（单机鼠标、按下键盘等操作）**
  + 事件对象(Event)：封装了GUI组件上发生的特定事件（通常是用户的一次操作）
  + 事件源（组件）：事件发生的场所，通常是产生事件的组价
  + 监听器(Listener):负责监听事件源上发生的事件，并对各种事件做出相应处理的对象（对象中包含事件处理器）
  + 事件处理器：监听器对象对接收的事件对象进行相应处理的方法

![1554435208184](assets/1554435208184.png)

+ 事件源是一个组件，用户操作时，这些动作会触发相应的事件。如果事件源注册了事件监听器，则触发的相应事件将会被处理。

```java
//演示窗口关闭的功能
import java.awt.*;
public class Example {
    public static void main(String[] args) {
        //建立新窗体
        Frame f = new Frame("我的窗体！");
        //设置窗体的宽和高
        f.setSize(300, 200);
        //设置窗体的出现位置
        f.setLocation(300, 200);
        //设置窗体可见
        f.setVisible(true);
        //为窗口组件注册监听器
        MyWindowListener mw = new MyWindowListener();
        f.addWindowListener(mw);
    }
}
//创建 MyWindowListener 类实现 WindowListener接口
class MywindowListener implements WindowListener {
    //监听器监听事件对象作出处理
    public void windowClosing(WindowEvent e) {
        Window window = e.getWindow();
        window.setVisible(false);
        //释放窗口
        window.dispose();
    }
    public void windowActivated(WindowEvent e) {}
    public void windowClosed(WindowEvent e) {}
    public void windowDeactivated(WindowEvent e) {}
    public void windowDeiconified(WindowEvent e) {}
    public void windowIconified(WindowEvent e) {}
    public void windowOpened(WindowEvent e) {}
}
```

![1554439913509](assets/1554439913509.png)



##### 事件适配器

+ 在上面的代码中，需要实现接口中定义的7个方法，然而在程序中需要用到的只有一个 windowClosing()，其他 6个都是空实现，没有发挥任何作用
+ 针对这样的问题，JDK提供了一些适配器类，它们是**监听器接口的默认实现类，这些实现类实现了接口的所有方法**，但方法中没有任何代码，程序可以通过**继承适配器类来达到实现监听器接口的目的**
+ 几乎所有的监听器接口都有对应的适配器类，通过继承适配器类来实现监听器接口时，需要处理哪种事件，就直接重写该事件对应的方法

```java
import java.awt.*;
import java.awt.event.*;
public class Example {
    public static void main(String[] args) {
        //建立新窗体
        Frame f = new Frame("我的窗体");
        f.setSize(400, 300);
        f.setLocation(300, 200);
        f.setVisible(true);
        f.addWindowListener(new MyWindowListener());
    }
}
//继承 WindowAdapter类，重写 windowClosing()方法
class MyWindowListener extends WindowAdapter {
    public void windowClosing(WindowEvent e) {
        Window window = (Window) e.getComponent();
        window.dispose();
    }
}
```





##### 用匿名内部类实现事件处理

+ 在实际开发中，**为了代码的简洁，经常通过匿名内部类来创建事件的监听器对象，针对所发生的事件进行处理**

```java
import java.awt.*;
import java.awt.event.*;
public class Example {
    public static void main(String[] args) {
        frame f = new Frame("我的窗体!");
        f.setSize(300, 200);
        f.setLocation(300, 200);
        f.setVisible(true);
        Button btn = new Button("EXIT");//创建按钮组件对象
        f.add(btn);//把按钮对象加载到窗口上
        //用内部类的方式为按钮组件注册监听器
        btn.addMouseListener(new MouseAdapter() {
            public void MouseClicked(MouseEvent e) {
                System.exit(0);
            } 
        });
    }
}
```







#### 常用事件分类

+ AWT 中提供了非常丰富的事件，这些事件大致可以分为
  + 窗体事件(WindowEvent)
  + 鼠标事件(MouseEvent)
  + 键盘事件(KeyEvent)
  + 动作事件(ActionEvent)



##### 1. 窗体事件

+ 大部分GUI应用程序都需要使用 Window窗体对象作为最外层的容器，**可以说窗体对象是所有GUI应用程序的基础**，应用程序中都是将其他组件直接或间接地置于窗体中
+ JDK中提供了一个类 WindowEvent用于表示窗体事件，对窗体事件进行处理时
  + 首先要定义一个实现了 WindowListener 接口的类作为窗体监听器
  + 通过 addWindowListener()方法对窗体对象与监听器绑定

```java
import java.awt.*;
import java.awt.event.*;
public class Example {
    public static void main(String[] args) {
        final Frame f = new Frame("WindowEvent");
        f.setSize(400, 300);
        f.setLocation(300, 200);
        f.setVisible(true);
        //使用内部类创建 WindowListener实例对象，监听窗体事件
        f.addWindowListener(new WindowListener() {
            public void windowOpened(WindowEvent e) {
                System.out.println("windowOpened---窗体打开事件");
            } 
            public void windowIconified(WindowEvent e) {
                System.out.println("windowIconified---窗体图标化事件")      
            }
            public void windowDeiconified(WindowEvent e) {
           		System.out.println("windowDeiconified---窗体停用事件");
            }
            public void windowClosing(WindowEvent e) {
                System.out.println("windowClosing---窗体正在关闭事件");
                ((Window) e.getComponent()).dispose();
            }
            public void windowClosed(WindowEvent e) {
                System.out.println("windowClosed---窗体关闭事件");
            }
            public void windowActivated(WindowEvent e) {
                System.out.println("windowActivated---窗体激活事件");
            }
        });
    }
}
```







##### 2. 鼠标事件

+ 几乎所有的组件都可以产生鼠标事件，处理鼠标事件时
  + 通过实现 MouseListener接口定义监听器（也可通过继承适配器 MouseAdapter类来实现）
  + 调用 addMouseListener()方法将监听器绑定到事件源对象

```java
import java.awt.*;
import java.awt.event.*;
public class Example {
    public static void main(String[] args) {
        final Frame f = new Frame("WindowEvent");
        //为窗口设置布局
        f.setLayout(new FlowLayout());
        f.setSize(300, 299);
        f.setLocation(300, 200);
        f.setVisible(true);
        Button but = new Button("Button");//创建按钮对象
        f.add(but);//在窗口添加按钮组件
        //为按钮添加鼠标事件监听器
        but.addMouseListener(new MouseListener() {
            public void mouseReleased(MouseEvent e) {
                System.out.println("mouseReleased--鼠标放开事件");
            }
            public void mousePressed(MouseEvent e) {
                System.out.println("mousePressed---鼠标按下事件");
            }
            public void mouseExited(MouseEvent e) {
                System.out.println("mouseExited---鼠标移除按钮区域事件");
            }
            public void mouseEntered(MouseEvent e) {
                System.out.println("mouseEnter--鼠标进入按钮区域事件");
            }
            public void mouseClicked(MouseEvent e) {
                System.out.println("mouseClicked--鼠标完成单击事件");
            }
        });
    }
}
```

+ MouseEvent类中定义了很多**常量来标识鼠标动作**

```java
public void mouseClicked(MouseEvent e) {
    if (e.getButton() == e.BUTTON1) {
        System.out.println("鼠标左击事件");
    }
    if (e.getButton() == e.BUTTON3) {
        System.out.println("鼠标右击事件");
    }
    if (e.getButton() == e.BUTTON2) {
        System.out.println("鼠标中键单击事件");
    }
}
```

> + 鼠标的单击次数也可以通过 MouseEvent 对象的 getClickCount()方法获取







##### 3. 键盘事件

+ JDK 中提供了一个 KeyEvent类表示键盘事件，处理键盘事件的监听器对象**需要实现 KeyListener接口或者继承 KeyAdapter类**

```java
import java.awt.*;
import java.awt.event.*;
public class Example {
    public static void main(String[] args) {
        Frame f = new Frame("KeyEvent");
        f.setLayout(new FlowLayout());
        f.setSize(400, 300);
        f.setLocation(300, 200);
        //创建文本框对象
        TextField tf = new TextField(30);
        f.add(tf);//在窗口添加文本框组件
        f.setVisible(true);
        //为文本框添加键盘事件监听器
        tf.addKeyListener(new KeyAdapter() {
            public void keyPressed(KeyEvent e) {
                int KeyCode = e.getKeyCode();//返回所按键对应的整数值
                String s = keyEvent.getKeyText(KeyCode);//返回按键的字符串描述
                System.out.print("输入的内容为：" + s + ",");
                System.out.println("对应的KeyCode为：" + KeyCode);
            } 
        });
    }
}
```





##### 4. 动作事件

+ 不代表某个具体的动作，只是表示一个动作发生了
+ 处理 ActionEvent 事件的监听器对象需要实现 ActionListener接口
+ **动作事件关注有意义的动作，但像鼠标移动和单击的细节则不是**









#### AWT绘图

+ GUI程序都需要在组件上绘制图形，Java提供了 Graphics类，抽象画笔绘制图形

![1554462488181](assets/1554462488181.png)

```java
/*
 *目前大部分网站为了防止用户在注册时重复提交表单，模仿注册页面图片验证码
 */
import java.awt.*;
import java.util.Random;
public class Example {
    public static void main(String[] args) {
        final Frame frame = new Frame("验证码");
        final Panel panel = new MyPanel();
        Frame.add(panel);
        frame.setSize(200, 100);
        //将Frame窗口居中
        frame.setLocationRelativeTO(null);
        frame.setVisible(true);
    }
}
class MyPanel extends Panel {
    public void paint(Graphics g) {
        int width = 160;//定义验证码图片的宽度
        int height = 40;//定义验证码的高度
        g.setColor(Color.LIGHT_GRAY);//设置上下文颜色
        g.fillRect(0, 0, width - 1, height - 1);//填充验证码背景
        //绘制干扰点
        Random r = new Random();
        for (int i = 0; i < 100; i++) {
        	int x = r.nextInt(width) - 2;
            int y = r.nextInt(height) - 2;
            g.drawOval(x, y, 2, 2);
        }
        g.setFont(new Font("黑体", Font.BOLD, 30));//设置验证码字体
        g.setColor(Color.BLUE);
        //产生随机验证码
        char[] chars = ("122345678jkwidiuawhth" + "xwdauUDIUIDWAHJHE").toCharArray();
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < 4; i++) {
            int pos = r.nextInt(chars.length);
            char c = chars[pos];
            sb.append(c, " ");
        }
        g.drawString(sb.toString(), 20, 30);
    }
}
```

![1554465903713](assets/1554465903713.png)







#### Swing

---

+ Swing包中提供了更加丰富、便捷、强大的GUI组件这些组件都是 Java语言编写而成的，因此Swing组件不依赖平台，真正做到了跨平台运行
+ 通常来说，**依赖本地平台的的AWT组件称为重量级组件，而把不依赖平台的Swing组件称为轻量级组件**

+ `JWindow,JFrame,Jdialog`Swing中三个顶级容器都需要依赖本地平台，因此被称为重量级组件

![1554466503161](assets/1554466503161.png)





##### JFrame

+ JFrame支持通用窗口所有的基本功能，例如窗口最小化、设定窗口大小

``` java
import java.awt.FlowLayout;
import javax.swing.*;
public class EXample extends JFrame {
    public Example() {
        this.setTitle("JFrameTest");
        this.setSize(250, 300);
        //定义一个按钮组件
        JButton bt = new JButton("按钮");
        //设置流式布局管理器
        this.setLayout(new FlowLayout());
        //添加按钮组件
		this.add(bt);
        //设置单击关闭按钮时的默认操作
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
    public static void main(String[] args) {
        new Example();
    }
}
```

![1554467051088](assets/1554467051088.png)

> + JFrame 和 Frame窗体效果大致相同，区别在于JFrame类提供了关闭窗口的功能，在程序中不需要添加窗体监听器





##### JDialog

+ Swing的另一个顶级窗口，也表示对话框
+ 对话框分为两种状态：
  + 模态对话框：户需要等到处理完对话框才能继续与其他窗口交互
  + 非模态对话框：允许用户在处理对话框的同时与其他窗口交互
+ 对话框是否模态，**可以在创建 JDialog对象时为构造方法传入参数设置，也可以在创建 JDialog对象后调用它的 `setModal()`方法进行设置**

![1554802257270](assets/1554802257270.png)

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Example {
    public static void main(String[] args) {
        //建立两个按钮
        JButton btn1 = new JButton("模态对话框");
        JButton btn2 = new JButton("非模态对话框");
        JFrame f = new JFrame("DialogDemo");
        f.setSize(300, 200);
        f.setLocation(300, 200);
        f.setLayout(new FlowLayout());//为内容面板设置布局管理器
        //在 Container对象上添加按钮
        f.add(btn1);
        f.add(btn2);
        //设置单击关闭按钮默认关闭窗口
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        f.setVisible(true);
        final JLabel label = new JLabel();
        final JDialog dialog = new JDialog(f, "Dialog");
        dialog.setSize(200, 150);
        dialog.setLocation(350, 250);
        dialog.setLayout(new FlowLayout());
        final JButton btn3 = new JButton("确定");//创建按钮对象
        dialog.add(btn3);//在对话框的内容面板添加按钮
        //为“模态对话框”按钮添加单击事件
        btn1.addActionListener(new addActionListener() {
            public void actionPerformed(ActionEvent e) {
                //设置对话框为模态
                dialog.setModal(true);
                //如果 JDialog窗口中没有添加 JLabel标签，就把 JLabel标签加上
                if (dialog.getComponents().length == 1) {
                    dialog.add(label);
                }
                //否则修改标签的内容
                label.setText("模态对话框，点击确定按钮关闭");
                //显示对话框
                dialog.setVisible(true);
            }
        });
        //为“非模态对话框”按钮添加单击事件
        btn2.addActionListener (new addActionListener() {
            public void actionPerformed(ActionEvent e) {
                //设置对话框为非模态
                dialog.setModal(false);
                //如果 JDialog窗口中没有添加 JLabel标签，就把 JLabel标签加上
                if (dialog.getComponents().length == 1) {
                    dialog.add(label);
                }
                //否则修改标签的内容
                label.setText("模态对话框，点击确定按钮关闭");
                //显示对话框
                dialog.setVisible(true);
            }
        });
        //为对话框中的按钮添加单击事件
        btn3.addActionListener(new addActionListener () {
            public void actionPerformed(ActionEvent e) {
                dialog.dispose();
            }
        });
    }
}
```

![1554804986016](assets/1554804986016.png)







##### 中间容器

+ Swing组件中还提供了**一些中间容器，容器不能单独存在，只能放在顶级窗口中**
+ 常见的中间容器有 JPanel 和 JScrollPane
  + JPanel：与 Panel使用方法基本一致，无边框，不能被移动、放大、缩小或者关闭的面板
  + JScrollPane:带有滚动条的面板容器，而且这个面板只能添加一个组件
    + 如果想在 JScrollPane面板中添加多个组件，应该将其先加入到 JPanel中，然后再添加到 JScrollPane

![1554805584652](assets/1554805584652.png)

```java
import java.awt.*;
import javax.swing.*;
public class Example extends JFrame {
    public Example () {
        this.setTitle("PanelDemo");
        //创建滚动面板
        JScrollPane scrollPane = new JScrollPane();
        //设置水平滚动条策略--滚动条需要时提示
        scrollPane.setVerticalScrollBarPolicy(scrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS);
        //定义一个JPanel面板
        JPanel panel = new JPanel();
        //在JPanel面板中添加四个按钮
        panel.add(new Button("按钮1"));
        panel.add(new Button("按钮2"));
        panel.add(new Button("按钮3"));
        panel.add(new Button("按钮4"));
        //设置JPanel面板在滚动面板中显示
        scrollPane.setViewportView(panel);
        //将滚动面板添加到内容面板的 Center区域
        this.add(scrollPane, BorderLayout.CENTER);
        //将一个按钮添加到内容面板的SOUTH区域
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setSize(400, 200);
        this.setVisible(true);
    }
    public static void mian(String[] args) {
        new Example ();
    }
}
```

![1554806567425](assets/1554806567425.png)



##### 文本组件

+ 接收用户输入的信息或向用户展示信息
  + 文本框（JTextField）
  + 文本域（JTextArea）
+ 有一个共同父类 JTextComponent，抽象类，提供了文本组件常用的方法

![1554865002555](assets/1554865002555.png)

+ `JTextField`:只能接收单行文本的输入。

![1554865086770](assets/1554865086770.png)

+ `JTextArea`:接收多行文本的输入，使用 JTextArea构造方法创建对象时可以设定区域的行数、列数

 ![1554865568535](assets/1554865568535.png)

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame {
    JButton sendBt;
    JTextField inputField;
    JTextArea charContent;
    public Example {
        this.setLayout(new BorderLayout());
        charContent = new JTextArea(12, 34);//创建一个文本域
        //创建一个滚动面板，将文本域作为其显示组件
        JScrollPane showPanel = new JScrollPane(charContent);
        charContent.setEditable(false);//设置文本域为不可编辑
        JPanel inputPanel = new JPanel();//创建一个 JPanel面板
        inputField =  new JTextField(20);//创建一个文本框
        sendBt = new JButton("发送");//创建一个发送按钮
        //为按钮添加事件
        sendBt.addActionListener(new addActionListener() {
            public void actionPerformed(ActionEvent e) {
                String content = inputField.getText();//获取输入的文本信息
                //判断输入的信息是否为空
                if (content != null && !content.trim().equals("")) {
                    //如果不为空，将输入的文本追加到聊天窗口
                    charContent.append("本人：" + content + "\n");
                } else {
                    //为空，提示聊天信息不能为空
                    charContent.append("聊天信息不能为空" + "\n");
                }
                inputField.setText("");//将输入的文本域内容置空
            }
        });
        Label label = new Label("聊天信息");//创建一个标签
        inputPanel.add(label);//将标签添加到 JPanel面板
        inputPanel.add(inputField);//将文本框添加到 JPanel面板
        inputPanel.add(sendBt);//将按钮添加到 JPanel面板
        //将滚动面板和 JPanel面板添加到 JFrame窗口
        this.add(showPanel, BorderLayout.CENTER);
        this.add(inputPanel, BorderLayout.SOUTH);
        this.setTitle("聊天窗口");
        this.setSize(400, 300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
    public static void main (String[] args) {
        new Example();
    }
} 
```

![1554867883161](assets/1554867883161.png)

> + JFrame模拟一个简单的聊天窗口
>   + 首先通过 BorderLayout 布局管理器将窗口分为 CENTER 和 SOUTH
>   + CENTER区域放置一个 JScrollPane滚动面板，在其中放置了 JTextArea文本域，用于显示聊天记录
>   + SOUTH区域放置了一个 JPanel面板，其中放置了3个组件，其中
>     + JLabel标签用于信息说明
>     + JTextField 文本框用于输入用户的聊天信息
>     + JButton按钮用于发送聊天信息
> + ==注意==：JLabel组件是一个静态组件，用于显示一行静态文本和图标，**它起到的作用只是信息说明，不接收用户的输入，也不能添加事件。





##### 按钮组件

---

+ 常见的按钮组件有 JButton 、 JCheckBox、JRadioButton等

+ 都是抽象类 AbstractButton类的直接或间接子类

![1554878419554](assets/1554878419554.png)





###### JCheckBox

+ 称为复选框，有**选中/未选中两种状态**，如果用户想接收的输入只有“是“和”非“，则可以通过复选框来切换状态
+ 如果复选框有多个，则用户可以选中其中一个或者多个

![1554878714397](assets/1554878714397.png)

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame {
    private JCheckBox italic;
    private JCheckBox bold;
    private JLabel label;
    public Example () {
        //创建一个 JLabel标签，标签文本居中对齐
        label = new JLabel("欢迎你", JLabel.CENTER);
        //设置标签文本的字体
        label.setFont(new Font("宋体", Font.PLAIN, 20));
        this.add(label);//在 Center区域添加标签
        JPanel panel = new JPanel();//创建一个 JPanel面板
        //创建两个 JCheckBox复选框
        italic = new JCheckBox("ITALIC");
        bold = new JCheckBox("BOLD");
        //为复选框定义 ActionListener监听器
        ActionListener listener = new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                int mode = 0;
                if (bold.isSelected()) {
                    mode += Font.BOLD;
                }
                if (italic.isSelected()) {
                    mode += Font.italic;
                    label.setFont(new Font("宋体", mode, 20));
                }
            }
        };
        //为两个复选框添加监听器
        italic.addActionListener(listener);
        bold.addActionListener(listener);
        //在 JPanel面板添加复选框
        panel.add(italic);
        panel.add(bold);
        //在SOUTH区域添加 JPanel面板
        this.add(panel, BorderLayout.SOUTH);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setSize(300, 300);
        this.setVisibel(true);
    }
    public static void main(String[] args) {
        new Example();
    }
}
```

![1554879758808](assets/1554879758808.png)





###### JRadioButton

+ 单选按钮，只能选中一次
+ 当一个按钮被选中时，先前被选中的按钮就会自动取消选中

> + 由于 JRadioButton组件本身并不具备这种功能，因此想要实现互斥，需要使用 javax.swing.ButttonGroup类，这是**一个不可见组件，不需要将其增加到容器中显示**，只是在逻辑上表示一个单选按钮组
> + 将多个 JRadioButton按钮添加到同一个单选按钮组对象中，就能实现按钮的单选功能

![1554880672465](assets/1554880672465.png)

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame {
    private ButtonGroup group;//单选按钮组对象
    private JPanel panel;//JPanel面板放置 3个 JRadioButton按钮
    private JPanel pallet;// JPanel面板作为调色板
    public Example() {
        pallet = new JPanel();
        this.add(pallet, BorderLayout.CENTER);//将调色板面板放在中间
        panel = new JPanel();
        group = new ButtonGroup();
        //调用 addRadioButton()方法
        addJRdioButton("灰");
        addJRdioButton("粉");
        addJRdioButton("黄");
        this.add(panel, BorderLayout.SOUTH);
        this.setSize(300, 300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
    /**
     * JRadioButton 按钮的文本信息 用于创建一个带有文本信息的 JRadioButton按钮
     * 将按钮添加到 panel面板和 ButtonGroup按钮组中，并添加监听器
     */
    private void addJRdioButton(final String Text) {
        JRadioButton radioButton = new JRadioButton(text);
        group.add(radioButton);
        panel.add(radioButton);
        radioButton.addActionListener(new addActionListener() {
            public void actionPerformed(ActionEvent e) {
                Color color = null;
                if ("灰".equals(text)) {
                    color = Color.GRAY;
                } else if ("粉"equals(text)) {
                    color = Color.PINK;
                } else if ("黄"equals(text)) {
                    color = Color.YELLOW;
                } else {
                    color = Color.WHITE;
                }
                pallet.setBackground(color);
            }
        });
    }
    public static void main(String[] args) {
        new Example();
    }
}
```

![1554883403901](assets/1554883403901.png)





###### JComboBox

+ 组合框或者下拉列表框，将所有的选项折叠收藏在一起，默认显示第一个添加的选项
+ JComboBox组合框组件分为两种形式：
  + 可编辑：用户可以在现有选项中选择，也可以自己输入新的内容
  + 不可编辑：用户只能在现有的选项列表中进行选择

![1554883769536](assets/1554883769536.png)

![1554883794927](assets/1554883794927.png)

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame {
    private ButtonGroup group;//单选按钮组对象
    private JPanel panel;//JPanel面板放置 3个 JRadioButton按钮
    private JPanel pallet;// JPanel面板作为调色板
    public Example() {
        pallet = new JPanel();
        this.add(pallet, BorderLayout.CENTER);//将调色板面板放在中间
        panel = new JPanel();
        group = new ButtonGroup();
        //调用 addRadioButton()方法
        addJRdioButton("灰");
        addJRdioButton("粉");
        addJRdioButton("黄");
        this.add(panel, BorderLayout.SOUTH);
        this.setSize(300, 300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
    /**
     * JRadioButton 按钮的文本信息 用于创建一个带有文本信息的 JRadioButton按钮
     * 将按钮添加到 panel面板和 ButtonGroup按钮组中，并添加监听器
     */
    private void addJRdioButton(final String Text) {
        JRadioButton radioButton = new JRadioButton(text);
        group.add(radioButton);
        panel.add(radioButton);
        radioButton.addActionListener(new addActionListener() {
            public void actionPerformed(ActionEvent e) {
                Color color = null;
                if ("灰".equals(text)) {
                    color = Color.GRAY;
                } else if ("粉"equals(text)) {
                    color = Color.PINK;
                } else if ("黄"equals(text)) {
                    color = Color.YELLOW;
                } else {
                    color = Color.WHITE;
                }
                pallet.setBackground(color);
            }
        });
    }
    public static void main(String[] args) {
        new Example();
    }
}


import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame {
    private JComboBox comboBox;//定义一个 JComboBox组合框
    private JTextField field;//定义一个 JTextField文本框
    public Example() {
        JPanel panel = new JPanel();
        comboBox = new JComboBox();
        //为组合框添加选项
        comboBox.addItem("请选择城市");
        comboBox.addItem("北京");
        comboBox.addItem("北京");
        comboBox.addItem("北京");
        comboBox.addItem("北京");
        comboBox.addItem("北京");
        //为组合框添加事件监听器
        comboBox.addActionListener(new addActionListener() {
            public void actionPerformed(ActionEvent e) {
                String item = (String) comboBox.getSelectedItem();
                if ("请选择城市".equals(item)) {
                    field.setText("");
                } else {
                    field.setText("您选择的城市是:" + item);
                }
            }
        });
        field = new JTextField(20);
        panel.add(comboBox);//在面板中添加组合框
        panel.add(field);//在面板中添加文本框
        //在内容面板中添加 JPanel面板
        this.add(panel, BorderLayout.NORTH);
        this.setSize(350, 100);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
    public static void main(String[] args) {
        new Example();
    }
}
```

![1554885119017](assets/1554885119017.png)





###### 菜单组件

---

+ 在GUI程序中，菜单是很常用的组件，**利用 Swing提供的菜单组件可以创建出多种样式的菜单



1. 下拉式菜单

+ 创建下拉式菜单需要 3个组件
  + JmenuBar(菜单栏)
  + Jmenu(菜单)
  + JmenuItem(菜单项)

![1554950483019](assets/1554950483019.png)

+ JMenuBar:水平的菜单栏，用来管理菜单，不参与同用户的交互式操作。可以放在容器的任何位置
  + **通常情况下会使用顶级窗口（JFrame、Jdialog）的 setJMenuBar(JMenuBar menuBar)方法将它放置到顶级窗口的顶部。**
  + **JMenuBar有一个无参构造函数，创建菜单栏时，只需要使用 new关键字创建 JMenuBar对象即可**
  + **创建其对象后，调用 add(JMenu c)方法为其添加 JMenu菜单
+ JMenu：用来整合管理菜单项，**菜单可以是单一层次结构，也可是多层次结构**
  + 大多情况下，会使用构造函数 JMenu(String text)创建 JMenu菜单

![1554952037783](assets/1554952037783.png)

![1554952056381](assets/1554952056381.png)

+ JMenuItem：菜单系统中最基本的组件，和 JMenu菜单一样，在创建菜单项时，**通常会使用构造方法 JMenuItem(String tetx)为菜单项指定文本内容**
  + 由于 JMenuItem类是继承自 AbstractButton类的，因此可以把其看做一个**按钮**
  + 如果使用无参的构造方法创建了一个菜单项，则可以调用从 AbstractButton类中继承的 setText(String text)方法和 setlcon()方法为其设置文本和图标

```java
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame{
    public Example() {
        JMenuBar menuBar = new JMenuBar();//创建菜单栏
        this.setJMenuBar(menuBar);//将菜单栏添加到 JFrame窗口中
        JMenu menu = new JMenu("操作");//创建菜单
        menuBar.add(menu);  //将菜单添加到菜单栏上
        //创建两个菜单项
        JMenuItem item1 = new JMenuItem("弹出窗口");
        JMenuItem item2 = new JMenuItem("关闭");
        //为菜单项添加事件监听器
        item1.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                //创建一个 JDialog窗口
                JDialog dialog = new JDialog(Example.this, true);
                dialog.setTitle("弹出窗口");
                dialog.setSize(200, 200);
                dialog.setLocation(50, 20);
                dialog.setVisible(true);
            }
        });
        item2.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                System.exit(0);
            }
        });
        menu.add(item1);//将菜单项添加到菜单中
        menu.addSeparator();//添加一个分隔符
        menu.add(item2);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setSize(300, 300);
        this.setVisible(true);
    }

    public static void main(String[] args) {
        new Example();
    }
}
```

![1554964304076](assets/1554964304076.png)



![1554964375630](assets/1554964375630.png)



2. 弹出式菜单

+ 在 Windows桌面单击鼠标右键会出现一个菜单，就是弹出式菜单
+ **JPopupMenu 弹出式菜单，调用 add()方法添加到 JMenuItem菜单项，但它默认是不可见的，如果想要显示，则必须调用 show(Component invoke, int x, int y)**

```java
import java.awt.event.*;
import javax.swing.*;
public class Example extends JFrame{
    private JPopupMenu popupMenu;
    public Example() {
        //创建一个 JPopupMenu菜单
        popupMenu = new JPopupMenu();
        //创建三个 JMenuItem菜单项
        JMenuItem refreshItem = new JMenuItem("refrush");
        JMenuItem createItem = new JMenuItem("create");
        JMenuItem exitItem = new JMenuItem("exit");
        //为 exitItem菜单项添加事件监听器
        exitItem.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                System.exit(0);
            }
        });
        //往 JPopupMenu菜单添加菜单项
        popupMenu.add(refreshItem);
        popupMenu.add(createItem);
        popupMenu.addSeparator();//添加一个分割符
        popupMenu.add(exitItem);
        //为 JFrame窗口添加 clicked鼠标事件监听器
        this.addMouseListener(new MouseAdapter() {
            public void mouseClicked(MouseEvent e) {
                //如果单击的是鼠标的右键，显示 JPopupMenu菜单
                if (e.getButton() == e.BUTTON3) {
                   popupMenu.show(e.getComponent(), e.getX(), e.getY());
                }
            }
        });
        this.setSize(300, 300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }

    public static void main(String[] args) {
        new Example();
    }
}
```





##### JTable

---

+ 表格是一个由多行、多列组成的二维显示区
+ JTable创建表格非常容易，可以把一个二维数据包装成一个表格，**这个二维数据既可以是一个二维数组，也可以是集合元素 Vector对象**
+ 为了给表格的每一列指定列标题，还需要传入一个一维数据作为列标题，这个一维数据既可以是一维数组，也可以是 Vector对象

![1554966289158](assets/1554966289158.png)

```java
import java.awt.event.*;
import javax.swing.*;
public class Example {
    //创建 JFrame窗口
    JFrame jf = new JFrame("简单表格");
    //声明 JTable类型的变量 table
    JTable table;
    //1.定义一维数组作为列标题
    Object[] columnTitle = {"姓名", "年龄", "性别"};
    //2.定义二维数组作为表格行对象数据
    Object[][] tableDate = {
            new Object[] { "李清照", 29, "女"},
            new Object[] { "舒格拉蒂", 56, "男"},
            new Object[] { "李白", 35, "男"},
            new Object[] { "弄玉", 18, "女"},
            new Object[] { "虎头", 2, "男"},
    };
    //3.使用 JTable对象创建表格
    public void init() {
        //以二维数组和一维数组来创建一个 JTable对象
        table = new JTable(tableDate, columnTitle);
        //将 JTable对象放在 JScrollPane中，并将该 JScrollPane放在窗口中显示出来
        jf.add(new JScrollPane(table));
        //设置自适应 JFrame窗体大小
        jf.pack();
        //设置单击关闭按钮时默认退出
        jf.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        //设置窗体可见
        jf.setVisible(true);
    }
    public static void main(String[] args) {
        new Example().init();
    }
}
```

![1554967562685](assets/1554967562685.png)









#### 案例15 水果超市管理系统

![1554967726650](assets/1554967726650.png)

1. 创建项目，实现系统欢迎窗口类的定义
   + 创建一个名为fruitstore 的 java Project，在 src下创建一个包 cn.test.view，并在包中创建一个继承自 JFrame的抽象类 AbstractMainFrame，在类中实现了系统欢迎窗口的显示

```java
package cn.test.view;
import java.awt.BorderLayout;
import java.awt.event.*;
import javax.swing.*;

/**
 * 主窗口类
 */
@SuppressWarnings("serial")
public abstract class AbstractMainFrame extends JFrame{
    //组件
    private JLabel titleLabel = new JLabel(new ImageIcon("FruitStore.jpg"));
    private JButton btn = new JButton("进入系统");//顾客按钮
    //构造函数
    public AbstractMainFrame() {
        this.init();//初始化操作
        this.addComponent();//添加组件
        this.addListener();//添加监听器
    }
    //初始化操作
    private void init() {
        this.setTitle("水果超市欢迎你！");//标题
        this.setSize(600, 400);//窗体大小与位置
        this.setResizable(false);//窗体大小固定
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
    //添加组件
    private void addComponent() {
        //窗体使用默认的边界布局，北区放入图片
        this.add(this.titleLabel, BorderLayout.NORTH);
        //创建 JPanel对象
        JPanel btnPanel = new JPanel();
        //清除布局，使用 JPanel中的组件可以自定义位置
        btnPanel.setLayout(null);
        //将 JPanel对象添加到窗体中
        this.add(btnPanel);
        //定义边界位置
        btn.setBounds(240, 20, 120, 50);
        //将按钮添加到 JPanel对象中
        btnPanel.add(btn);
    }
    //添加监听器
    private void addListener() {
        btn.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                showAdminDialog();
            }
        });
    }
    //展示管理员界面方法
    public abstract void showAdminDialog();
}
```

2. 定义主窗口测试类

   + 编写一个测试类来验证其效果和功能,在 src下创建一个名为 cn.test.fruitstore.test的包，包中创建一个名称为 AbstractMainFrameTest的类，该类继承 AbstractMainFrame

   ```java
   package cn.test.fruitstore.test;
   import cn.test.fruitstore.view.AbstractMainFrame;
   /**
    *主窗口测试类
    */
   @SuppressWarnings("serial")
   public class AbstractMainFrameTest extends AbstractMainFrame {
       //定义主函数
       public static void main(String[] args) {
           new AbstractMainFrameTest().setVisible(true);
       }
       //覆盖父类中管理员界面的方法
       public void showAdminDialog () {
           System.out.println("进入管理界面");
       }
   }
   ```

3. 在项目的 src目录下，创建一个名为 cn.test.fruitstore.tools的包，包下创建一个名为 GUITools的类，类中定义窗口组件居中的方法以及显示窗口图标的方法

```java

```

