# 抽象类
## 抽象类&抽象方法
1. 抽象方法
- 将**共性的行为（方法）** 抽取到父类之后，由于每个子类执行的内容是不一样的，所以，在父类不能确定**具体的方法体**，该方法就可以定义为抽象方法
2. 抽象类
- 如果一个类中存在抽象方法，那么该类就必须声明抽象类
### 抽象类和抽象方法的定义格式
- 抽象方法：
`public abstract 返回值类型 方法名（参数）;`
- 抽象类：
`public abstract class 类名{}`
### 抽象类和抽象方法的注意事项
- 抽象类不能实例化——**不能创建对象**
- 抽象类中不一定有抽象方法，有抽象方法一定又抽象类
- 可以构造方法
	- 当子类创建对象时，给子类进行赋值
- 抽象类的子类
	- 要么重写抽象类中的所有抽象方法
	- 要么子类是抽象类
# 接口
## 为什么要有接口
![[为什么要有接口图示.png]]
- 可以把接口视为一个规则
- 需要给多个类同时定义规则就需要用到规则
### 接口与抽象类的异同
![[接口与抽象类的区别.png]]
- 抽象类需要有继承关系
- 而接口时一种规则，是面向行为的抽象，可以存在于不同的继承体系
## 接口的定义和使用
- 接口用关键字**interface**定义
`public interface 接口名{}`
- 接口不能实例化
- 接口和类之间是实现关系，通过**implements**关键字表示
`public class 类名 implements 接口名{}`
- 接口的子类（实现类）
	- 要么重写接口中所有抽象方法
	- 要么子类是抽象类
- 注：
1. 接口和类的实现关系，可以单实现，也可以多实现
`public class 类名 implements 接口1， 接口2{}`
2. 实现类还可以在继承一个类的同时实现多个接口
`public class 类名 extends 父类 implements 接口1，接口2{}`
## 接口中成员的特点
- 成员变量
	- 只能是常量
	- 默认修饰符：public static final
- 构造方法
	- 没有
- 成员方法
	- 只能是抽象方法——jdk7以前
	- 默认修饰符：public abstract
	- jdk8新特性：接口中可以定义有方法体的方法
	- jdk9新特性：接口中可以定义私有方法
## 接口与类之间的关系
- 类和类之间的关系
	- 继承关系：只能单继承，不能多继承，但可以多层继承
- 接口和类之间的关系
	- 实现关系，可以单实现，可以多实现，还可以在继承一个类的同时实现多个接口
- 接口和接口之间的关系
	- 继承关系，可以单继承，可以多继承
### 注：
- 如果类在实现多个接口的同时，有重名的抽象方法怎么办
	- 重名的只用写一次就好了
- 如果接口与接口继承，接口的是最下层的子类接口
	- 那么要重写以上所有的抽象方法
## JDK8以后开始新增的方法
- jdk8新特性：接口中可以定义有方法体的方法
- jdk9新特性：接口中可以定义私有方法
### JDK8——默认方法
#### 如何解决接口升级，更改实现类中的方法
- 允许在接口定义默认方法，需要使用关键字**default**修饰
##### 作用：解决接口升级问题
#### 接口中默认方法的定义格式
```
格式：public default 返回值类型 方法名（参数列表）{}
范例：public default void show(){}
```
#### 接口中默认方法的注意事项
- 默认方法不是抽象方法，所以不强制被重写，但如果被重写，重写时去掉default关键字
- public可以省略，但是default不能省略
- 如果实现了多个接口，多个接口中存在相同名字的默认方法，子类就必须对该方法进行重写
```
public interface Inter{
	//1.抽象方法
	public abstract void method();
	//2.默认方法
	public default void show(){
		sout("接口中的默认方法");
	}
}

public class InterImp1 implements Inter{
	public void method(){
		sout("抽象方法的重写");
	}
	//这里的默认方法show不写也可以
	public void show(){
		sout("默认方法的重写");
	}
}
```
### JDK8——静态（static）方法
- 允许在接口定义静态方法，需要用static修饰
#### 接口中静态方法的定义格式
```
格式；public static 返回值类型 方法名（参数）{}
范例：public static void show(){}
```
#### 接口中静态方法的注意事项：
- 静态方法**只能通过接口名调用**，不能通过实现类名或者对象名调用
- public可以省略，static不能省略
### JDK9——私有方法
![[Inter—JDK9—新增私有方法.png]]
#### 使用私有方法接口的注意事项
![[static.png]]
## 总结
1. JDK7以前：接口中只能定义抽象方法
2. JDK8：接口中可用定义有方法体的方法（默认、静态）
3. JDK9：接口中可用定义私有方法
4. 私有方法分两种：普通私有方法，静态私有方法
# 适配器模式
1. 当一个接口中抽象方法过多，但是我只要使用其中一部分的时候，就可以适配器设计模式
2. 书写步骤：1. 编写中间类XXXAdapter，实现对应的接口
			2. 对接口中的抽象方法进行空实现
			3. 让真正的实现类继承中间类，并重写需要用的方法
			4. 为了避免其他类创建适配器对象，**中间的适配器类用abstract进行修饰**
# 内部类
