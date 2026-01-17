```java
public class Hello
{
	public static void main(String[] args)
	{
		System.out.println("Hello,world!");
	}
}
```
在一个Java程序中，总能找到一个类似
```Java
public class Hello{
	...
}
```
的定义，这个定义被称为class（类），这里的类名为`Hello`，Java对大小写敏感，`public`表示这个类是公开的，`public`、`class`都是Java的关键字，必须小写，`Hello`是类的名字，按照习惯首字母大写，花括号`{}`中间是类的定义

在类的定义中我们定义了一个名为`main`的方法
```Java
	public static void main(String[] args){
	...
	} 
```
方法是可执行的代码块，`main`为方法名，括号里的为方法参数，这里的`main`有一个方法参数，参数类型是`String[]`，参数名是`args`，`public`、`static`用来修饰方法，表示他是一个公开静态的方法，`void`是方法返回的类型，方法的每一行用`;`结束。这里只有一行代码
```Java
		System.out.println("Hello,world!");
```
他用来打印一个字符串到屏幕上

Java规定，某个类定义的`public static void main(String[] args)`方法是Java程序的固定入口方法，Java程序总是从`main`方法开始执行

Java源码的缩进不是必须的。最后我们把代码保存为文件时，文件名必须是`Hello.java`，而且文件名也需要注意大小写，和我们定义的类名`Hello`保持一致

## 如何运行Java程序
Java源码本质上是一个文本文件，我们需要先用`javac`把`Hello.java`编译为字节码文件`Hello.class`，然后，用`java`命令执行这个字节码文件：
```
┌──────────────────┐
│    Hello.java    │◀── source code
└──────────────────┘
          │ compile
          ▼
┌──────────────────┐
│   Hello.class    │◀── byte code
└──────────────────┘
          │ execute
          ▼
┌──────────────────┐
│    Run on JVM    │
└──────────────────┘
```
因此可执行文件`javac`是编译器，`java`就是虚拟机。

在保存`Hello.java`的目录执行命令`javac Hello.java`
```bash
$ javac Hello.java
```
如果源代码无误，上述命令不会有任何输出，而在当前目录下会产生一个`Hello.class`文件，然后执行`Hello.class`，使用命令`java Hello`（注意不是`java Hello.class`）
```bash
& java Hello
Hello,world!
```
注意：给虚拟机传递的参数`Hello`是我们的类名，虚拟机自动查找对应的class文件执行

直接运行`java Hello.java`也是可以的，这是因为从Java11开始，java可以直接运行一个单文件源码。

但是在实际项目中，单个不依赖第三方库的Java源码是不常见的，多数情况下我们无法直接运行一个Java源码文件，原因是他需要依赖其他的库
## 小结
一个Java源码只能定义一个`public`类型的class，并且class名称和文件名要完全一致；
使用`javac`可以将`.java`源码编译成`.class`的字节码；
使用`java`可以运行一个以编译的Java程序，参数是类名