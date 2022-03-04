# lg_stage01_module02
阶段1模块2：Java面向对象编程

## 一. 类和对象
### 对象和面向对象的概念
* 万物皆对象
* 属性和行为
* 面向对象编程：先以面向对象的思想进行分析，然后使用面向对象的编程语言进行表达的过程。
* 面向对象特性：封装、继承、多态

### 类和对象的概念
* 对象主要指现实生活中客观存在的实体，在Java中对象体现为内存空间中的一块存储区域
* 类：对具有相同特征和行为的多个对象共性的抽象描述。Java中体现为引用数据类型，包含了描述特征/属性的成员变量以及描述行为的成员方法。
* 类是用构建对象的模板，对象的数据结构由定义它的类来决定。


###  类的定义
### 对象的创建
* 当一个类定义完毕后，可以使用new关键字来创建该类的对象，这个过程叫类的实例化。
* 创建对象的本质就是在内存空间的堆区申请一块存储区域用于存放该对象独有特征信息。

###  引用的定义
基本概念
* 使用引用数据类型定义的变量叫做引用型变量
* 引用变量主要用于记录对象在堆区中内存地址信息，便于下次访问

###  成员变量的初始值
对象创建后，其成员变量可以按照默的方式初始化，
数值类型：byte、short、int、long、float、double、char：0  
boolean类型：false  
引用类型：null  

###  Person类代码执行流程和内存分析

栈区、堆区、方法区

###  成员方法的定义

### 成员方法体详解
* 成员方法体主要用于编写描述该方法功能的语句块
* 成员方法可以实现代码的重用，简化代码

###  可变长参数
* 返回值 函数名(参数类型... 参数名)
* 一个方法的形参列表最多只能声明一个可变长形参，并且要放到参数列表末尾

### 参数传递注意事项：
* 基本数据类型的变量作为方法的参数传递时，形参变量数值的改变通常不会影响到实参变量的数值，因为两个变量有各自独立的内存空间（形参传变量的副本，传递值）。
* 引用数据类型传地址

### 内存结构之栈区
* 栈用于存放程序运行过程当中所有的局部变量。一个运行的Java程序从开始到结束会有多次方法的调用。
* JVM会为每一个方法调用在栈中分配一个对应的空间，这个空间称为该方法的栈帧。一个栈帧对应一个正在调用的方法，栈帧存储了该方法的参数、局部变量等数据
* 当某一个方法调用完成后，其对应的栈帧将被清除。

## 二、方法和封装
### 1. 构造方法
* 默认构造方法：类中没有定义构造方法，编译器会自动添加一个无参构造方法，当定义有参构造方法时，编译器不再提供默认构造方法
* 构造方法的作用：使用new关键字创建对象时会自动调用构造方法实现成员变量的初始化工作。

### 2. 重载
* 重载的体现形式：参数个数不同、参数类型不同、参数顺序不同，与返回值类型和形参变量名无关，但建议返回值类型最好相同。
* 重载的实际意义：
    只需记住一个方法名就可以调用各种不同的版本，来实现各种不同的功能
    
### 3. this关键字
* 在构造方法中，this代表当前正在构造的对象
* 在成员方法中，this代表当前正在调用的对象
* this关键字本质上就是当前类类型的引用变量

### 4. this关键字使用方式

### 5. 递归
* 使用递归必须有递归的规律以及退出条件
* 使用递归必须使问题简单化而不是复杂化
* 若递归影响到程序执行性能，则使用递推取代之


### 6. 封装的概念
* 封装：对成员变量进行密封包装，隐藏成员变量的细节以及保证成员变量数值的合理性。
### 7. 封装实现的流程
    1.私有化成员变量，使用private修饰
    2.提供公有（public）的get和set方法，并在方法体中进行合理值的判断
    3.在构造方法中调用set方法进行合理值的判断


## 三、static关键字和继承
1. 基本概念
    使用static关键字修饰成员变量表示静态含义，此时成员变量由对象层级提升为类层级，也就是整个类只有一份并被所有对象共享，
    该成员变量随着类的加载准备就绪，与是否创建对象无关。
2. 使用方式
    * 在非静态方法中既能访问非静态成员，又能访问静态成员。
    * 在静态方法中只能访问静态成员，不能访问非静态成员。
3. 构造块和静态代码块
    * 构造块：在类体中直接使用{}括起来的代码块。
    * 每创建一个对象都会执行一次构造块。
    * 静态代码块：用static修饰的构造块
4. 单例设计模式
    * 实现流程  
    (1) 私有化构造方法，使用private关键字修饰  
    (2) 声明本类类型的引用指向本类类型的对象，并使用private static关键字共同修饰  
    (3) 提供公有的get方法负责将对象返回出去，并使用public static修饰
5. 继承的概念
    * 当多个类之间有相同的特征和行为时，可以将相同的内容提取处理组成一个公共类，让多个类吸收公共类中已有特征和行为，
    而在多个类型只需要编写自己独有特征和行为的机制，叫做继承。
    * Java中使用extends（扩展）关键字表示继承关系
    * 使用继承提高了代码的复用性、可维护性及扩展性，是多态的前提
6. 继承的特点
    * 子类不能继承父类的构造方法和私有方法，但私有成员变量可以被继承，只是不能直接访问
    * 无论使用何种方式构造子类的对象时，都会自动调用父类的无参构造方法，来初始化从父类中继承的成员变量，
    相当于他在构造方法的第一行增加super()的效果。Call to 'super()' must be first statement in constructor body
    * 使用继承必须满足逻辑关系：子类is a父类，不能滥用继承
    * Java只支持单继承，不支持多继承
7. 方法重写的概念
    * 从父类中继承下来的方法不满足子类需求时，就需要在子类中重写一个和父类一样的方法来覆盖从父类中继承下来的版本，
    该方式就叫做方法的重新（Override）。
8. 方法重写的原则
    * 要求方法名相同、参数列表相同以及返回值类型相同，从Java 5开始，允许返回子类类型
    * 要求方法的访问权限不能变小，可以相同或者变大
    * 要求方法不能抛出更大的异常（异常机制）
9. 构造块与静态代码块执行顺序
    * 父类静态代码块
    * 子类静态代码块
    * 父类构造块
    * 父类构造方法
    * 子类构造块
    * 子类构造方法体
    
10. 常用的访问控制符

| 修饰符 | 本类 | 同一个包中的类 | 子类 | 其他类 |
| ---- | ---- | ---- | ---- | ---- |
| public | 可以访问 | 可以访问 | 可以访问 | 可以访问 |
| protected | 可以访问 | 可以访问 | 可以访问 | 不能访问 |
| 默认 | 可以访问 | 可以访问 | 不能访问 | 不能访问 |
| private | 可以访问 | 不能访问 | 不能访问 | 不能访问 |

注意事项：
* public修饰的成员可以在任意位置使用
* private修饰的成员只能在本类内部使用
* 通常情况下，成员方法都使用public关键字修饰，成员变量都使用private关键字修饰
    
11. package包的定义
    * 在定义一个类时，除了定义类的名称一般还要指定一个包名，格式如下：   
    package 包名;  
    package 包名1.包名2.包名3...包名n;  
    * 为了实现项目管理、解决命名冲突以及权限控制的效果
    
12. 定义包的规范

13. 包的导入
    * 使用关键字import导入
    * 使用import关键字导入静态成员，java5开始支持

14. final修饰类和方法的作用  
    14.1 基本概念    
    * final本意为“最终的、不可改变的”，可以修饰类、成员方法及成员变量
    
    14.2 使用方式
    * final关键字修饰体现在该类不能被继承
        - 主要用于防止滥用继承
    * final关键字修饰成员方法体现在该方法不能被重写但可以被继承 
        - 主要用于防止不经意间造成重写  
    * final关键字修饰成员变量体现在该变量必须初始化且不能改变  
        - 主要用于防止不经意间造成改变
15. 常量
    * 常量使用public static final关键字共同修饰
     

## 四、多态和特殊类

1. 多态的概念
    * 多态主要指同一种事务表现出来的多种形态

2. 多态的语法格式
    * 父类类型 引用变量名 = new 子类类型();
    
3. 多态的特点
    * 当父类类型的引用指向子类类型对象时，父类类型的引用可以直接调用父类独有的方法。
    * 当父类类型的引用指向子类类型对象时，父类类型的引用不可以直接调用子类类独有的方法。
    * 对于父子类都有的非静态方法，编译阶段调用父类版本，运行阶段调用子类重写版本（动态绑定）
    * 对于父子类都有的静态方法来说，编译和运行阶段都调用父类版本

4. 引用数据类型之间的转换
    * 引用数据类型之间的转换方式有两种：自动类型转换和强制类型转换
    * 自动类型转换：小类型向大类型的转换，子类转为父类，也叫向上转型
    * 强制类型转换：大类型向小类型的转换，父类转为子类，向下转型
    * 引用数据类型的转换必须发生在父子类之间，否则编译报错
    * 若强转的目标类型并不是该引用真正指向的数据类型时则编译通过，运行阶段发生类型转换异常
    * 为了避免发生上述错误，应该在强转之前进行判断：  
        if(引用变量 instanceof 数据类型)  
        判断引用变量指向的对象是否为后面数据类型  

5. 多态的实际意义
    * 多态的实际意义在于屏蔽不同子类的差异性实现通过编程带来不同的效果。
  
6. 抽象方法的概念
    * 抽象方法主要指不能具体实现的方法，并且使用abstract关键字修饰，也就是没有方法体。
    * 具体格式：访问权限 abstract 返回值类型 方法名称(形参列表);

7. 抽象类的概念
    * 抽象类主要指不能具体实例化的类，并且使用abstract关键字修饰，也就是不能创建对象。

8. 抽象类和抽象方法的关系
    * 抽象类可以有成员变量、构造方法、成员方法；
    * 抽象类中可以没有抽象方法，也可以有抽象方法；
    * 拥有抽象方法的类必须是抽象类，因此真正意义上的抽象类应该是具有抽象方法，并且使用abstract关键字修饰的类。
   
9. 抽象类的实际意义
    * 抽象类的实际意义不在于创建对象而在于被继承。
    * 当一个类继承抽象类后必须重写抽象方法，否则该类也变成抽象类，也就是抽象类对子类具有强制性和规范性，因此叫做模版设计模式。

10. 开发经验分享
    * 开发中推荐使用多态格式，此时父类类型的引用直接调用的所有方法一定是父类中拥有的方法，若以后更换子类时，只需将new关键字后面的子类类型修改而其他地方无需改变就可以立即生效，从而提高代码可维护性和扩展性。
    * 该方式的缺点：父类引用不能直接调用子类独有的方法，若调用则需要强制类型转换。

11. 接口的基本概念
    * 接口就是一种比抽象类还抽象的类，体现在所有方法都为抽象方法。
    * 定义类的关键字是class，定义接口的关键字是interface。

12. 类和接口之间的关系
   
| 名称 | 关键字 | 关系 |
| ---- | ---- | ---- |
| 类和类之间的关系 | 使用extends关键字表达继承关系 | 支持单继承 |
| 类和接口之间的关系 | 使用implements关键字表达实现关系 | 支持多实现 |
| 接口和接口之间的关系 | 使用extends关键字表达继承关系 | 支持多继承 |

13. 抽象类和接口的主要区别
    * 定义抽象类的关键字是abstract class，定义接口的关键字是interface
    * 继承抽象类的关键字是extends，实现接口的关键字是implements
    * 继承抽象类支持单继承，实现接口支持多实现
    * 抽象类可以有构造方法，而接口不可用有构造方法
    * 抽象类中可以有成员变量，而接口中只可以有常量
    * 抽象类中可以有成员方法，接口中只可以有抽象方法
    * 抽象类中增加方法时子类可以不用重写，而接口中增加方法时实现类需要重写（Java8以前的版本）
    * Java8增加新特性，接口中允许出现非抽象方法和静态方法，但非抽象方法需要使用default关键字修饰
    * Java9开始增加新特性，接口中允许出现私有方法
    
## 五、特殊类 
1. 内部类的基本概念
    * 当一个类的定义出现在另一个类的类体中时，那么这个类叫做内部类（Inner），而这个内部类
    所在的类叫做外部类（Outer）。
    * 类中的内容：成员变量、成员方法、构造方法、静态成员、构造块和静态代码块、内部类。
    
2. 内部类的实际作用
    * 当一个类存在的价值仅仅是为某一个类单独服务时，那么就可以将这个类定义为所服务类中的内部类，这样可以隐藏该类实现细节并且可以方便
    访问外部类的私有成员，而不再需要提供公有的get和set方法。

3. 内部类的分类
    * 普通内部类：直接将一个类的定义放在另外一个类的类体中
    * 静态内部类：使用static关键字修饰的内部类，隶属于类层级
    * 局部内部类：直接将一个类的定义放在方法体的内部
    * 匿名内部类：没有名字的内部类
    
4. 普通（成员）内部类的格式

5. 普通内部类的使用方式
    * 普通内部类和普通类一样可以定义成员变量、成员方法以及构造方法等
    * 普通内部类和普通类一样可以使用final或者abstract关键字修饰
    * 普通内部类还可以使用private或者protected关键字进行修饰
    * 普通内部类需要使用外部类对象来创建对象
    * 如果内部类访问外部类中与本类内部同名的成员变量或方法时，需要使用this关键字
    
6. 静态内部类的格式

7. 静态内部类是使用方式
    * 静态内部类不能直接访问外部类的非静态成员
    * 静态内部类可以直接创建对象
    * 如果静态内部类访问外部类中与本类同名的成员变量或方法时，需要使用类名.的方式访问

8. 局部（方法）内部类的格式

9. 局部内部类的使用方式
    * 局部内部类只能在该方法的内部使用
    * 局部内部类可以在方法体内部直接创建对象
    * 局部内部类不能使用访问控制符和static关键字修饰
    * 局部内部类可以使用外部方法的局部变量，但必须是final的。
    由局部内部类和局部变量的生命周期不同所致

10. 回调模式的概念
    * 回调模式：如果一个方法的参数是接口类型，则在调用该方法时，需要创建并传递一个实现此接口类型的对象；
    而该方法运行时会调用到参数对象中所实现的方法（此接口中定义的）。

11. 开发经验
    当接口/类类型的引用作为方法的形参时，实参的传递方式有两种：
    1.  自定义类实现接口/继承类并重写方法，然后创建该类对象作为实参传递；
    2.  使用上述匿名内部类的语法格式得到接口/类类型的引用即可。

12. 匿名内部类的语法格式
    * 接口/父类型 引用变量名 = new 接口/父类型(){ 方法的重写 };

13. 枚举类型的基本概念
    * 在日常生活中一些事物的取值只有明确的几个固定值，此时描述这些事物的所有值
    都可以一一列举出来，而这个列举出来的类型就叫做枚举类型。
    
14. 枚举的定义
    * 使用public static final表示的常量描述较为繁琐，使用enum关键字来定义枚举类型取代常量。
    枚举类型是从Java5开始增加的一种引用数据类型。
    * 枚举值就是当前类的类型，也就是指向本类的对象，默认使用public static final关键字共同修饰，因此采用”枚举类型.“的调用方式
    * 枚举类可以定义构造方法，但构造方法的修饰符必须是private，默认也是私有的。
    
15. Enum类的概念和方法
    * 所有的枚举类都继承自java.lang.Enum类，常用方法:
    
    | 方法 | 描述 | 
    | ---- | ---- |
    | static T[] values() | 返回当前枚举类中所有对象 |
    | String toString() | 返回当前枚举类对象的名称 |
    | int ordinal() | 获取枚举对象在枚举类中的索引位置 |
    | static T valueOf(String str) | 将参数指定的字符串转为当前枚举类的对象 |
    | int compareTo(E o) | 比较两个枚举对象在定义时的顺序 |
    
16. 枚举类实现接口的方式
    * 枚举实现接口后需要重写抽象方法，而重写方法的方式有两种：
        1. 重写一个
        2. 每个对象都重写
   
