```
public class HelloWorld {
	public static void main(String[] args) {
		System.out.println("HelloWorld");
	}
}
```
- public：被JVM调用，访问权限足够大
- static：被JVM调用，不用创建对象，直接类名访问
		因为main方法是static，所以测试类中其他方法也需要static
- void：被JVM调用，不需要给JVM返回值
- main：一个通用名称，不是关键字，但是被JVM识别
- String[] args：以前用于接收键盘录入数据的，现在没用