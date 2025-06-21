# 填空
1. 在面向对象中，类之间共享属性和操作的机制称为==继承==
2. 在继承关系中，子类会自动继承父类中的方法，但有时在子类中需要对继承的方法进行修改，即对父类的方法进行==重写==
3. `final`关键字可用于修饰类、变量和方法，它有“无法改变的”或者“最终”
4. 一个类要实现一个接口，可以使用关键字==implements==
5. 一个类要实现一个接口，那么它就需要重写接口中定义的全部方法，否则该类就必须定义成==抽象类==
6. 如果子类想引用父类成员，可以使用关键字==super==
# 判断
1. 定义一个抽象类的关键字是`interface` ==**✘**==
>`abstract`
2. 父类的引用指向自己子类的对象是多态的一种体现形式 ==**✓**==
3. Java中一个类最多可以有一个直接父类 ==**✓**==
4. 接口中定义的变量默认是`public static final`型，且必须赋初值 ==**✓**==
5. `final`修饰的局部变量只能被赋值一次
6. 在定义方法时不写方法体，这种不包含方法体的方法为静态方法 ==**✘**==
>应为抽象方法
7. Java中的`instanceof`关键字可以判断一个对象是否为某个类（或接口）的实例
# 选择
1. 下面程序运行结果为==可以编译运行，并输出结果AB==
```java
public class A{
	public static void main(String[]args){
	B b=new B();
	b.test();
	}
	void test(){
		System.out.println("A");
	}
}
class B extends A{
	void test(){
		super.test();
		System.out.print("B");
	}
}
```
2. 下列关于继承的描述错误的是==D==

A.Java中一个类只能有一个直接父类
B.多个类可以继承一个父类
C.Java中，C类继承B类，B类继承A类，这时C类也可以称作A类的子类
D.Java是支持多继承的
>Java ‌**不支持类的多继承**‌，但支持接口的多继承

3. 下列关于对象的类型转换的描述错误的是==C==

A.对象的类型转换可通过自动转换或强制转换进行
B.无继承关系的两个类的对象之间试图转换时会出现编译错误
C.由`new`语句创建的父类对象可以强制转换为之类对象
>子类对象可以向上转型为父类引用
>
但父类对象不能强制转换为子类类型（运行时抛出ClassCastException），因为父类对象可能不包含子类的特有属性和方法

D.子类对象转换为父类类型后，父类对象不能调用子类的特有方法

4. 下列关于接口的说法错误的是==D==

A.接口定义的方法默认使用`public abstract`修饰
B.接口中的变量默认使用`public static final`修饰
C.接口中的所有方法都是抽象方法
D.接口中定义的变量可以被修改
>所有变量默认是`public static final`的（常量），必须初始化且不能被修改
>
不存在实例变量，因为接口不能被实例化

5. 阅读下列代码，返回值为`true`的是==C==
```java
class Dog{
	public String name;
	Dog(String name){
		this.name=name;
	}
}
public class Demo1{
	public static void main(String[]args){
	Dog dog1=new Dog("xiaohuang");
	Dog dog2=new Dog("xiaohuang");
	String s1=dog1.toString();
	String s2=dog2.toString();
	String s3="xiaohuang";
	String s4="xiaohuang";
	}
}
```

A.dog1.equals(dog2) B.s1.equals(s2) C.s3.equals(s4) D.dog1\==dog2

# 简答
1. 简述Java中继承的概念以及使用继承的好处
>概念：Java继承是子类继承父类的属性和方法的过程，子类可以复用父类代码、扩展或重写功能
>好处：代码复用、逻辑层次清晰、便于扩展和多态实现
2. 简述多态的作用
>多态通过同一接口处理不同对象，提高代码灵活性和可扩展性，简化代码逻辑
3. 简述接口和抽象类的区别
>接口是纯抽象设计，允许多实现，用于定义行为规范
>抽象类可包含部分实现，单继承，用于代码复用和部分通用逻辑
# 编程
```java
/*Employee.java*/
abstract class Employee{
	private String name;                     //定义姓名name并私有化属性
	private int month;                       //定义生日月份month并私有化属性
	public Employee(){}                       //无参构造器
	public Employee(String name,int month){  //有参构造方法
		this.name = name;    //给属性name初始化赋值
		this.month = month;  //给属性month初始化赋值
	}
	//获取属性name的方法
	public String getName(){
		return name;   //返回name属性
	}
	//获取属性month的方法
	public int getMonth(){
		return month;  //返回month属性
	}
	//给属性name赋初始值
	public void setName(String name){
		this.name = name;  //本类中的属性name
	}
	//给属性month赋初始值
	public void setMonth(int month){
		this.month = month; //本类中的属性month
	}
	//创建一个方法getSalary()用来计算工资，参数month是月份，如果当月是员工生日，奖励100元
	public double getSalary(int month){
		double salary = 0;      //定义工资变量
		//判断当前月份是否是员     工的生日月份，如果是奖励100元
		if(this.month == month){
			salary = salary + 100;        
			return salary;    //返回工资salary
		}
	}
}
```

```java
/*SalariedEmployee.java*/
class SalariedEmployee extends Employee{
	private double monthSalary;           //封装monthSalary属性
	public SalariedEmployee(){}           //无参构造方法
	//有参构造方法   参数  姓名 生日月份  月薪
	public SalariedEmployee(String name,int month,double monthSalary){
		super(name,month);                  //调用父类有参构造方法
		his.monthSalary = monthSalary;   //为属性monthSalary初始化赋值
	}
	//获取monthSalary的值
		public double getMonthSalary(){
		return monthSalary;
	}
	//给monthSalary赋值
	public void setMonthSalary(double monthSalary){
	this.monthSalary = monthSalary;
	}
	//覆盖父类中的方法
	public double getSalary(int month){
		double salary = monthSalary+super.getSalary(month);   //定义工资变量
			return salary;   
	}
}
```

```java
/*HourlyEmployee.java*/
class HourlyEmployee extends Employee{
	private double hourlySalary; //定义属性hourlySalary每小时的工资
	private int hours; //定义属性hours每月工作的小时数
	public HourlyEmployee(){}    //无参构造方法
	//有参构造方法  参数 姓名 生日月份  每小时的工资 每月工作的小时数 
	public HourlyEmployee(String name,int month,double hourlySalary,int hours){
		super(name,month);                    //调用父类有参构造方法    
		this.hourlySalary = hourlySalary ; //为属性hourlySalary初始化赋值
		this.hours = hours;                //为属性hours 初始化赋值
	}
	public double getHourlySalary(){    //获取hourlySalary的值
		return hourlySalary;
	}
	public int getHours(){             //获取hours的值
		return hours;
	}
	//定义set方法设置hourlySalary  hours的值
	public void setHourlySalary(double hourlySalary){
		this.hourlySalary =hourlySalary;
	}
	public void setHourly(int hours){
		this.hours = hours;
	}
	//覆盖父类方法
	public double getSalary(int month){
		if(hours < 0){      //如果工作小时数小于0  输出数据错误
		System.out.println("数据错误");
		return 0;
		}  
		//小于160个小时的 按照每个月的工作小时数乘以每小时的工资
		else if(hours <= 160)
			return hourlySalary*hours+super.getSalary(month);
		//超出160个小时的小时数 按照1.5倍计算    
		else return hourlySalary*160+hourlySalary*1.5*(hours-160)+super.getSalary(month);
	}
}
```

```java
/*SalesEmployee.java*/
class SalesEmployee extends Employee{
	private double sales ; //定义销售额sales
	private double rate; //定义提成率rate
	public SalesEmployee(){}
	public SalesEmployee(String name,int month,double sales,double rate){
		super(name,month);
		this.sales = sales;
		this.rate = rate;
	}
	public double getSales(){
		return sales;
	}
	public double getRate(){
		return rate;
	}
	public void setSales(double sales){
		this.sales = sales;
	}
	public void setRate(double rate){
		this.rate = rate;
	}
	public double getSalary(int month){
		return this.getSales()*(1+this.getRate())+super.getSalary(month);
	}
}
```

```java
/*BasePlusSalesEmployee.java*/
class BasePlusSalesEmployee extends SalesEmployee{
	private double baseSalary; //定义基础工资baseSalary
	//无参构造方法
	public BasePlusSalesEmployee(){}
	//有参构造方法
	public BasePlusSalesEmployee(String name,int month,double sales,double rate,double baseSalary){
		super(name,month,sales,rate);
		this.baseSalary = baseSalary;
	}
	//get/set方法对私有属性的调用和设置
	public double gatBaseSalary(){
		return baseSalary;
	}
	public void setBaseSalary(){
		this.baseSalary = baseSalary;
	}
	public double getSalary(int month){
		return baseSalary+super.getSalary(month);
	}
}
```

```java
/*Test.java*/
//定义一个测试类
public class Test{
	public static void main(String[] args){
	//声明一个Employee类型的数组，并创建不同子类型的对象
	Employee[] employee = {new SalariedEmployee(“张三”,1,6000),new HourlyEmployee(“李 四”,2,50,180),new SalesEmployee(“王 五”,3,6500,0.15),new BasePlusSalesEmployee(“赵 六”,4,5000,0.15,2000)};
	//打印每个员工的工资
	for(int i = 0; i < employee.length ;i++)
		System.out.println(Math.round(employee[i].getSalary(10)));
	}
}
```