# 我的JAVA**学习笔记**

## BY **王治凯**

[TOC]

## 第一章    JAVA类基础知识 

### 第一节    JAVA类结构和main函数

**JAVA的几大特性**

1.Java是简单的

JAVA语言不使用指针，而是引用，不必为了内存管理而担忧

2.JAVA是面向对象的

JAVA提供类，接口和继承等面向对象的特性，但只支持类之间的单继承（接口之间可多继承）

3.JAVA是多线程的

JAVA支持多个线程同时执行，多个线程还能同步

**Class类**

注意：java文件只能有一个public class,且其名字必须和文件名字完全一致，项目一定不能游离类之外，一个class最多只能有一个main函数，（程序启动的总入口）其无法被其他方法/类所调用

类的构成（java程序最小独立单元)

-成员变量/属性

-成员方法/函数

**变量**

```java
public class demo{
    static int a=0;//类变量
    String str='吴恺科技工作室'//实例变量
    public void code(){
        int i=0;//局部变量
    } 
    public static void main(string[] args){//每次都要有这个，相当于main函数的形参
        System.out.println("MIAS");//这里为换行输出，相当于\n，c语言的printf类似于System.out.print
    }
}
```

讲一下区别：

局部变量： 局部变量在方法、构造方法、或者语句块被执行的时候创建，当它们执行完成后，变量将会被销毁。局 部变量没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。

实例变量： 实例变量声明在一个类中，但在方法、构造方法和语句块之外； 当一个对象被实例化之后，每个实例变量的值就跟着确定； 实例变量在对象创建的时候创建，在对象被销毁的时候销毁；

类变量：类变量也称为静态变量，在类中以 static 关键字声明，但必须在方法之外。 静态变量储存在静态存储区。经常被声明为常量，很少单独使用static声明变量。 静态变量在第一次被访问时创建，在程序结束时销毁

**数据基本类型**

1. byte(8位，一个字节)

2. short(16位，两个字节)

3. int(32位，四个字节)

4. long(64位)

5. float(单精度32位)

6. double(双精度64位)

7. boolean(只有两个取值ture&false默认false,作为一种标志来记录)

8. char(16位)

   

   **Java运算符:monkey_face:**

   

   **算术运算符**（+,-,*,/,%,++,--)

   d++和++d的区别是，d++是先使用d，再自加，++d是先加后再使用

   **关系运算符**（只会返回ture或者false），包括（==，！=，>, <, >=,<=）

   **位运算符**

   ![image-20210525203436222](C:\Users\86151\AppData\Roaming\Typora\typora-user-images\image-20210525203436222.png)

   **逻辑运算符**（且&&，或||，非！）

   **赋值运算符**（=，+=，-=，*=，/=，（%）=....)

   **三元运算符:dog2:条件运算符**（？：），是if...else的缩写

   **instanceof 运算符** 该运算符用于操作对象实例，检查该对象是否是一个特定类型（类类型或接口类型）

   

   **条件语句**:information_desk_person:

   1.if 

   2.if....else 

   3.if...else if ...else

   ```java
   if(布尔表达式 1){
   //如果布尔表达式 1的值为true执行代码
   }else if(布尔表达式 2){
   //如果布尔表达式 2的值为true执行代码
   }else if(布尔表达式 3){
   //如果布尔表达式 3的值为true执行代码
   }else {
   //如果以上布尔表达式都不为true执行代码
   }
   ```

   Swith case语句

   ```java
   switch(expression){
   case value :
   //语句
   break; //可选
   case value :
   //语句
   break; //可选
   //你可以有任意数量的case语句
   default : //可选
   //语句
   }
   ```

   **理解:clap:**

   当遇到 break 语句时，switch 语句终止。程序跳转到 switch 语句后面的语句执行。case 语 句不必须要包含 break 语句。如果没有 break 语句出现，程序会继续执行下一条 case 语句， 直到出现 break 语句。default 分支不需要 break 语句。

   switch case 执行时，一定会先进行匹配，匹配成功返回当前 case 的值，再根据是否有 break，判断是否继续输出，或是跳出判断。

   如果 case 语句块中没有 break 语句时，匹配成功后，从当前 case 开始，后续所有 case 的 值都会输出。

   **循环语句:punch:**

   

   1.while循环     (只有布尔表达式为ture时才进行循环)

   ```java
   while( 布尔表达式 ) {
   //循环内容
   }
   ```

   2.do..while循环 （do…while 循环至少会执行一次）

   ```java
   do {
   //代码语句
   }while(布尔表达式);
   
   ```

   3.for循环

   ```java
   for(初始化; 布尔表达式; 更新) {
   //代码语句
   }
   ```

   4.快捷键foreach JAVA里的加强循环

   ```
   for(声明语句 : 表达式)
   {
   //代码句子
   }
   ```

   ![image-20210525204406205](C:\Users\86151\AppData\Roaming\Typora\typora-user-images\image-20210525204406205.png)

5.continue关键字

 适用于任何循环控制结构中。作用是让程序立刻跳转到下一次循环的迭代。



再来聊聊自定义函数

1.函数必须放在类的范围内

2.同一个类中，函数名称可以相同（重载函数）,但是参数的个数或者类型必须有所不同

3.不能以返回值来区分同名函数

4.函数可以互相调用



**阶段作业**

第一题

```java
public class HelloWorld {

	public static void main(String[] args) {

		System.out.println("Hello World!");

		int a = 1;

		a=a+1;

		a=a+2;

		System.out.println("a is " + a);

		a=a+3;  //断点行,此时a=4

		a=a+4;

		System.out.println("a is " + a);

	}

}
```

第二题

1  2  3  4  5

6  7  8  9  10

11 12 13 14 15

16 17 18 19 20

21 22 23 24 25

需要在main函数的输入参数中设置5，输出5*5的数字方格。如果是输入7，则是7*7的数字方格。

我的解法（有多种思路，这里用最简单的做演示）

```java
import java.util.Scanner;
public class text {
    public static void main(String[] args) {
        System.out.println("请输入n");
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int i, j = 0;
        int a = 1;
        for (i = 0; i < n; i++) {
            for ( j = 0; j < n; j++) {
                System.out.print(a + "\t");
                a++;
            }
            System.out.println();

        }
    }
}
```

第三题

```
import java.util.Scanner;

public class text {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("请输入塔的层数(奇数且都大于等于5，小于等于11）");
        int n= sc.nextInt();
        int i,j;
        if ((n > 4 && n < 12) && (n & 1) != 0) {
            int kong = n / 2 + 1;
            int xing = 1;
            for ( i = 0; i < n; i++) {
                for ( j = 0; j < kong; j++) {
                    System.out.print(" ");
                }
                for ( j = 0; j < xing; j++) {
                    System.out.print("*");
                }
               System.out.println("");//换行

                if (i < n / 2) {
                    xing += 2;
                    kong--;
                } else {
                    xing -= 2;
                    kong++;
                }
            }
        }
    }

}
```

需要在main函数的输入参数中设置5，输出5层星塔。如果是输入7，则是7层星塔。假设输入参数都是奇数，且都大于等于5，小于等于11。

### 第二节 面对对象的语言

#### 1.面向对象的基本概念 

在说对象之前先来聊聊类的概念

什么是类，比如最简单的类class A{}，这是没有任何属性和行为的

对象A obj =new A();

简单来讲，类是定义，是一种规范，而对象是实例，是类的一个实现，是具体的。

打个比方

类——吴恺的食谱

对象——根据食谱做出来的菜，就比如西红柿炒蛋

对象=属性+方法

对象的规范=属性定义+方法定义

- 现实世界是由对象和对象之间的相互作用共同组成的

- 对象不仅包括成员变量还有成员方法

- 对象的内容可以继承

##### 面向对象和面向过程的区别

 例如，现在有两位师傅“面向过程”和“面向对象”要设计-一个首饰盒: 

 (1）“面向过程”师傅:用户提出哪些要求，师傅就针对用户的要求进行制作，直接制作‘ 出一个完整的整体，本身也不准备好做首饰盒所需要的工具，而是需要什么再单独拿什么。

 (2）“面向对象”师傅:针对用户提出的要求进行分析，并将分析的结果设计成一张完整 的图纸，与需求的用户确认，然后将一切的准备工作全部处理完之后再分块制作，最后将 各个小的部分组装在一起。

 从以上两个师傅的做法可以发现，“面向对象”师傅要比“面向过程”师傅更能适应用户 的变化，而一旦用户有变化之后，“面向过程”师傅基本上要推倒重做，而“面向对象” 师傅却可以适应变化。

#####  类的定义和使用

- **类的定义**：类实际上是表示一个客观某类群体的一些基本特征抽象，由属性和方法组成。

- **类的属性**：定义类一个个的具体信息，实际上一个属性就是一个变量,也叫成员变量。

- **类的方法**：一些操作的行为。

​       以人来举例子，因为人类是一个很大的概念，是一个群体；这里我们就可以把人类抽 象成一个类来定义；因为你可以代表自己，不能说自己代表整个人类吧，所以人类就可以声明成一 个类。 然后人类有很多基本特征，头发， 眼睛，鼻子，皮肤颜色等。这些基本特征就可以称为人类这个类的属性。 接着作为一个人，你要吃饭，睡觉，学习吧，这些都是人的行为，在类中它有称为方法。

```java
package person;
public class Person {
String name;
int age;
String color;
public void eat()
{
System.out.println("该吃饭了，好想吃吴恺鸡。");
}
public void sleep()
{
System.out.println("上课了，该钓鱼了。");
}
public void doHomework()
{
System.out.println("遭了高数作业还没做，赶紧找个人。");
}
}
```

每个JAVA类都必须有构造函数，如果没有显示定义的构造函数，编译器就会自动的为该类产生一个空的无形参的构造函数

每个子类的构造函数的第一句话是super关键字引导的继承

类里的成员属性是私有的private

方法则是公有的public，这就是java的信息隐藏规则

#####   this关键字

 对⾃⾝对象的⼀个地址引⽤，负责指向本类中的成员方法，当然也可以替代本类的构造函数

#####   super关键字

  是类似引⽤ 但不是引⽤的调⽤

   在⼦类构造⽅法中要调⽤⽗类的构造⽅法，⽤“super(参数列表)”的⽅式调⽤，参数不 是必须的。同时还要注意的⼀点是：“super(参数列表)”这条语句只能⽤在⼦类构造⽅ 法体中的第⼀⾏。

（注意区分关系:sweat_drops:）

#### 2.使用对象

方法的声明及使用

:point_right:**定义**：方法就是一段可重复调用的代码段。在C语言中好像是被称为函数，不过在java中我们称为方法。

:loudspeaker:**方法的好处**：可以重复利用，增加代码的质量

:star2:**命名规范**：第一个单词的首字母小写，之后每个单词的首字母大写，如printInfo()

ps:在定义类时，全部单词的首字母必须大写

:eyes:**方法的结构**

```java
public static 返回值类型 方法名称（类型参数1,类型参数2，...) {
//程序语句;
//[ return表达式];
}
//如果返回类型是void这里我们就不用return 数据回去
```

例如

```java
public void doHomework() {
System.out.println("遭了高数作业还没做，赶紧找个人。");
}

```

**:laughing:******方法的重载********: 就是方法名称相同，但参数的类型和参数的个数不同。

​      通过传递参数的个数及类型的 不同可以完成不同功能的方法调用。

```java
public static int add(int x,int y)
{
return x+y;
}
public static int add(int x,int y,int z)
{
return x+y+z;
}
public static float add（float x,float y)
{
return x+y;
}
```

:v:**结束一个方法**：如果返回类型是void则调用方法就自动结束了，如果是int，或者是float，string， 用return返回对应数据结束方法。

**:ear:方法的重写**：子类与父类方法的方法名，参数，返回值都要相同

（1）父类与子类之间的多态性，对父类的函数进行重新定义。如果在子类中定义某方法与其 父类有相同的名称和参数，我们说该方法被重写 (Overriding)。在java中，子类可继承父类中的方 法，而不需要重新编写相同的方法。但有时子类并不想原封不动地继承父类的方法，而是想作一定 的修改，这就需要采用方法的重写。方法重写又称方法覆盖; 

（2）若子类中的方法与父类中的某一方法具有相同的方法名、返回类型和参数表，则新方法 将覆盖原有的方法。如需父类中原有的方法，可使用super关键字，该关键字引用了当前类的父类; 

（3）子类函数的访问修饰权限不能少于父类的.

##### 构造方法

在对象实例化时就直接把对象属性赋值

```java
Person ts=new Person("吴恺",18,"green");
Person tq=new Person("崔校",18,"yellow");
//person类里的构造方法
public Person(String name, int age, String color) {
this.name = name;
this.age = age;
this.color = color;
}
```

  **注意：** 

- 构造方法的名称必须与类名称一致。 

- 构造方法的声明处不能有任何返回值类型的声明。 

- 不能在构造方法中使用return返回一个值。



#### 3.面向对象的三大特性：封装，继承，多态



##### 封装

指利⽤抽象数据类型将数据和基于数据的操作封装在⼀起，使其构成⼀个不可分割的独⽴ 实体，对外不可见。也可以使⽤上⾯的访问修饰符，限制访问权限.（数据隐藏）

```java
private String name;
private int age;
private String color;
//这种情况下，外部访问成员变量目前只能够通过getter来得到数据，外部改变目前也只能通过setter来访问

```

封装之后就不需要管内部是如何实现功能的，直接操作就可以，就比如c语言的调用函数

##### 继承

拥有反映事物一般特性的类，然后在其基础上派生出反映特殊事物的类。

**关键字： extends**

表示正在构造的新类派⽣于⼀个已存在的类。被继承的类称为超类，基类或⽗ 类； 继承产生的类称为⼦类，派⽣类或孩⼦类。

:clap:Java继承只能继承⼀个⽗类

java所有类都是单根继承的

java所有类都继承自java.lang.object类

```java
public class Student extends Person {
//子类调用父类的构造方法
public Student(String name, int age, String color) {
super(name, age, color);
}
public void doHomework() {
System.out.println("我要做作业了");
}
}
//这里你会发现学生也会拥有人的属性和基本方法，这就是继承的好处
```

##### 多态

java语言中含有对象有着多态和方法重载；对象可以在特定的情况下，表现不同的状态，从 ⽽对应着不同的属性和⽅法；我们可以在不同的调用下，选择不同的方法

作用：

- 以统一的接口来操作某一类中不同的对象的动态行为
- 对象之间的解耦

契约设计：类不会直接使用另一个类，而是采用接口的形式

**类转型**

变量支持互相转换

类型也可以相互转型，但只限制于有继承关系的类

**子类可以转换成父类（向上转型），而父类不可以转换成子类**，**但是父类本身就是从子类转化过来的则可以再转换成子类（向下转型）**

对象向上转型：

```java
Person stu = new Stdudent ()
/*在这里我们这样理解，这里定义了一个Person 类型的stu，它指向Student对象实例。由于Student是继承与Person，所以Student可以自动向上转型为Person，所以stu是可以指向Student实例对象的。这样做的好处是，在继承中我们知道子类是父类的扩展，它可以提供比父类更加强大的功能，如果我们定义了一个指向子类的父类引用类型，那么它除了能够引用父类的共性外，还可以使用子类强大的功能。但是向上转型存在一些缺点，那就是它必定会导致一些方法和属性的丢失，而导致我们不能够获取它们。所以父类类型的引用可以调用父类中定义的所有属性和方法，对于只存在与子类中的方法和属性就不能调用了。
```

对象向下转型：对象先向上转型，在向下转型

```java
Person per = new Student();//向上转型
Student stu = (Student) per;//向下转型
//调用父类及子类所有方法，弥补向上转型的缺点。
```

**第四题**

完善以下程序，利用swap函数，完成数字按从小到大的顺序输出。例如输入5 4 3 输出3,4,5。



import java.util.Scanner;



public class Main

{

​	public static void main(String[] args)

​	{

​		//创建Scanner对象

​		//System.in表示标准化输入，也就是键盘输入

​        Scanner sc = new Scanner(System.in);

​        //利用hasNextXXX()判断是否还有下一输入项

​        int a = 0;

​        int b = 0;

​        int c = 0;

​        if (sc.hasNext()) {

​          a = sc.nextInt();

​        }

​        if (sc.hasNext()) {

​          b = sc.nextInt();

​        }

​        if (sc.hasNext()) {

​          c = sc.nextInt();

​        }

​        if(a==0 || b==0 || c==0)

​        {

​    	  System.out.println("输入不能为0");

​    	  System.exit(-1);

​        }

​    

​        MyNumber obj1, obj2, obj3;

​       

```
        obj1.num = a;
        obj2.num = b;
        obj3.num = c;
        swap(obj1, obj2);
        swap(obj2, obj3);
        swap(obj1, obj2);
        System.out.println(obj1.num + " " + obj2.num + " " + obj3.num);
```



​	}

​	

​	public static void swap(MyNumber m, MyNumber n)

​	{

​		if(m.num > n.num)

​		{

​			int s = m.num;

​			m.num = n.num;

​			n.num = s;

​		}

​	}

}



class MyNumber

{

​	int num;

}



**输入格式:**

输入3个数字。



**输出格式：**

数字从小到大排列



**输入样例：**

5

4

3



**输出样例：**

3,4,5

### 第三节 抽象类和接口

#### 1.抽象类

相关概念：一个完整的类是如果存在方法就都要实现，一个完整的类才可以被实例化，被new出来

如果一个类暂时有方法未实现，需要被定义为抽象类

**关键字：abstract**

抽象类由成员变量，具体方法，抽象方法组成

子类继承抽象父类时，如果实现父类所有的abstract方法就是完整类，反之则是抽象类。

抽象类不能实例化对象，故必须被继承，才能被使用

在Java中抽象类表示的是一种继承关系，一个类只能继承一个抽象类，而一个类却可以实现 多个接口。

简单理解：抽象类可以当作一个模板，它里面的方法是抽象的，也就是还未实现的，需要子类去继承并且实例化

```java
public abstract class GuitarPlayer {
private Computer computer;//私有属性：电脑
private String name;//私有属性，姓名
public Programmer(Computer computer, String name) {
this.computer = computer;
this.name = name;
}
//get set方法
public computer computer() {
return computer;
}
public String getName() {
return name;
}
public void setcomputer(Computer computer) {
this.computer = computer;
}
public void setName(String name) {
this.name = name;
}
public abstract void playgame();//抽象方法：玩游戏
public abstract Music makeMusic(String inspire);//抽象方法：玩游戏，需要传入数据，返回游戏
public void eat(){//普通方法，不抽象
System.out.println(name+"在恰饭");
}
}
```

抽象类中可以声明两类方法，分别为抽象方法和与之对应的普通方法

- **抽象方法**：由abstract关键词修饰，只能声明接收的参数类型和返回的参数类型，不能书写方法 的具体实现，这个方法子类必须覆写，以此实现此方法的具体功能。

- **普通方法**：常规的方法，具体是使用规则可以参考父类中的方法的继承规则。

继承抽象类时需注意：内部方法为抽象方法，非抽象子类必须**强制进行覆写**，不然会报错

#### 2.接口

定义：如果类的所有方法都没有实现，那么这个类就是接口（interface)

**接口是抽象方法的集合**，接口声明了某种能力，拥有某种接口的对象一定具备这种能力。

类只可以继承一个类，但是可以实现多个接口，继承和实现可以同时。

类与类之间的继承使用的关键词为extends，而一个类实 现一个接口使用的是implements关键词

在implements后面跟上接口的名称，如果需要实现多个接口，接口名称与接口名称之间要用“,”隔开

#### 3.接口与抽象类的区别

**语法层面上**

- 接口支持多继承，抽象类不支持多继承（也就是说一个类可以继承多个接口，但是只能继承一个抽 象类）
- 接口中只能声明抽象方法，抽象类中可以声明普通方法

- 接口中的成员变量只能是public static final的，抽象类的成员变量可以是各种类型的

**设计层面上**

- 接口是对方法的抽象，而抽象类是对类的抽象
- 抽象类可以有部分方法实现，接口所有方法不能有实现
- 接口没有main函数
- 抽象类方法可以有private/protectted,接口方法都是public



继承是一种是不是的关系，而接口是一种有没有的关系。



### 第四节  static和final

##### static 关键字

可作用于

- 变量
- 方法
- 类
- 匿名方法块

static变量只依赖于类存在，不依赖于对象实例存在

static方法是静态的，无需通过对象来引用，可以通过类名直接引用，由于方法是静态的，故只能使用静态变量不能使用非静态变量，也没法引用非静态的方法

static块

只在类第一次加载时调用，运行期间代码只执行一次，执行顺序static块>匿名块>构造函数

单例模式

- 限定某一个类在整个程序运行过程中，只能保留一个实例对象在内存空间
- 属于创建型模式类型
- 采用static来共享对象实例
- 采用private构造函数防止new操作

##### final

- final可以修饰：属性，方法，类，局部变量（方法中的变量）
- final类 :  不能被子类继承
- final方法：不能被子类改写
- final变量：基本类型不能被修改值，对象类型不能被修改指针
- 利用关键字final对一个变量赋值的时候，表示这个变量只能被赋值一次，一旦被赋值以后将不能再进行更改
- 如果是基本型的变量，不能修改其值
- 如果是对象实例，不能修改它的指针                                                                                                                                         

##### 常量

定义：不会修改的变量

如final,static(只读)，java接口中的变量

组合在一起就是：

public final static double ABC =4.0

对象生成有两种：常量赋值（栈内存），new创建（堆内存）



### 第五节  package,import和 classpath



#### Package

- package即为包的意思，在java类文件的第一句给出包的名称，即说明文件的目录位置
- package的包名尽量唯一
- 域名是唯一的，故常用域名做包名
- 类的完整名字：包名+类名

#### import

- import在类定义之前，必须全部放在package之后
- 可以用**import**关键字来引入需要的类
- 可以用来引入一个目录下的所有类，比如 import java.lang.*意思是包括java.lang下面所有的类文件，但是不包括所有子目录文件
- import尽量精确，不推荐使用*



**:collision:java通过包(package)来分开类，通过引用(import)来导入类**



#### jar文件

**定义：**jar文件是java所持有的一种文件格式，用于可执行程序文件的传播

**本质：**java文件实际上是一组class文件的压缩包

**优点：**

- jar文件可以包括多个class，比多层目录更加简介实用
- jar文件只包括class，而没有包含Java文件，在保护源文件和知识版权方面可以起到更好的作用
- 可以把多个class文件压缩成jar文件，可以规定给一个版本号，更容易进行版本控制

#### java访问权限

- private:私有的，只能本类访问
- default （通常忽略不写）同一个包类访问
- protected 同一个包，子类均可以访问
- public 公开的，所有类都可以访问

**使用范围：**四种都可以用来修饰成员变量、成员方法、构造函数 

​                    default和public可以修饰类

**建议：**成员变量都是private

​            成员方法都是public

第五次作业

```
package com.bussiness;//bussiness包

import com.test.Worker;//这里的操作是导入worker

public class Boss {
    public static void main(String[] a)

    {

        Worker w = new Worker();

        w.sayHello();

    }
}
```

```
package com.test;//test包


public class Worker {

    public void sayHello() {

        System.out.println("hello");

    }

}
```

### 第六节 JAVA常用类

#### java类库

- 包名以java开始的包是Java核心包
- 包名以Javax开始的包是Java拓展包
- 可以从相关API文档找到已有的功能组件

#### 数字相关类

- 整数 Short,Int,Long

- 浮点数 Float,Double

- 大整数 BigInteger(大整数),BigDecimal(大浮点数)

- 随机数类 Random

- 工具类 Math

  | 常用math          |
  | :---------------- |
  | 对数函数log       |
  | 绝对值函数abs     |
  | 比较函数max、min  |
  | 幂函数pow         |
  | 四舍五入函数round |
  | 向下取整floor     |
  | 向上取整ceil      |

  #### 字符相关类

  使用频率最高：String

  **可变字符串**

  - StringBuffer (字符串加减，同步，性能好)
  - StringBuilder(字符串加减，不同步，性能更好)

  #### 时间相关类

  - java.util.Date（基本废弃）
  - java.sql.Date（和数据库对应的时间类）
  - Calendar是目前程序中最常用的，但是是抽象类

  **java.time**

  - 新的Java日期，时间API的基础包

####       格式化相关类

java.test.Format

> NumberFormat:数字格式化，抽象类
>
> 1234567 -> 1,234,567

> MessageFormat:字符串格式化
>
>  "Hello{1}"格式化为Hello World

> DateFormat:日期/时间格式化，抽象类
>
>  将当前时间转化为YYYY-MM-DD HH24: MI:SS

### 第七节 Java异常处理

#### 定义：异常，即程序不正常的状态

eg

- int a=5/0;
- 数组越界访问
- 读取的文件不存在

#### 异常处理

- 使程序返回到安全状态
- 保存结果并关闭

#### 异常分类

> Throwable 所有错误的祖先
>
> Error 系统内部错误或者资源耗尽

> **Exception** 程序有关的异常
>
> IOException 外界相关的错误 RuntimeException 程序自身错误的异常

#### 异常处理

- 允许用户即使保存结果
- 抓住异常，分析异常内容
- 控制程序返回到安全状态
- try： 正常业务逻辑代码
- catch： 当try发生异常将执行catch代码，若无异常就绕过
- finally： 当执行了try或catch之后，必须执行finally
- throws:声明异常
- catch块可以有多个，每个有不同的入口形参。进入catch之后，并不会返回到try发生异常的位置，也不会执行后续的catch代码块，一个异常只能进入一个catch代码块
- 一个方法被覆盖，那么覆盖她的方法必须抛出相同的异常或者异常的子类
- 如果父方法抛出多个异常，那么重写的子类方法必须抛出那些异常的子类，也就是不能抛出新的异常

#### 自定义异常

- 需要继承Exception类或者其子类

1. 继承自Exception就变成Checked Exception

2. 继承RuntimeException就变成Unckecked Exception

   

- 自定义重点在构造方法

1. 调用父类Exception的message构造函数

2. 可以自定义自己的成员变量

   

- 在程序中采用throw主动抛出异常

**第六次作业**

输入一个字符串，请判断是否满足身份证基本要求，并返回具体的生日yyyy-mm-dd。如果输入数据有误，请输出0000-00-00。基本要求是：a)必须是18位；b) 前面位数必须是数字，最后一位可以是数字或小写字母；c) 日期是存在的。



**输入格式:**

一个身份证号码，18位字符串



**输出格式：**

yyyy-mm-dd



**输入样例：**

53010219200508011x



**输出样例：**

1920-05-08



### 第八节 JAVA数据结构

#### 1.数组

##### 定义：

一种确定大小的储存同种数据的容器，可通过位置索引来快速定位来访问数据（需明确容器的长度）

##### 初始化：

1. 元素类型[] 数组名 = new 元素类型[元素个数或数组长度];
2. 元素类型[] 数组名 = new 元素类型[]{元素1，元素2，……}

#### 2.JCF

全称：Java Collections Framework（集合框架）

容器框架 为表示和操作容器而规定的一种标准体系结构

- 对外的接口 容器中所能存放的抽象数据类型
- 接口的实现 可复用的数据结构
- 算法 对数据的查找和排序

- 容器框架的优点：提高数据存取效率，避免程序员重复劳动

####  3.列表List

#####         ArrayList:

- 以数组实现的列表，不支持同步

List list =Collections.synchronizedList(new ArrayList(..));

- 利用索引位置可以快速定位访问
- 不适合指定位置的插入和删除
- 适合变动不大，用于查询的数据
- 相比于java数组，容量可以动态调整

#####         LinkedList：

- 以双向链表实现的列表，不支持同步
- 可被当作堆栈、队列和双端队列进行操作
- 顺序访问高效，随机访问较差，中间插入和删除高效
- 适用于经常变化的数据

#### 4.集合Set

##### 主要特性

- 确定性：能判定任意对象是否属于某一个结合
- 互异性：集合内每个元素都是无差异的，仅内容差异
- 无序性：集合内的顺序无关

##### JAVA中的集合接口Set

- HashSet 基于散列函数的集合 无序 不支持同步

- TreeSet 基于树结构的集合 可排序的 不支持同步
- LinkedHashSet 基于散列函数和双向链表的集合 可排序的 不支持同步

#### 5.映射Map

定义：两个集合之间元素的对应关系

一个输入对应到一个输出

- HashTable 同步 慢 数据量小
- HashMap 不支持同步 快 数据量大（最常用的映射结构）
- Properties 同步 文件形式 数据量小

第七次作业

在国际机场，我们会发现有多个货币兑换的窗口，这是由于各国货币的单位价值是不一样的。下面列出了某日国际货币的汇率表（相对于100人民币的各国货币值）。

 

| 货币 | CNY  | HKD  | USD  | EUR  |
| ---- | ---- | ---- | ---- | ---- |
| 汇率 | 100  | 118  | 15   | 13   |

 

例如，100元人民币可以兑换118香港币。请利用继承机制与Comparable接口实现不同数目货币对象价值的排序。下面给出了程序的基本框架，请给出相关的函数实现。(假设所有的输入数值和比较都是用整数)



### 第九节 JAVA文件读写

#### 1.文件

##### 概述：

- 文件系统是由操作系统管理的
- 文件系统和Java进程是**平行**的，是两套系统
- 系统文件是由文件夹和文件递归组合而成的
- 文件目录分隔符

1. Linux/Unix 用/隔开
2. Windows用\隔开 涉及到转义 在程序中需要用/或\\ \代替

- 文件包括文件里面的内容和文件的基本属性
- 文件的基本属性：名称、大小、拓展名、修改时间等

##### File文件类

- java.io.File是文件和目录的重要类(JDK6以前是唯一)
- File类与OS无关，但会受到OS的权限限制
- File不涉及具体的文件内容，**只涉及属性**

#### 2.JAVA IO包

文件系统和JAVA是两套系统

JAVA读文件，只能以数据流的形式进行



java.io包中

- 字节：byte，8bit，最基础的储存单位
- 字符：a，10000，我，の
- 数据类型：3，5，25，abcdef
- 文件是以字节保存，因此程序变量保存到文件需要转化

#### 3.文本文件读写

##### 文件类型

- 一般文本文件--txt
- 一般二进制文件--dat
- 带特殊格式的文本文件--xml
- 带特殊格式的二进制文件--doc,ppt

文本可以理解为数据的一个容器，用于储存大量的数据，因为文件很大故java只能以流的形式依次处理

输出：数据从Java到文件中，写操作

输入：数据从文件到Java中，读操作

##### 写文件

- 先创建文件 写入数据 关闭文件
- FileOutputStream OutputStreamWriter BufferedWriter
- BufferWriter 
- write 
- newLine
- try-resource语句 自动关闭资源
- 关闭最外层的数据流 将会把其上的所有的数据流关闭

##### 读文件

- 先打开文件 逐行读入数据 关闭文件
- FileInputStream BufferedReader InputStreamReader
- BufferReader
- readLine
- try-resource语句 自动关闭资源
- 关闭最外层的数据流 将会把其上的所有的数据流关闭

#### 4.二进制文件读写

#####   二进制文件

1. 狭义上说 采用字节编码 非字符编码的文件
2. 广义上说 一切文件都是二进制文件
3. 用记事本等无法打开阅读

#####   二进制文件读写

1. 输出数据到文件中
2. 从文件中读取数据

#####   写文件

- 先创建文件 写入数据 关闭文件
- FileOutputStream BufferedOutputStream DataOutputStream
- try-resource语句 自动关闭资源
- 关闭最外层的数据流 将会把其上的所有的数据流关闭

#####   读文件

- 先创建文件 写入数据 关闭文件
- FileInputStream BufferedInputStream DataInputStream
- try-resource语句 自动关闭资源
- 关闭最外层的数据流 将会把其上的所有的数据流关闭

第八次作业

读取以下的a.txt，统计相同单词的次数，最后按照次数的大小降序排列，输出到b.txt中。

a.txt (===算分隔符，不算单词，不考虑单词大小写)

==============

hello world

hello

java world  hello

==============



b.txt

============

hello,3

world,2

java,1

============



提示：需要用到的内容有文本文件读和写操作。还要加上数据结构，有ArrayList, HashMap,Comparable等。

第九次作业

通常来说动物的物理年龄与其生理年龄是不匹配的，如果要严格的根据动物的生理年龄排序需要有一个具体的参照（例如人）。下面列出了狗和人以及猫和人的年龄对照表。

 

| 狗   | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 人   | 18   | 23   | 28   | 32   | 36   | 40   | 45   | 50   | 55   | 60   |

 

| 猫   | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 人   | 15   | 24   | 28   | 32   | 36   | 40   | 44   | 48   | 52   | 56   |

例如，1岁的狗与1岁的猫相比，1岁的狗生理年龄较大。请利用继承机制与Comparable接口实现不同狗与猎豹对象的排序。下面给出了程序的基本框架，请给出相关的函数实现。

```java
import java.util.Arrays;
import java.util.Scanner;

class Animal {

    int age;//动物年龄
    int mage; //映射到人的年龄
    String name; //名字
    static int[] dog = {0, 18, 23, 28, 32, 36, 40, 45, 50, 55, 60};
    static int[] cat = {0, 15, 24, 28, 32, 36, 40, 44, 48, 52, 56};
    @Override
    public String toString() {
        return name + "," + age;
    }
}

class Dog extends Animal implements Comparable<Animal> {
    public Dog(String name, int age) {
        super.name = name;
        super.mage = dog[age];
        super.age = age;
    }

    @Override
    public int compareTo(Animal o) {
        if (mage < o.mage)
            return -1;
        else
            return 1;
    }

    

}

class Cat extends Animal implements Comparable<Animal> {
    public Cat(String name, int age) {
        super.name = name;
        super.mage = cat[age];
        super.age = age;
    }

    @Override
    public int compareTo(Animal o) {
        if (mage < o.mage)
            return -1;
        else
            return 1;
    }

    //实现你的构造函数与Comparable中的接口

}


public class text {


    public static void main(String[] args) {

        Animal[] as = new Animal[4];


        // 初始化

        Scanner sc = new Scanner(System.in);


        // 利用hasNextXXX()判断是否还有下一输入项

        if (sc.hasNext()) {

            as[0] = new Dog("dog1", sc.nextInt());

        }

        if (sc.hasNext()) {

            as[1] = new Cat("cat1", sc.nextInt());

        }

        if (sc.hasNext()) {

            as[2] = new Dog("dog2", sc.nextInt());

        }

        if (sc.hasNext()) {

            as[3] = new Cat("cat2", sc.nextInt());

        }
        Arrays.sort(as);
        for (Animal animal : as) {
            System.out.println(animal);
        }
    }
}
```



### 章节小结

java基础原理：类/对象，继承，多态，异常，包

java常用类库：数字，字符串，时间

java基础数据结构：ArrayList,HashSet,HashMap

初步应用：相关文件的处理

附相关关键字

![image-20210609145114799](C:\Users\86151\AppData\Roaming\Typora\typora-user-images\image-20210609145114799.png)

