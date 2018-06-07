##一、Java基本语法：
    1.概念：
        ·对象：对象是一个类的实例，有状态和行为。
        ·类：类是一个模板，它描述一类对象的行为和状态。
        ·方法：方法就是行为，一个类可以有很多种方法。逻辑运算、数据修改以及所有动作都是方法中完成的。
        ·实例变量：每个对象都有独特的实例变量，对象的状态由这些实例变量的值决定。

    2.注意：
        编写Java程序时，需要注意：
        ·大小写敏感：Java是大小写敏感的。
        ·类名：对于所有的类来说。类名的首字母应该大写。如果类名由若干单词组成，则每个单词的首字母应该大写。
        ·方法名：所有的方法名都应该以小写字母开头。如果方法名含有若干单词，则后面的每个单词首字母大写。
        ·源文件名：必须和类名保持一致。XXXX.java(切记Java是大小写敏感的)
        ·主方法入口：所有的Java程序有public static void main (String []args)方法开始执行

    3.Java标识符
        Java的所有组成部分都需要名字。类名、变量名以及方法名都被称为标识符。
        关于Java标识符，有以下几点需要注意：
        ·所有的标识符都应该以字符（A-Z或者a-z），美元符（￥），或者下划线（_）开始的。
        ·首字母之后可以是字母、美元符、下划线、数字的任何字符组合
        ·关键字不能用作标识符
        ·标识符是大小写敏感的

    4.Java修饰符
        ·访问控制修饰符：default、public、protected、private
        ·非访问控制修饰符：final、abstract、strictfp

    5.Java变量
        ·局部变量
        ·类变量（静态变量）
        ·成员变量（非静态变量）

    6.Java数组

    7.Java枚举

    8.Java关键字
        访问控制             private 私有的
                            protected   受保护的
                            public  公共的

        类、方法和变量修饰符    abstract    声明抽象
                            class   类
                            extends 扩允,继承
                            final   最终值,不可改变的
                            implements  实现（接口）
                            interface   接口
                            native  本地，原生方法（非Java实现）
                            new 新,创建
                            static  静态
                            strictfp    严格,精准
                            synchronized    线程,同步
                            transient   短暂
                            volatile    易失

        程序控制语句          break   跳出循环
                            case    定义一个值以供switch选择
                            continue    继续
                            default 默认
                            do  运行
                            else    否则
                            for 循环
                            if  如果
                            instanceof  实例
                            return  返回
                            switch  根据值选择执行
                            while   循环

        错误处理             assert  断言表达式是否为真
                            catch   捕捉异常
                            finally 有没有异常都执行
                            throw   抛出一个异常对象
                            throws  声明一个异常可能被抛出
                            try 捕获异常
                            包相关 import  引入
                            package 包
                            基本类型    boolean 布尔型
                            byte    字节型
                            char    字符型
                            double  双精度浮点
                            float   单精度浮点
                            int 整型
                            long    长整型
                            short   短整型
                            null    空

        变量引用              super   父类,超类
                            this    本类
                            void    无返回值
                            保留关键字   goto    是关键字，但不能使用
                            const   是关键字，但不能使用
    9.Java注释
        ·单行注释：//
        ·多行注释：/*
                    *注释
                    *注释
                */

    10.Java空行
        空白行，或者有注释的行，Java编译器会自动忽略掉

    11.继承
        在Java中，一个类可以由其他类派生。如果你要创建一个类，而且已经存在一个类具有你所需要的属性或方法，那么你可以将新创建的类继承该类。
        利用继承的方法，可以重用已存在类的方法和属性，而不用重写这些代码。被继承的类称为超类（super class），派生类称为子类（subclass）

    12.接口
        在Java中，接口可理解为对象间相互通信的协议。接口在继承中扮演着很重要的角色。
        接口只定义派生要用到的方法，但是方法的具体实现完全取决于派生类。



##二、Java对象和类
    1.Java中的类
        类可以看成是创建Java对象的模板
        public class Dog{
          String breed;
          int age;
          String color;
          void barking(){
          }

          void hungry(){
          }

          void sleeping(){
          }
        }
        一个类可以包含以下类型变量：
            ·局部变量：在方法、构造方法或者语句块中定义的变量被称为局部变量。变量声明和初始化都是在方法中，方法结束后，变量就会自动销毁。
            ·成员变量：成员变量是定义在类中，方法体之外的变量。这种变量在创建对象的时候实例化。成员变量可以被类中方法、构造方法和特定类的语句块访问。
            ·类变量：类变量也声明在类中，方法体之外，但必须声明为static类型。
            ·一个类可以拥有多个方法，在上面的例子中：barking()、hungry()和sleeping()都是Dog类的方法。

    2.构造方法
        每个类都有构造方法。如果没有显式地为类定义构造方法，Java编译器将会为该类提供一个默认构造方法。
        在创建一个对象的时候，至少要调用一个构造方法。构造方法的名称必须与类同名，一个类可以有多个构造方法。
        下面是一个构造方法示例：
        public class Puppy{
            public Puppy(){
            }

            public Puppy(String name){
                // 这个构造器仅有一个参数：name
            }
        }

    3.创建对象
        对象是根据类创建的。在Java中，使用关键字new来创建一个新的对象。创建对象需要以下三步：
        声明：声明一个对象，包括对象名称和对象类型。
        实例化：使用关键字new来创建一个对象。
        初始化：使用new创建对象时，会调用构造方法初始化对象。
        下面是一个创建对象的例子：
        public class Puppy{
           public Puppy(String name){
              //这个构造器仅有一个参数：name
              System.out.println("小狗的名字是 : " + name );
           }
           public static void main(String []args){
              // 下面的语句将创建一个Puppy对象
              Puppy myPuppy = new Puppy( "tommy" );
           }
        }
        编译并运行上面的程序，会打印出下面的结果：
        小狗的名字是 : tommy

    4.访问实例变量和方法
        通过已创建的对象来访问成员变量和成员方法，如下所示：
        /* 实例化对象 */
        ObjectReference = new Constructor();
        /* 访问类中的变量 */
        ObjectReference.variableName;
        /* 访问类中的方法 */
        ObjectReference.MethodName();

    5.实例
        下面的例子展示如何访问实例变量和调用成员方法：
        public class Puppy{
           int puppyAge;
           public Puppy(String name){
              // 这个构造器仅有一个参数：name
              System.out.println("小狗的名字是 : " + name );
           }

           public void setAge( int age ){
               puppyAge = age;
           }

           public int getAge( ){
               System.out.println("小狗的年龄为 : " + puppyAge );
               return puppyAge;
           }

           public static void main(String []args){
              /* 创建对象 */
              Puppy myPuppy = new Puppy( "tommy" );
              /* 通过方法来设定age */
              myPuppy.setAge( 2 );
              /* 调用另一个方法获取age */
              myPuppy.getAge( );
              /*你也可以像下面这样访问成员变量 */
              System.out.println("变量值 : " + myPuppy.puppyAge );
           }
        }

        编译并运行上面的程序，产生如下结果：
        小狗的名字是 : tommy
        小狗的年龄为 : 2
        变量值 : 2

    6.源文件声明规则
        ·当在一个源文件中定义多个类，并且还有import语句和package语句时，要特别注意这些规则。
        ·一个源文件中只能有一个public类
        ·一个源文件可以有多个非public类
        ·源文件的名称应该和public类的类名保持一致。例如：源文件中public类的类名是Employee，那么源文件应该命名为Employee.java。
        ·如果一个类定义在某个包中，那么package语句应该在源文件的首行。
        ·如果源文件包含import语句，那么应该放在package语句和类定义之间。如果没有package语句，那么import语句应该在源文件中最前面。
        ·import语句和package语句对源文件中定义的所有类都有效。在同一源文件中，不能给不同的类不同的包声明。
        ·类有若干种访问级别，并且类也分不同的类型：抽象类和final类等。这些将在访问控制章节介绍。
        ·除了上面提到的几种类型，Java还有一些特殊的类，如：内部类、匿名类。

    7.Java包
        包主要用来对类和接口进行分类。当开发Java程序时，可能编写成百上千的类，因此很有必要对类和接口进行分类。

    8.一个简单的例子
        在该例子中，我们创建两个类：Employee 和 EmployeeTest。
        首先打开文本编辑器，把下面的代码粘贴进去。注意将文件保存为 Employee.java。
        Employee类有四个成员变量：name、age、designation和salary。该类显式声明了一个构造方法，该方法只有一个参数。
        Employee.java 文件代码：
        import java.io.*;

        public class Employee{
           String name;
           int age;
           String designation;
           double salary;
           // Employee 类的构造器
           public Employee(String name){
              this.name = name;
           }
           // 设置age的值
           public void empAge(int empAge){
              age =  empAge;
           }
           /* 设置designation的值*/
           public void empDesignation(String empDesig){
              designation = empDesig;
           }
           /* 设置salary的值*/
           public void empSalary(double empSalary){
              salary = empSalary;
           }
           /* 打印信息 */
           public void printEmployee(){
              System.out.println("名字:"+ name );
              System.out.println("年龄:" + age );
              System.out.println("职位:" + designation );
              System.out.println("薪水:" + salary);
           }
        }
        程序都是从main方法开始执行。为了能运行这个程序，必须包含main方法并且创建一个实例对象。
        下面给出EmployeeTest类，该类实例化2个 Employee 类的实例，并调用方法设置变量的值。
        将下面的代码保存在 EmployeeTest.java文件中。
        EmployeeTest.java 文件代码：
        import java.io.*;
        public class EmployeeTest{

           public static void main(String args[]){
              /* 使用构造器创建两个对象 */
              Employee empOne = new Employee("RUNOOB1");
              Employee empTwo = new Employee("RUNOOB2");

              // 调用这两个对象的成员方法
              empOne.empAge(26);
              empOne.empDesignation("高级程序员");
              empOne.empSalary(1000);
              empOne.printEmployee();

              empTwo.empAge(21);
              empTwo.empDesignation("菜鸟程序员");
              empTwo.empSalary(500);
              empTwo.printEmployee();
           }
        }
        编译这两个文件并且运行 EmployeeTest 类，可以看到如下结果：
        $ javac EmployeeTest.java
        $ java EmployeeTest
        名字:RUNOOB1
        年龄:26
        职位:高级程序员
        薪水:1000.0
        名字:RUNOOB2
        年龄:21
        职位:菜鸟程序员
        薪水:500.0


##三、Java基本数据类型
    1.Java 基本数据类型
        ·变量就是申请内存来存储值。也就是说，当创建变量的时候，需要在内存中申请空间。
        ·内存管理系统根据变量的类型为变量分配存储空间，分配的空间只能用来储存该类型数据。
                CODE:             MEMORY:
            int x = 7;          x       y
            int y = 10;         7       10
        ·因此，通过定义不同类型的变量，可以在内存中储存整数、小数或者字符。
        ·Java 的两大数据类型:
         ·内置数据类型
         ·引用数据类型

    2.内置数据类型
        Java语言提供了八种基本类型。六种数字类型（四个整数型，两个浮点型），一种字符类型，还有一种布尔型。
        (1)byte：
        byte 数据类型是8位、有符号的，以二进制补码表示的整数；
        最小值是 -128（-2^7）；
        最大值是 127（2^7-1）；
        默认值是 0；
        byte 类型用在大型数组中节约空间，主要代替整数，因为 byte 变量占用的空间只有 int 类型的四分之一；
        例子：byte a = 100，byte b = -50。

        (2)short：
        short 数据类型是 16 位、有符号的以二进制补码表示的整数
        最小值是 -32768（-2^15）；
        最大值是 32767（2^15 - 1）；
        Short 数据类型也可以像 byte 那样节省空间。一个short变量是int型变量所占空间的二分之一；
        默认值是 0；
        例子：short s = 1000，short r = -20000。

        (3)int：
        int 数据类型是32位、有符号的以二进制补码表示的整数；
        最小值是 -2,147,483,648（-2^31）；
        最大值是 2,147,483,647（2^31 - 1）；
        一般地整型变量默认为 int 类型；
        默认值是 0 ；
        例子：int a = 100000, int b = -200000。

        (4)long：
        long 数据类型是 64 位、有符号的以二进制补码表示的整数；
        最小值是 -9,223,372,036,854,775,808（-2^63）；
        最大值是 9,223,372,036,854,775,807（2^63 -1）；
        这种类型主要使用在需要比较大整数的系统上；
        默认值是 0L；
        例子： long a = 100000L，Long b = -200000L。
        "L"理论上不分大小写，但是若写成"l"容易与数字"1"混淆，不容易分辩。所以最好大写。

        (5)float：
        float 数据类型是单精度、32位、符合IEEE 754标准的浮点数；
        float 在储存大型浮点数组的时候可节省内存空间；
        默认值是 0.0f；
        浮点数不能用来表示精确的值，如货币；
        例子：float f1 = 234.5f。

        (6)double：
        double 数据类型是双精度、64 位、符合IEEE 754标准的浮点数；
        浮点数的默认类型为double类型；
        double类型同样不能表示精确的值，如货币；
        默认值是 0.0d；
        例子：double d1 = 123.4。

        (7)boolean：
        boolean数据类型表示一位的信息；
        只有两个取值：true 和 false；
        这种类型只作为一种标志来记录 true/false 情况；
        默认值是 false；
        例子：boolean one = true。

        (8)char：
        char类型是一个单一的 16 位 Unicode 字符；
        最小值是 \u0000（即为0）；
        最大值是 \uffff（即为65,535）；
        char 数据类型可以储存任何字符；
        例子：char letter = 'A';。


    3.实例
        对于数值类型的基本类型的取值范围，我们无需强制去记忆，因为它们的值都已经以常量的形式定义在对应的包装类中了。请看下面的例子：
        实例
        public class PrimitiveTypeTest {
            public static void main(String[] args) {
                // byte
                System.out.println("基本类型：byte 二进制位数：" + Byte.SIZE);
                System.out.println("包装类：java.lang.Byte");
                System.out.println("最小值：Byte.MIN_VALUE=" + Byte.MIN_VALUE);
                System.out.println("最大值：Byte.MAX_VALUE=" + Byte.MAX_VALUE);
                System.out.println();

                // short
                System.out.println("基本类型：short 二进制位数：" + Short.SIZE);
                System.out.println("包装类：java.lang.Short");
                System.out.println("最小值：Short.MIN_VALUE=" + Short.MIN_VALUE);
                System.out.println("最大值：Short.MAX_VALUE=" + Short.MAX_VALUE);
                System.out.println();

                // int
                System.out.println("基本类型：int 二进制位数：" + Integer.SIZE);
                System.out.println("包装类：java.lang.Integer");
                System.out.println("最小值：Integer.MIN_VALUE=" + Integer.MIN_VALUE);
                System.out.println("最大值：Integer.MAX_VALUE=" + Integer.MAX_VALUE);
                System.out.println();

                // long
                System.out.println("基本类型：long 二进制位数：" + Long.SIZE);
                System.out.println("包装类：java.lang.Long");
                System.out.println("最小值：Long.MIN_VALUE=" + Long.MIN_VALUE);
                System.out.println("最大值：Long.MAX_VALUE=" + Long.MAX_VALUE);
                System.out.println();

                // float
                System.out.println("基本类型：float 二进制位数：" + Float.SIZE);
                System.out.println("包装类：java.lang.Float");
                System.out.println("最小值：Float.MIN_VALUE=" + Float.MIN_VALUE);
                System.out.println("最大值：Float.MAX_VALUE=" + Float.MAX_VALUE);
                System.out.println();

                // double
                System.out.println("基本类型：double 二进制位数：" + Double.SIZE);
                System.out.println("包装类：java.lang.Double");
                System.out.println("最小值：Double.MIN_VALUE=" + Double.MIN_VALUE);
                System.out.println("最大值：Double.MAX_VALUE=" + Double.MAX_VALUE);
                System.out.println();

                // char
                System.out.println("基本类型：char 二进制位数：" + Character.SIZE);
                System.out.println("包装类：java.lang.Character");
                // 以数值形式而不是字符形式将Character.MIN_VALUE输出到控制台
                System.out.println("最小值：Character.MIN_VALUE="
                        + (int) Character.MIN_VALUE);
                // 以数值形式而不是字符形式将Character.MAX_VALUE输出到控制台
                System.out.println("最大值：Character.MAX_VALUE="
                        + (int) Character.MAX_VALUE);
            }
        }

        运行实例 »
        编译以上代码输出结果如下所示：
        基本类型：byte 二进制位数：8
        包装类：java.lang.Byte
        最小值：Byte.MIN_VALUE=-128
        最大值：Byte.MAX_VALUE=127

        基本类型：short 二进制位数：16
        包装类：java.lang.Short
        最小值：Short.MIN_VALUE=-32768
        最大值：Short.MAX_VALUE=32767

        基本类型：int 二进制位数：32
        包装类：java.lang.Integer
        最小值：Integer.MIN_VALUE=-2147483648
        最大值：Integer.MAX_VALUE=2147483647

        基本类型：long 二进制位数：64
        包装类：java.lang.Long
        最小值：Long.MIN_VALUE=-9223372036854775808
        最大值：Long.MAX_VALUE=9223372036854775807

        基本类型：float 二进制位数：32
        包装类：java.lang.Float
        最小值：Float.MIN_VALUE=1.4E-45
        最大值：Float.MAX_VALUE=3.4028235E38

        基本类型：double 二进制位数：64
        包装类：java.lang.Double
        最小值：Double.MIN_VALUE=4.9E-324
        最大值：Double.MAX_VALUE=1.7976931348623157E308

        基本类型：char 二进制位数：16
        包装类：java.lang.Character
        最小值：Character.MIN_VALUE=0
        最大值：Character.MAX_VALUE=65535

        Float和Double的最小值和最大值都是以科学记数法的形式输出的，结尾的"E+数字"表示E之前的数字要乘以10的多少次方。
        比如3.14E3就是3.14 × 103 =3140，3.14E-3 就是 3.14 x 10-3 =0.00314。
        实际上，JAVA中还存在另外一种基本类型void，它也有对应的包装类 java.lang.Void，不过我们无法直接对它们进行操作。


    4.引用类型
        ·在Java中，引用类型的变量非常类似于C/C++的指针。引用类型指向一个对象，指向对象的变量是引用变量。
        这些变量在声明时被指定为一个特定的类型，比如 Employee、Puppy 等。变量一旦声明后，类型就不能被改变了。
        ·对象、数组都是引用数据类型。
        ·所有引用类型的默认值都是null。
        ·一个引用变量可以用来引用任何与之兼容的类型。
        例子：Site site = new Site("Runoob")。

    5.Java 常量
        常量在程序运行时是不能被修改的。
        在 Java 中使用 final 关键字来修饰常量，声明方式和变量类似：
        final double PI = 3.1415927;
        虽然常量名也可以用小写，但为了便于识别，通常使用大写字母表示常量。

        字面量可以赋给任何内置类型的变量。例如：
        byte a = 68;
        char a = 'A'
        byte、int、long、和short都可以用十进制、16进制以及8进制的方式来表示。
        当使用常量的时候，前缀 0 表示 8 进制，而前缀 0x 代表 16 进制, 例如：
        int decimal = 100;
        int octal = 0144;
        int hexa =  0x64;

        和其他语言一样，Java的字符串常量也是包含在两个引号之间的字符序列。下面是字符串型字面量的例子：
        "Hello World"
        "two\nlines"
        "\"This is in quotes\""

        字符串常量和字符常量都可以包含任何Unicode字符。例如：
        char a = '\u0001';
        String a = "\u0001";

        Java语言支持一些特殊的转义字符序列。
        符号  字符含义
        \n  换行 (0x0a)
        \r  回车 (0x0d)
        \f  换页符(0x0c)
        \b  退格 (0x08)
        \0  空字符 (0x20)
        \s  字符串
        \t  制表符
        \“  双引号
        \‘  单引号
        \\  反斜杠
        \ddd    八进制字符 (ddd)
        \uxxxx  16进制Unicode字符 (xxxx)

    6.自动类型转换
        整型、实型（常量）、字符型数据可以混合运算。运算中，不同类型的数据先转化为同一类型，然后进行运算。
        转换从低级到高级。
        低  ------------------------------------>  高

        byte,short,char—> int —> long—> float —> double

        数据类型转换必须满足如下规则：
        1. 不能对boolean类型进行类型转换。
        2. 不能把对象类型转换成不相关类的对象。
        3. 在把容量大的类型转换为容量小的类型时必须使用强制类型转换。
        4. 转换过程中可能导致溢出或损失精度，例如：
        int i =128;
        byte b = (byte)i;
        因为 byte 类型是 8 位，最大值为127，所以当 int 强制转换为 byte 类型时，值 128 时候就会导致溢出。
        5. 浮点数到整数的转换是通过舍弃小数得到，而不是四舍五入，例如：
        (int)23.7 == 23;
        (int)-45.89f == -45

        自动类型转换
            必须满足转换前的数据类型的位数要低于转换后的数据类型，例如: short数据类型的位数为16位，
            就可以自动转换位数为32的int类型，同样float数据类型的位数为32，可以自动转换为64位的double类型。

            实例
            public class ZiDongLeiZhuan{
                    public static void main(String[] args){
                        char c1='a';//定义一个char类型
                        int i1 = c1;//char自动类型转换为int
                        System.out.println("char自动类型转换为int后的值等于"+i1);
                        char c2 = 'A';//定义一个char类型
                        int i2 = c2+1;//char 类型和 int 类型计算
                        System.out.println("char类型和int计算后的值等于"+i2);
                    }
            }
            运行结果为:
            char自动类型转换为int后的值等于97
            char类型和int计算后的值等于66
            解析：c1的值为字符'a',查ascii码表可知对应的int类型值为97，'A'对应值为65，所以i2=65+1=66。

        强制类型转换

            1. 条件是转换的数据类型必须是兼容的。
            2. 格式：(type)value type是要强制类型转换后的数据类型 实例：
            实例
            public class QiangZhiZhuanHuan{
                public static void main(String[] args){
                    int i1 = 123;
                    byte b = (byte)i1;//强制类型转换为byte
                    System.out.println("int强制类型转换为byte后的值等于"+b);
                }
            }
            运行结果：
            int强制类型转换为byte后的值等于123

        隐含强制类型转换
            1. 整数的默认类型是 int。
            2. 浮点型不存在这种情况，因为在定义 float 类型时必须在数字后面跟上 F 或者 f。
##四、Java变量类型
        1.
            在Java中语言中，所有的变量在使用前必须声明。申明白能量的基本格式如下：
                type identifier [ = value ][, identifier [= value] ...];
            格式说明：type为Java数据类型。indentifier是变量名。可以使用逗号隔开来声明多个同类型变量。

            一下列出了一些变量的声明实例。有些包含了初始化过程。
                int a, b, c;    //声明三个int型整数
                int d = 3, e = 4, f = 5; //声明三个int型整数并初始化
                byte 在= 22; //声明并初始化z
                String s = "ssssssssss"； //声明并初始化字符串s
                double pi = 3.14159; //声明双精度浮点型变量 pi
                char x = 'x'  //声明变量x的值是字符'x'

            Java语言支持的变量类型：
                类变量：独立于方法之外的变量，用static修饰
                实例变量：独立于方法之外的变量，不过没有static修饰
                局部变量：类的方法变量

            实例：
            public class Variable{
                static int allClicks=0;    // 类变量

                String str="hello world";  // 实例变量

                public void method(){

                    int i =0;  // 局部变量

                }
            }

        2.Java局部变量
            ·局部变量声明在方法、构造方法或者语句块中；
            ·局部变量在方法、构造方法、或者语句块中被执行的时候创建，当它们使用完成后，变量将会被销毁。
            ·访问修饰符不能用于局部变量
            ·局部变量只在声明它的方法、构造方法或者语句块中可见。
            ·局部变量是在栈上分配的。
            ·局部变量没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。

            实例 1：
                在以下实例中age是一个局部变量。定义在pupAge()方法中，它的作用域就限制在这个方法中。
                    package com.runoob.test;

                    public class Test{
                       public void pupAge(){
                          int age = 0;
                          age = age + 7;
                          System.out.println("小狗的年龄是: " + age);
                       }

                       public static void main(String[] args){
                          Test test = new Test();
                          test.pupAge();
                       }
                    }

                    以上实例编译运行结果如下:
                    小狗的年龄是: 7

            实例 2：
                在下面的例子中 age 变量没有初始化，所以在编译时会出错：
                    package com.runoob.test;

                    public class Test{
                       public void pupAge(){
                          int age;
                          age = age + 7;
                          System.out.println("小狗的年龄是 : " + age);
                       }

                       public static void main(String[] args){
                          Test test = new Test();
                          test.pupAge();
                       }
                    }
                    以上实例编译运行结果如下:
                    Test.java:4:variable number might not have been initialized
                    age = age + 7;
                             ^
                    1 error

            3.实例变量
                ·实例变量声明在一个类中，但在方法、构造方法和语句块之外。
                ·当一个对象被实例化之后，每个实例变量的值就跟着确定。
                ·实例变量在对象创建的时候创建，在对象被销毁的时候销毁。
                ·实例变量的值应该至少被一个方法、构造方法或者语句块引用，使得外部能够通过这些方式获取实例变量信息；
                ·实例变量可以声明在使用前或者使用后；
                ·访问修饰符可以修饰实例变量；
                ·实例变量对于类中的方法、构造方法或者语句块是可见的。一般情况下应该把实例变量设为私有。通过使用访问修饰符可以使实例变量对子类可见；
                ·实例变量具有默认值。数值型变量的默认值是0，布尔型变量的默认值是false，引用类型变量的默认值是null。变量的值可以在声明时指定，也可以在构造方法中指定；
                ·实例变量可以直接通过变量名访问。但在静态方法以及其他类中，就应该使用完全限定名：ObejectReference.VariableName。

                实例
                    Employee.java 文件代码：
                    import java.io.*;
                    public class Employee{
                       // 这个实例变量对子类可见
                       public String name;
                       // 私有变量，仅在该类可见
                       private double salary;
                       //在构造器中对name赋值
                       public Employee (String empName){
                          name = empName;
                       }
                       //设定salary的值
                       public void setSalary(double empSal){
                          salary = empSal;
                       }
                       // 打印信息
                       public void printEmp(){
                          System.out.println("名字 : " + name );
                          System.out.println("薪水 : " + salary);
                       }

                       public static void main(String[] args){
                          Employee empOne = new Employee("RUNOOB");
                          empOne.setSalary(1000);
                          empOne.printEmp();
                       }
                    }
                    以上实例编译运行结果如下:
                    $ javac Employee.java
                    $ java Employee
                    名字 : RUNOOB
                    薪水 : 1000.0

            4. 类变量（静态变量）
                ·类变量也称为静态变量，在类中以static关键字声明，但必须在方法构造方法和语句块之外。
                ·无论一个类创建了多少个对象，类只拥有类变量的一份拷贝。
                ·静态变量除了被声明为常量外很少使用。常量是指声明为public/private，final和static类型的变量。常量初始化后不可改变。
                ·静态变量储存在静态存储区。经常被声明为常量，很少单独使用static声明变量。
                ·静态变量在程序开始时创建，在程序结束时销毁。
                ·与实例变量具有相似的可见性。但为了对类的使用者可见，大多数静态变量声明为public类型。
                ·默认值和实例变量相似。数值型变量默认值是0，布尔型默认值是false，引用类型默认值是null。变量的值可以在声明的时候指定，也可以在构造方法中指定。此外，静态变量还可以在静态语句块中初始化。
                ·静态变量可以通过：ClassName.VariableName的方式访问。
                ·类变量被声明为public static final类型时，类变量名称一般建议使用大写字母。如果静态变量不是public和final类型，其命名方式与实例变量以及局部变量的命名方式一致。

                实例：
                    Employee.java 文件代码：
                    import java.io.*;

                    public class Employee {
                        //salary是静态的私有变量
                        private static double salary;
                        // DEPARTMENT是一个常量
                        public static final String DEPARTMENT = "开发人员";
                        public static void main(String[] args){
                        salary = 10000;
                            System.out.println(DEPARTMENT+"平均工资:"+salary);
                        }
                    }
                    以上实例编译运行结果如下:
                    开发人员平均工资:10000.0

##五、Java修饰符
            1.Java提供了很多修饰符，主要分为以下两类：
                ·访问修饰符
                ·非访问修饰符
                修饰符用来定义类、方法或者变量，通常放在语句的最前端。

                例子：
                    public class className {
                       // ...
                    }
                    private boolean myFlag;
                    static final double weeks = 9.5;
                    protected static final int BOXWIDTH = 42;
                    public static void main(String[] arguments) {
                       // 方法体
                    }

            2.访问控制修饰符
                （1）Java中，可以使用访问控制修饰符来保护对类、变量、方法和构造方法的访问。Java支持四种不同的访问权限。
                    ·default（缺省，什么也不写）：在同一包内，不使用任何修饰符。使用对象：类、接口、变量、方法。
                    ·private：在同一类内可见。使用对象：变量、方法。注意：不能修饰类（外部类）
                    ·public：对所有类可见。使用对象：类、接口、变量、方法。
                    ·protected：对同一包内的类和子类可见。使用对象：变量、方法。注意：不能修饰类（外部类）
                    我们可以可以通过以下表来说明访问权限：

                                    访问控制
                        修饰符         当前类 同一包内    子孙类 其他包 其他包子孙类
                        public          Y   Y   Y   Y       Y
                        protected       Y   Y   Y   N       Y/N（说明）
                        default         Y   Y   N   N       N
                        private         Y   N   N   N       N

                （2）默认访问修饰符-不使用任何关键字
                        使用默认方法访问修饰符声明的变量和方法，对同一包内的类是可见的。接口的变量都隐式声明为public static final ，而接口里
                        的方法默认情况下访问权限是public。

                    如下例所示，变量和方法的声明可以不使用任何修饰符。
                        实例
                        String version = "1.5.1";
                        boolean processOrder() {
                           return true;
                        }

                （3）私有访问修饰符-private
                    私有访问修饰符是最严格的访问级别，所有被声明为private的方法、变量和构造方法只能被所属类访问，并且类和接口不能声明为private。
                    声明为私有访问类型的变量只能通过类中公共的getter方法被外部类访问。
                    private访问修饰符的使用主要用来隐藏类的实现细节和保护类的数据。

                    下面的类使用了私有访问修饰符：
                    public class Logger {
                       private String format;
                       public String getFormat() {
                          return this.format;
                       }
                       public void setFormat(String format) {
                          this.format = format;
                       }
                    }
                    实例中，Logger 类中的 format 变量为私有变量，所以其他类不能直接得到和设置该变量的值。为了使其他类能够操作该变量，
                    定义了两个 public 方法：getFormat() （返回 format的值）和 setFormat(String)（设置 format 的值）

                （4）公有访问修饰符-public
                    被声明为 public 的类、方法、构造方法和接口能够被任何其他类访问。
                    如果几个相互访问的 public 类分布在不同的包中，则需要导入相应 public 类所在的包。由于类的继承性，类所有的公有方法和变量都能被其子类继承。

                    以下函数使用了公有访问控制：
                    public static void main(String[] arguments) {
                       // ...
                    }
                    Java 程序的 main() 方法必须设置成公有的，否则，Java 解释器将不能运行该类。

                （5）受保护的访问修饰符-protected
                    protected 需要从以下两个点来分析说明：
                        ·子类与基类在同一包中：被声明为 protected 的变量、方法和构造器能被同一个包中的任何其他类访问；
                        ·子类与基类不在同一包中：那么在子类中，子类实例可以访问其从基类继承而来的 protected 方法，而不能访问基类实例的protected方法。

                    protected 访问修饰符不能修饰类和接口，方法和成员变量能够声明为 protected，但是接口的成员变量和成员方法不能声明为 protected。
                    子类能访问 protected 修饰符声明的方法和变量，这样就能保护不相关的类使用这些方法和变量。

                    下面的父类使用了 protected 访问修饰符，子类重写了父类的 openSpeaker() 方法。
                    class AudioPlayer {
                       protected boolean openSpeaker(Speaker sp) {
                          // 实现细节
                       }
                    }

                    class StreamingAudioPlayer extends AudioPlayer {
                       protected boolean openSpeaker(Speaker sp) {
                          // 实现细节
                       }
                    }
                    如果把 openSpeaker() 方法声明为 private，那么除了 AudioPlayer 之外的类将不能访问该方法。
                    如果把 openSpeaker() 声明为 public，那么所有的类都能够访问该方法。
                    如果我们只想让该方法对其所在类的子类可见，则将该方法声明为 protected。

            3.非访问修饰符
                (1).为了实现一些其他的功能，Java 也提供了许多非访问修饰符。
                    ·static 修饰符，用来修饰类方法和类变量。
                    ·final 修饰符，用来修饰类、方法和变量，final 修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。
                    ·abstract 修饰符，用来创建抽象类和抽象方法。
                    ·synchronized 和 volatile 修饰符，主要用于线程的编程。
                (2).static 修饰符
                    静态变量：
                        ·static 关键字用来声明独立于对象的静态变量，无论一个类实例化多少对象，它的静态变量只有一份拷贝。 静态变量也被称为类变量。局部变量不能被声明为 static 变量。
                    静态方法：
                        ·static 关键字用来声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法从参数列表得到数据，然后计算这些数据。
                        ·对类变量和方法的访问可以直接使用 classname.variablename 和 classname.methodname 的方式访问。

                    如下例所示，static修饰符用来创建类方法和类变量。
                    public class InstanceCounter {
                       private static int numInstances = 0;
                       protected static int getCount() {
                          return numInstances;
                       }

                       private static void addInstance() {
                          numInstances++;
                       }

                       InstanceCounter() {
                          InstanceCounter.addInstance();
                       }

                       public static void main(String[] arguments) {
                          System.out.println("Starting with " +
                          InstanceCounter.getCount() + " instances");
                          for (int i = 0; i < 500; ++i){
                             new InstanceCounter();
                              }
                          System.out.println("Created " +
                          InstanceCounter.getCount() + " instances");
                       }
                    }

                    以上实例运行编辑结果如下:
                    Starting with 0 instances
                    Created 500 instances

                (3)final 修饰符
                    ·final 变量：
                    ·final 变量能被显式地初始化并且只能初始化一次。被声明为 final 的对象的引用不能指向不同的对象。但是 final 对象里的数据可以被改变。也就是说 final 对象的引用不能改变，但是里面的值可以改变。
                    ·final 修饰符通常和 static 修饰符一起使用来创建类常量。

                    实例
                    public class Test{
                      final int value = 10;
                      // 下面是声明常量的实例
                      public static final int BOXWIDTH = 6;
                      static final String TITLE = "Manager";

                      public void changeValue(){
                         value = 12; //将输出一个错误
                      }
                    }
                    ·final 方法
                        类中的 final 方法可以被子类继承，但是不能被子类修改。
                        声明 final 方法的主要目的是防止该方法的内容被修改。
                        如下所示，使用 final 修饰符声明方法。
                        public class Test{
                            public final void changeName(){
                               // 方法体
                            }
                        }
                    ·final 类
                        final 类不能被继承，没有类能够继承 final 类的任何特性。
                        实例
                        public final class Test {
                           // 类体
                        }

                (4)abstract 修饰符
                    抽象类：
                        抽象类不能用来实例化对象，声明抽象类的唯一目的是为了将来对该类进行扩充。
                        一个类不能同时被 abstract 和 final 修饰。如果一个类包含抽象方法，那么该类一定要声明为抽象类，否则将出现编译错误。
                        抽象类可以包含抽象方法和非抽象方法。

                    实例
                    abstract class Caravan{
                       private double price;
                       private String model;
                       private String year;
                       public abstract void goFast(); //抽象方法
                       public abstract void changeColor();
                    }
                    ·抽象方法
                        抽象方法是一种没有任何实现的方法，该方法的的具体实现由子类提供。
                        抽象方法不能被声明成 final 和 static。
                        任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类。
                        如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法。
                        抽象方法的声明以分号结尾，例如：public abstract sample();。

                    实例
                    public abstract class SuperClass{
                        abstract void m(); //抽象方法
                    }

                    class SubClass extends SuperClass{
                         //实现抽象方法
                          void m(){
                              .........
                          }
                    }

                （5）synchronized 修饰符
                synchronized 关键字声明的方法同一时间只能被一个线程访问。synchronized 修饰符可以应用于四个访问修饰符。
                实例
                public synchronized void showDetails(){
                .......
                }
                (6)ransient 修饰符
                序列化的对象包含被 transient 修饰的实例变量时，java 虚拟机(JVM)跳过该特定的变量。
                该修饰符包含在定义变量的语句中，用来预处理类和变量的数据类型。
                实例
                public transient int limit = 55;   // 不会持久化
                public int b; // 持久化
                (7)volatile 修饰符
                volatile 修饰的成员变量在每次被线程访问时，都强制从共享内存中重新读取该成员变量的值。而且，当成员变量发生变化时，会强制线程将变化值回写到共享内存。这样在任何时刻，两个不同的线程总是看到某个成员变量的同一个值。
                一个 volatile 对象引用可能是 null。

                实例
                public class MyRunnable implements Runnable
                {
                    private volatile boolean active;
                    public void run()
                    {
                        active = true;
                        while (active) // 第一行
                        {
                            // 代码
                        }
                    }
                    public void stop()
                    {
                        active = false; // 第二行
                    }
                }
                通常情况下，在一个线程调用 run() 方法（在 Runnable 开启的线程），在另一个线程调用 stop() 方法。 如果 第一行 中缓冲区的 active 值被使用，那么在 第二行 的 active 值为 false 时循环不会停止。
                但是以上代码中我们使用了 volatile 修饰 active，所以该循环会停止。


