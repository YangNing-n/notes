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

```csharp
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
```

# 数据类型

1. 值  
* double：64位双精度浮点数
* int：32 位有符号整数类型  
`sizeof()`获取变量的大小
```csharp
using System;
namespace DataTypeApplication
{
   class Program
   {
      static void Main(string[] args)
      {
         Console.WriteLine("Size of int: {0}", sizeof(int));
         Console.ReadLine();
      }
   }
}
```
2. 引用类型  
* object
object可以被分配任何其他类型
```
object obj;
obj = 100; // 值类型赋值给对象类型-装箱；对象类型转换为值类型-拆箱
```
* dynamic  
对象类型变量的类型检查是在**编译**时发生的，而动态类型变量的类型检查是在**运行**时发生的  
* string  
`string str = "abc";`  
`string str = @"abc";`  
@可以将转义符\作为普通字符，且可以任意换行：  
`strin str = @"C:\Windows";`  
等价于`string str = "C:\\Windows";`  
3. 指针类型  
`char* cptr`  

# 类型转换（类型铸造） 

* 隐式类型转换 - 这些转换是 C# 默认的以安全方式进行的转换, 不会导致数据丢失。例如，从小的整数类型转换为大的整数类型，从派生类转换为基类。  
* 显式类型转换 - 显式类型转换，即强制类型转换。显式转换需要强制转换运算符，而且强制转换会造成数据丢失。  
显式类型转换实例：  
```csharp
namespace TypeConversionApplication
{
    class ExplicitConversion
    {
        static void Main(string[] args)
        {
            double d = 5673.74;
            int i;

            // 强制转换 double 为 int
            i = (int)d;
            Console.WriteLine(i);
            Console.ReadKey();
           
        }
    }
}
```

# 封装  

C#支持的访问修饰符：
* public：所有对象都可以访问；  
* private：只有同一个类中的函数可以访问；  
* protected：只有该类对象及其子类对象可以访问
* internal：同一个程序集的对象可以访问；
* protected internal：访问限于当前程序集或派生自包含类的类型。
如果没有指定类的访问修饰符，默认为internal；不指定类成员的访问修饰符默认为private。  

# 方法

1. 定义方法  
语法：  
```
<访问修饰符> <返回类型> <Method Name>(Parameter List)
{
   Method Body
}
```
定义方法实例：  
```
class NumberManipulator
{
   public int FindMax(int num1, int num2)
   {
      /* 局部变量声明 */
      int result;

      if (num1 > num2)
         result = num1;
      else
         result = num2;

      return result;
   }
   ...
}
```
2. 调用方法  
```
using System;

namespace CalculatorApplication
{
   class NumberManipulator
   {
      public int FindMax(int num1, int num2)
      {
         /* 局部变量声明 */
         int result;

         if (num1 > num2)
            result = num1;
         else
            result = num2;

         return result;
      }
      static void Main(string[] args)
      {
         /* 局部变量定义 */
         int a = 100;
         int b = 200;
         int ret;
         NumberManipulator n = new NumberManipulator();

         //调用 FindMax 方法
         ret = n.FindMax(a, b);
         Console.WriteLine("最大值是： {0}", ret );
         Console.ReadLine();
      }
   }
}
```
