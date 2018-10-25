# lesson2

1.2 类型

C# 支持两种类型：“值类型”和“引用类型”。值类型包括简单类型（如 char、int 和 float）、枚举类型
和结构类型。引用类型包括类 (Class) 类型、接口类型、委托类型和数组类型。

值类型与引用类型的区别在于值类型的变量直接包含其数据，而引用类型的变量则存储对象引用。对于引用类
型，两个变量可能引用同一个对象，因此对一个变量的操作可能影响另一个变量所引用的对象。对于值类型，每
个变量都有自己的数据副本，对一个变量的操作不可能影响另一个变量。

示例

using System;

class Class1

{

public int Value = 0;

}

class Test

{

static void Main()
{

int val1 = 0;

int val2 = val1;

val2 = 123;

Class1 ref1 = new Class1();

Class1 ref2 = ref1;

ref2.Value = 123;

Console.WriteLine("Values: {0}, {1}", val1, val2);

Console.WriteLine("Refs: {0}, {1}", ref1.Value, ref2.Value);

}

}

显示了这种区别。运行该程序，可见下列输出：

Values: 0, 123

Refs: 123, 123

给局部变量 val1 赋值不会影响局部变量 val2，这是因为两个局部变量都是值类型（int 类型），每个局部
变量都保存着各自的数据。相反，赋值 ref2.Value = 123; 则会影响到 ref2，因为 ref1 和 ref2 所引
用的其实是同一个对象。

应对代码行

Console.WriteLine("Values: {0}, {1}", val1, val2);

Console.WriteLine("Refs: {0}, {1}", ref1.Value, ref2.Value);
