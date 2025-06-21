1. 编写一个程序，计算边长分别为50、100的直角三角形的面积与上、下边长和高分别为27、51、20的梯形的面积
```java
public class mianji {
    public static void main(String[] args) {
        // 计算直角三角形面积（底50，高100）
        double sjxmj = 0.5 * 50 * 100;
        
        // 计算梯形面积（上底27，下底51，高20）
        double txmj = 0.5 * (27 + 51) * 20;
        
        System.out.println("直角三角形的面积: " + sjxmj);
        System.out.println("梯形的面积: " + txmj);
    }
}
```
2. 今有鸡兔同笼，上有40个头，下有110足，问鸡兔各几只？试编写程序解决这个问题
```java
public class ChickenRabbitProblem {
    public static void main(String[] args) {
        int heads = 40;     // 总头数
        int legs = 110;     // 总腿数
        
        // 计算兔的数量: (legs - 2*heads) / 2
        int rabbits = (legs - 2 * heads) / 2;
        int chickens = heads - rabbits;
        
        System.out.println("鸡有 " + chickens + " 只，兔有 " + rabbits + " 只。");
    }
}
```
3. 编写程序将给定的小写字母c，转换成大写字母
```java
public class LowerToUpper {
    public static void main(String[] args) {
        char lowercase = 'c';
        char uppercase = Character.toUpperCase(lowercase);
        System.out.println("转换结果：" + uppercase);
    }
}
```