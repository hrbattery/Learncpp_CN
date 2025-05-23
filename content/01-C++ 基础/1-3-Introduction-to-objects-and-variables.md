---
title: 1.3 - 对象和变量
alias: 1.3 - 对象和变量
origin: /introduction-to-objects-and-variables/
origin_title: 1.3 — Introduction to objects and variables
time: 2021-9-28
type: translation
tags:
- object
- variable
---

> [!note] "Key Takeaway"
> - 尽管在语言层面，使用单一语句定义多个变量是被允许的，但是在实践中应当尽量避免这样去做（即时它们具有相同的类型）。正确的做法是一个语句定义一个变量（并使用单行注释解释该变量的用途）。
> - C++ 只能通过对象来间接地访问内存
> - 对象即存放在内存中具有值以及其他属性的数据
> - C++ 中的对象指的是变量和数据结构，但不包括函数
> - 对象可以是命名的或未命名的，命名的对象称为变量
> - 变量在程序运行时被实例化，即创建一个对象、为其分配内存并将结果保存在变量中
> - 数据类型用于告诉编译器它要存储或解析的变量是什么格式
> - 尽量避免在一行定义多个变量，容易出现忘记初始化的情况


## 数据

在 [[1-1-Statements-and-the-structure-of-a-program|1.1 - 程序结构和语句]] 中，我们学习了组成一个程序所涉及的大多数语句并且将它们封装成了函数。这些语句能够执行一系列操作并按照（但愿）预期输出正确的结果。

但是，程序究竟是如何生成这些结果的呢？它们是通过操作（读、修改、写）数据来完成这一过程的。在计算机领域，数据指的是任何可以被计算机移动、处理和存储的信息。


> [!tldr] "关键信息"
> 所谓程序，即一系列用于操作数据并输出预期结果的指令

一个程序可以通过多种途径来获取数据，例如通过文件、数据库、网络、用户输入来获取，程序员甚至可以直接将数据嵌入在程序源码中。在前面课程中编写的 “Hello world” 程序中，“Hello world”这个字符串便是直接嵌入在程序中的。随后，该程序对该数据进行操作，将其显示在显示器上。

数据在计算机中存储时，往往以一种更高效更便于处理的格式来存储（往往不能够被人类直接阅读）。因此，当 “Hello World” 程序被编译后，字符串 “Hello World” 会被转换为一种更为高效的格式来存储并提供给程序使用（二进制格式——我们将在后续的课程中进行详细介绍）

## 对象和变量

所有计算机都有内存，即 RAM （随机访问内存）， 可供程序使用。你可以将 RAM 看做是一系列具有标号的“信箱”，在程序运行的过程中，它们可以存放一系列的数据片段。一个单独的存放在内存中的数据，称之为值（value）。

在一些比较古老的编程语言中（例如 Apple Basic），你可以直接访问这些”信箱“（对应的语句类似于*获取标号为7532的信箱中的数据*）

在 C++ 中，直接访问内存是不被允许的，我们只能够通过某个对象间接地访问内存。所谓对象，即存放在某个区域（一般来讲为内存），具有值以及其他属性（后续课程会着重介绍）的数据。编译器和操作系统为对象分配内存的过程，超出了本课程的范围。但是，我们需要知道的是，*获取标号为7532的信箱中的数据* 是不可行的，取而代之的应当是*获取某个对象所保存的值*。这意味着，我们可以专注于使用对象来存储和读取数据，而不必担心它们实际使用的内存。

对象可以是命名的，或未命名的。一个命名的对象被称为变量，而该对象的名字本身，则称为[[identifier|标识符(identifier)]]。在我们的程序中，大多数的对象都属于变量。


> [!info] "作者注"
> 在一般的编程中，*对象*这个术语通常指代的是某一个变量、数据结构或函数。在 C++ 中，*对象*这个术语的含义要更加局限一些，它并不包括函数。



## 变量的实例化

为了创建变量，我们需要一种被称为”定义“的特殊类型的声明语句（稍后会澄清声明和定义之间的区别）。

定义一个变量名为x的变量，案例如下：

```cpp
int x; // define a variable named x, of type int
```

在编译阶段，当编译器解析到该语句时，它会记录下此时定义的一个名为x、类型为 int 的变量。（稍后会详细介绍类型系统）。从此以后（有一定的限制条件，稍后介绍），每当编译器看到标识符 x，它就知道去引用这个变量。

在程序运行的时候（称为运行时），该变量会被[[instantiated|实例化]]。实例化这个词只是听起来有点玄乎罢了，它的含义很简单——创建对象并为其分配一个内存地址。变量在使用前（存储值前）必须实例化。举例来说，假设变量x实例化后对应的内存地址为140，之后程序在任何时候使用该变量x时，它都会取访问内存地址140。一个实例化之后的对象，通常被称为[[instance|实例(instance)]]。


## 数据类型

到目前为止，我们已经知道了，变量就是某个命名之后的存储区域，它可以存放数据（如何存放将在后续的章节讨论）。数据类型（一般简称为类型）可以告知编译器它要存储的该数据的值是什么类型（例如，数字，字母，文本等等）。

在上面的例子中，变量 x 的类型是 int，也就是说，该变量 x 表示的是一个整型的值。整型表示该数字不需要小数部分就可以表示，例如 4，27，0，-2 或者 -12。长话短说，这里 x 是一个整型变量。

在 C++ 中，变量的类型必须在[[compile-time|编译时]]确定。此外，该类型在下一次编译前，不能发生改变。这意味着，该整型变量只能始终存放一个整型的值，如果你希望它存放其他类型的值，你必须使用另外的变量。

整型只是 C++ 原生支持的多种类型中的一种。为了更好的解释，请看下面的例子，这里我们定义了一个类型为 double 的变量：

```cpp
double width; // define a variable named width, of type double
```


C++ 允许用户创建自定义的数据类型。我们会在将来的课程中大量使用自定义的数据类型，这是 C++ 语言强大的原因之一。

在介绍性的章节中，我们只使用整型变量，因它们更加简单，但是我们很快就会在后续的课程中探索大量的其他 C++ 支持的数据类型。

## 定义多个变量

在一个语句中定义多个相同类型的变量当然也是可以的，只需要用逗号将变量名分割开来即可。下面两个代码片段的效果是一样的：

```cpp
int a;
int b;
```


```cpp
int a, b;
```


如果属于上述方式来定义多个变量，新手程序员常会犯下两种错误（这没有什么大不了的，因为编译器会捕获这些错误并要求你进行修复）：

第一种错误是为每个变量都添加类型说明。

```cpp
int a, int b; // wrong (compiler error)

int a, b; // correct
```

第二种错误是在一个语句中定义两种不同类型的数据，这是不被允许的。不同数据类型的变量必须分别定义。

```cpp
int a, double b; // wrong (compiler error)

int a; double b; // correct (but not recommended)

// correct and recommended (easier to read)
int a;
double b;
```


> [!success] "最佳实践"
> 
> 尽管在语言层面，使用单一语句定义多个变量是被允许的，但是在实践中应当尽量避免这样去做（即时它们具有相同的类型）。正确的做法是一个语句定义一个变量（并使用单行注释解释该变量的用途）。

## 小结

在 C++ 中，我们使用变量来访问内存。变量具有标识符、类型和值（以及其他一些与此处不相关的属性）。变量类型用于确定内存中的值应该被如何解析。

在下一节课中，我们会介绍如何为变量赋值并使用它们。