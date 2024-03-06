# 工具类
## 含义
- 帮助我们做一些事情，但不描述任何事物的类
## 特点
- 类名见名知意
- 私有化构造方法
- 方法定义为静态
```
public class ArrUtil{
	private ArrUtil(){}//私有化构造方法
	//定义静态方法
	public static int getMax(...){...}
	public static int getMin(...){...}
}
```
# JavaBean类
## 含义
- 用来描述一类事物的类
- 例如：Student，Teacher，Dog，Cat等
# 测试类
## 含义
- 用来检测其他类是否书写正确，带有main方法的类，是程序的主入口