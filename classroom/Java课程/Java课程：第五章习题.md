# 填空
1. ==RuntimeException==类及其子类用于表示运行时异常
2. 异常分为两种，分别是==运行时异常==和==编译时异常==
3. ==throw==关键字用于在方法中声明抛出异常的示例对象
4. 如果一个方法要抛出多个异常，可以使用==throws==关键字，多个异常之间用逗号隔开
5. 自定义异常需要继承==Exception==类
# 判断
1. `Throwable`有两个直接子类————`Error`和`Exception`，其中`Error`代表程序中产生的异常，`Exception`代表产生的错误 ==**✕**==
>Exception代表程序中可预期的异常情况（如IO异常、空指针异常等）
>
Error代表严重系统错误（如内存溢出），这些错误通常不应被捕获处理
2. Java中的异常类都继承自`java.lang.Throwable`类 ==**✓**==
3. 在处理异常时，`try`语句块中存放可能发生异常的语句 ==**✓**==
4. 在一个异常处理中，`finally`语句块只能有一个，也可以没有 ==**✓**==
5. 在Java语言中如果发生异常，但没有捕获异常的代码，程序会正常执行 ==**✕**==
>1. 如果出现**已检查异常**（即继承自 `Exception` 但不继承 `RuntimeException` 的异常），编译器会强制要求处理，否则代码无法编译通过
>2. 如果出现**未检查异常**（如 `RuntimeException` 或 `Error`），且没有 `try-catch` 处理，程序会**终止执行**，并打印堆栈跟踪信息（Stack Trace）
>3. **程序不会“正常执行”**，而是会因为未捕获的异常而中断当前线程的执行
# 选择
1. 在异常处理时，释放资源，关闭文件等操作由==finally==语句完成
2. ==Throwable==类是所有异常的父类
3. 下列异常声明中正确的是==C==

A.public void throws IOExceptionfun(){}
B.public void fun throws IOException(){}
C.public void fun() throws IOException{}
D.public void fun() throws IOException,throws SQLException{}

4. 以下关于编译异常的说法正确的是==C==

A.编译异常就是指`Exception`类及其子类
>“编译异常”通常指的是在代码编译阶段由编译器直接报出的错误（如语法错误、类型不匹配等），这类问题属于编译错误，而`Exception`类及其子类是程序运行时发生的异常，二者是不同的概念

B.编译异常如果产生可以不用处理
>编译异常是指必须处理的异常。Java编译器会强制检查这类异常，要么用`try-catch`捕获并处理，要么用` throws` 声明可能抛出的异常，否则代码无法通过编译

C.编译异常如果产生就必须处理，要么捕获，要么抛出
D.编译异常指的就是`Error`
>编译异常（通常指编译错误，如语法问题）和 `Error`（如 `OutOfMemoryError`）是不同概念：前者是代码未通过编译阶段的问题，后者是程序运行时发生的严重系统级错误，且 `Error` 通常不可恢复，而编译异常必须修复才能运行程序

5. 下面程序的运行结果是==A==
```java
class Demo{
	public static void main(String[]args){
		int x=div(1,2);
		try{
		}catch(Exception e){
			System.out.println(e);
		}
		System.out.println(x);
	}
	public static int div(int a,int b){
		retun a/b;
	}
}
```

A.输出0 B.输出1 C.输出0.5 D.编译失败
# 简答
1. 写出处理异常的5个关键字
>`try`,`catch`,`throw`,`throws`,`finally`

2. 简述`try...catch`语句的异常处理流程并画出流程图

>`try...catch` 的异常处理流程是在 `try` 块中执行代码，如果发生异常则立即停止 `try` 剩余代码，跳转到匹配的 `catch` 块处理异常；若没有匹配的 `catch`，则异常向外抛出。无论是否异常，`finally` 块都会执行

![[try...catch异常处理流程.excalidraw]]
3. 简述处理编译时异常的两种方式

 >1. 使用`try-catch`捕获并处理异常：
将可能抛出异常的代码放在`try`块中，并在对应的`catch`块处理异常
>2. 在方法签名中声明抛出异常（throws）：
如果不想在当前方法处理异常，可以用`throws`声明该异常，让调用者处理