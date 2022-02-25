# 简介

* Microsoft
* 特点：
  * 现代的、通用的编程语言。
  * 面向对象。
  * 面向组件。
  * 容易学习。
  * 结构化语言。
  * 它产生高效率的程序。
  * 它可以在多种计算机平台上编译。
  * .Net 框架的一部分。
* .Net框架
  * 编写应用程序的平台
  * 适用于C#、C++、Basic、Jscript等语言
# 程序结构  

```csharp	
using System; //主命名空间，包含所有.net基础类型和通用类型，比如Object，比如string等等
namespace HelloWorldApplication //命名空间声明
{
  class HelloWorld
  {
	  static void Main(string[] args) //程序的执行从 Main 方法开始
	  {
		  /*我的第一个C#程序*/
		  Console.WriteLine("Hello World");
		  Console.ReadKey();
	  }
  }
}
```
# 基本语法
~~~csharp
using System;
namespace RectangleApplication
{
    class Rectangle
    {
        // 成员变量
        double length;
        double width;
        public void Acceptdetails()
        {
            length = 4.5;    
            width = 3.5;
        }
        public double GetArea()
        {
            return length * width;
        }
        public void Display()
        {
            Console.WriteLine("Length: {0}", length);
            Console.WriteLine("Width: {0}", width);
            Console.WriteLine("Area: {0}", GetArea());
        }
    }
   
    class ExecuteRectangle // 实例化Rectangle类
    {
        static void Main(string[] args)
        {
            Rectangle r = new Rectangle();
            r.Acceptdetails();
            r.Display();
            Console.ReadLine();
        }
    }
}
~~~
# 数据类型

1. 值
| 类型 | 描述 |
| :--: | :-- |
| double | 64位双精度浮点数 |
| int | 32 位有符号整数类型|
