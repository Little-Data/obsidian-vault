# 填空
1. 面向对象的三大特征是==封装==、==继承==和==多态==
2. 针对类、成员方法的属性，Java提供了4种访问控制权限，分别为==private==、==default==、==protected==、==public==
3. 静态方法必须使用==static==
4. 类的封装是指在定义一个类时将类中的属性私有化，即使用==private==关键字修饰
5. 一个类的封装可以定义多个构造方法，只要每个构造方法的==类型==或==个数==不同即可实现重载
6. 在Java中解决成员变量与局部变量名称冲突时，可以使用==this==关键字
# 判断
1. 在成员方法中出现的`this`关键字代表的是调用这个方法的对象 ==**✓**==
2. 封装就是隐藏对象的属性和实现细节，仅对外提供公有的方法 ==**✓**==
3. 面向对象的特点主要可以概括为封装性、继承性和重载性 ==**✕**==
>面向对象的特点通常概括为==封装性==、==继承性==和==多态性==，而不是重载性。
>
封装性：隐藏对象的实现细节，仅对外提供接口。
继承性：子类可以继承父类的属性和方法，实现代码复用。
多态性：同一方法在不同对象中表现不同行为（如方法重写、接口实现）。
>
“重载性”（如方法重载）只是多态的一种表现形式，不属于基本特性。
4. 定义在类中的变量叫成员变量，定义在方法中的变量叫做局部变量 ==**✓**==
5. 构造方法的名称必须和类名称保持一致 ==**✓**==
# 选择题
1. 关于`this`关键字的说法，错误的是==C==

A.`this`关键字可以解决成员变量和局部变量重名的问题
B.`this`关键字出现在成员方法中，代表的是调用这个方法的对象
C.`this`关键字可以出现在任何方法中
>`this` **只能用于实例方法和构造方法中**，表示当前对象。它不能出现在：
>
静态方法中（`static`方法属于类，不依赖对象）。
静态代码块中（与对象无关）。

D.`this`关键字相当于一个引用，可以通过它调用成员方法与属性

2. 阅读下程序，运行结果为==WorldHello==

```java
class Test{
	private static String name;
	static{
		name="World";
		System.out.print(name);
	}
	public static void main(String[]args){
		System.out.print("Hello");
		Test test=new test();
	}
}
```
>执行顺序：
>1. 类加载时静态块(static)先执行 → 打印"World"
>
>2. main方法执行：
打印"Hello"
实例化Test对象时，**不会再次执行静态块（仅在类加载时执行一次）**

3. 对于声明为private、protected及public的类成员在类外部==都不能访问==
4. 阅读下程序，运行结果为==输出2个hello后会抛出异常==
```java
class Person{
	void say(){
		System.out.println("hello");
	}
}
class Example{
	public static void main(String[]args){
		Person p2=new Person();
		Person p1=new Person();
		p2.say();
		p1.say();
		p2=null;
		p2.say();
	}
}
```
5. 下列类定义中不正确的是==C==

A.class X {...}
B.class X extends Y {...}
C.static class X implements Y1,Y2 {...}
>有条件
>
static class 是合法的，但必须是嵌套类（定义在另一个类内部）
如果它是顶层类，则 不正确（static 不能用于顶层类）
如果它在另一个类内部（如 class Outer { static class X implements Y1, Y2 {...} }），则正确

D.public class X extends Applet {...}
# 简答
1. 简述你对面向对象的三大特征的理解
>封装：隐藏内部细节，提供安全接口
>继承：子类复用父类特性，扩展功能
>多态：同一接口不同实现，灵活调用
2. 简述构造方法的特点
>1. 名称必须与类名一致
>2. 无返回值类型
>3. 自动调用（new时）
>4. 可重载（参数不同）
>5. 默认有空参构造（除非显式定义）
>6. 初始化对象状态
# 编程
某公司正在进行招聘工作，被招聘人员需要填写个人信息。编写个人简历的封装类Resume，并编写测试类进行测试。Resume类图及输出效果如下。

| 类名：Resume                                                  |
| ---------------------------------------------------------- |
| name:String(private)                                       |
| sex:String(private)                                        |
| age:int(private)                                           |
|-|
| Resume() //没有参数的空构造方法                                      |
| Resume(String name,String sex,int age) //得到各个属性值的方法getxx() |
| introduce():void  //自我介绍（利用属性）                             |
运行结果如下：

| 姓名：李四 |
| ----- |
| 性别：男  |
| 年龄：20 |
```java
class Resume {
	private String name;
	private String sex;
	private int age;
	public Resume(){
	}
	public Resume(String name,String sex,int age){
		this.name = name;
		this.sex = sex;
		this.age = age;
	}
	public String getName(){
		return name;
	}
	public String getSex(){
		return sex;
	}
	public int getAge(){
		return age;
	}
	public void introduce(){
		System.out.println("姓名："+this.getName()+"\n性别："+this.getSex()+"\n年龄："+this.getAge());
	}
}
public class Example{
	public static void main(String[] args){
		Resume re = new Resume("李四","男",20);
		re.introduce();
	}
}
```