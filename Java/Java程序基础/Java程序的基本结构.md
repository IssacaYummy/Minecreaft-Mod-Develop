一个完整的Java程序如下：
```Java
/**
 * 可以用来自动创建文档的注释
 */
public class Hello {
    public static void main(String[] args) {
        // 向屏幕输出文本:
        System.out.println("Hello, world!");
        /* 多行注释开始
        注释内容
        注释结束 */
    }
} // class定义结束
```
因为Java是面对对象的语言，一个程序的基本单位就是`calss`，`class`是关键字，这里定义的`class`名字就是`Hello`：
```Java
public class Hello{ // 类名是Hello
	  // ...
	} // class定义结束
```
类名要求：
* 类名必须以英文字母开头，后接字母，数字和下划线组合
* 习惯以大写字母开头
`public`是访问修饰符，表示该`class`是公开的。
不写`public`也能正确编译，但是这个类将无法从命令行执行。
在`class`内部，可以定义若干方法（method）：
```Java
public class Hello {
    public static void main(String[] args) { // 方法名是main
        // 方法代码...
    } // 方法定义结束
}
```
这里的方法名是`main`，返回值是`void`，表示没有任何返回值。

我们注意到`public`除了可以修饰`class`外，也可以修饰方法。关键词`static`是另一个修饰符，表示静态方法。
Java入口程序规定方法必须是静态方法，方法名必须是`main`，括号里的参数必须是String数组。

方法名也有命名规则，命名和`class`一样，但是首字母小写。

方法内部的语句是真正执行的代码，每一行语句必须以分号结束。
```Java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!"); // 语句
    }
}
```
### 注释
和C/C++一样，共有三种注释
单行注释
```Java
// 这是注释...
```
多行注释
```Java
/*
这是注释
blablabla...
这也是注释
*/
```
特殊多行注释
```Java
/**
 * 可以用来自动创建文档的注释
 * 
 * @auther Yummy
 */
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```
这种多注释需要写在类和方法的定义处，用于自动创建文档。