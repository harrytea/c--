## 第二章 开始学习c++
 
### 2.1 进入c++

```c++
//2.1 myfirst.cpp--display a message
#include<iostream> //a preprocessor directive
int main()
{
    using namespace std; //function header
    cout << "Come up and C++ me some time."; //message
    cout << endl; //start a new line
    cout << "You won't regret it!" << endl; // more output
    return 0; // terminate main()
}
```

若程序运行完毕后自动关闭该窗口，可在return前加入**cin.get()**

程序中有：注释//，预处理器编译指令#include、函数头int main()、编译指令using namespace、函数体{}、显示消息的语句c++、结束main函数的语句return

#### 2.1.1 main()函数

```c++
int main()
{
    statements
    return 0; //返回语句，结束该函数
}
```

构成了函数的定义：函数头int main()+函数体{}

c++中，每条完整的指令都称为语句，语句是要执行的操作，为理解源代码，编译器需要知道一条语句何时结束，另一条语句何时开始，终止符是一个分号，他是语句的结束标记，是语句的组成部分，所有的语句都以分号结束，不能省略分号。

**作为函数的函数头**

描述了函数与调用它的函数之间的接口，位于函数名前面的部分叫做函数返回类型，描述的是从函数返回给调用它的函数的信息；函数名后口号中的部分叫做形参列表（参数列表），描述的是从调用函数传递给被调用函数的信息

通常，main函数被启动代码调用，而启动代码是由编译器添加到程序中的，是程序和操作系统之间的桥梁，事实上，该函数头描述的是main和操作系统之间的接口

main()从int开始，c++函数可以给调用函数返回一个值，这个值叫做返回值；空括号意味着main函数不接受任何信息，或者main不接受任何参数；main函数表明可以给调用它的函数返回一个整数值，且不从调用它的函数那里获得任何信息

*  也可以写成int main(void) //c+中空着和写成void等效
* 如果没有遇到返回语句，默认为return 0；

**为什么main()不能使用其他名称**

运行c++程序时，必须从main函数开始执行，如果没有main系统将指出未定义main函数

#### 2.1.2 c++注释

以双斜杠（//）打头，到行尾结束。注释是程序员为读者提供的说明，通常标识程序的一部分或解释代码的某个方面。程序越复杂，注释的价值越大，注释不仅有利于他人理解这些代码，也有助于程序员自己理解代码，特别是隔了一段时间没有接触该程序的情况下。

* c++也能够识别c注释，/* */符号之间的内容，且可以跨越多行

#### 2.1.3 c++预处理器和iostream文件

```c++
#include<iostream>
using namespace std;
```

第一条指令导致预处理器将iostream文件的内容添加到程序中，在源代码被编译前，替换或添加文本。为什么要将iostream文件的内容添加到程序中呢，答案涉及程序与外部世界之间的通信。iostream中的io指的是输入（进入程序的信息）和输出（从程序中发送出去的信息）。c++的输入/输出方案涉及iostream文件中的多个定义。为了使用cout来显示消息，第一个程序需要这些定义。include编译指令导致iostream文件的内容随源代码文件的内容一起被发送给编译器。iostream文件的内容将取代程序中的代码行#include< iostream>。原始文件没有修改，而是将源代码文件和iostream组合成一个复合文件，编译的下一阶段将使用该文件。

* 使用cin和cout进行输入和输出的程序必须包含文件iostream

#### 2.1.4 头文件名

像iostream这样的文件叫做包含文件（由于他们被包含在其他文件中）；也叫头文件（由于他们被包含在文件起始处）。c语言的传统是使用扩展名h，将其作为一种通过名称标识文件类型的简单方式，例如math.h。c++对老式c的头文件保留了扩展名h（c++程序仍然可以使用这种文件），而c++头文件则没有扩展名。有些c头文件被转换为c++头文件，这些文件被重新命名，去掉了扩展名h（使之称为c++风格的名称）并在文件名称前面加上前缀c（表明来自c语言），例如math.h变为cmath（没有h的头文件也可以包含名称空间，下面进行介绍）

#### 2.1.5 名称空间

如果使用iostream而不是iostream.h，则应使用下面的名称空间编译指令来使iostream中的定义对程序可用：using namespace std，这叫做using编译指令

名称空间支持是一项c++特性，旨在编写大型程序以及将多个厂商现有的代码组合起来的程序时更容易，它还有助于组织程序。一个潜在的问题是，可能使用两个已经封装好的产品，他们都包含一个名为wanda的函数，使用时，编译器将不知道指的是哪个版本，名称空间让厂商能够将其产品封装在一个叫做名称空间的单元中，这样就可以用名称空间的名称来指出想使用哪个厂商的产品。例如

```c++
microflop::wanda("go dancing?")
piscine::wanda("a fish named desire")
```
在iostream中定义的用于输出的cout变量实际上是std::cout，endl是std::endl，若省略using namespace std，则
```c++
std::cout<<"Come up and c++ me some time.";
std::cout<<std::endl;
```

* 名称空间之前的代码：使用iostream.h和cout
* 名称空间代码：使用iostream和std::cout

using namespace std（lazy approach，all names available）；可以使用std名称空间中定义的名称，而不使用前缀std::，这个指令允许std名称空间中的所有指令均可用，如果只需要某一名称指令，例如cout，写成using std::cout。

#### 2.1.6 使用cout进行c++输出

```c++
cout << "Come up and c++ me some time"
```

功能显示字符串，cout<< string ，若string是一个字符串，直接显示字符串。cout将字符串插入到输出流中

注意：运算符重载，插入运算符（<<）像按位左移运算符（<<），这是一个运算符重载的例子，通过重载，同一个运算符将有不同的含义。

**控制符endl和换行符**

cout语句的输出从前一个输出的末尾开始，之间没有空隙。

控制符endl和换行符‘\n’的区别：

* endl是在头文件iostream中定义的，位于名称空间std中。
* ‘\n’是c语言中特定的换行符，被视为一个字符。

显示引用括起的字符串时，通常使用换行符‘\n’，在其他情况下使用控制符endl。endl确保程序继续运行前刷新输出（将其立即显示在屏幕上），换行符则不行。

#### 2.1.7 c++源代码的格式化

c++中，通常可以在能够使用回车的地方使用空格

**标记和空白**

一行代码中不可分割的元素叫做标记，必须用空格、制表符或回车将两个标记分开，空格、制表符和回车统称为空白。

**c++源代码风格**

* 每个语句占一行
* 每个函数都有一个开始花括号和一个结束花括号，各占一行
* 函数中的语句都相对于花括号进行缩进
* 与函数名称相关的圆括号周围没有空白

### 2.2 C++语句

```c++
// 2.2 carrots.cpp -- food processing program
// uses and displays a variable

#include<iostream>

int main()
{
	using namespace std;

	int carrots; // declare an integer variable

	carrots = 25; // assign a value to the variable
	cout << "I have ";
	cout << carrots; // display athe value of the variable
	cout << " carrots.";
	cout << endl;
	carrots = carrots - 1; // modify the variable
	cout << "Crunch, crunch. Now I have " << carrots << " carrots." << endl;
	return 0;
}
```

#### 2.2.1 声明语句和变量

```c++
int carrots;
```

* 提供了两条信息：需要的内存以及该内存单元的名称
* 给存储单元指定名称，使用carrots来标识存储在该内存单元中的值，carrots为变量，可以修改。**在c++中，所有变量必须先声明，后使用。**

程序中的声明语句叫做定义声明语句，简称为定义。在较为复杂的情况下还有引用声明，这些声明命令计算机使用在其他地方定义的变量。

* 通常声明不一定是定义，此处的声明是定义。

#### 2.2.2 赋值语句

```c++
carrots = 25;
```

符号“=”叫做赋值运算符，可以连续使用赋值运算符，例如

```c++
yamaha = baldwin = steinway = 88;
```

赋值从右向左进行，88先给steinway，然后steinway给baldwin，以此类推

##### 2.2.3 cout新花样

```c++
cout << carrots;
```

程序打印存储在carrots中的值。首先cout将carrots替换为其当前值25，然后把值转换为合适的输出字符

**cout和printf()**

cout有明显的优点，它能够识别类型的功能表示，设计灵活，他也是可扩展的，可以重新定义<<符号，使cout能够识别和显示所开发的新数据类型，如果喜欢printf()提供的细致的控制功能，可以使用更高级的cout来获得相同的效果

### 2.3 其他C++语句

```c++
// 2.2 getinfo.cpp -- input and output
#include<iostream>

int main()
{
	using namespace std;

	int carrots;

	cout << "How many carrots do you have?" << endl;
	cin >> carrots; // C++input
	cout << "Here are two more. ";
	carrots = carrots + 2; 
	// the next line concatenates output
	cout << "Now you have " << carrots << " carrots." << endl;
	return 0;
}
```

**程序调整**

若以前的程序中需要添加cin.get(),此程序需要添加两条，第一条再输入数字并按Enter时读取输入，第二条让程序暂停。

#### 2.3.1 使用cin

```c++
cin >> carrots;
```

信息从cin流向carrots，输入时cin使用>>运算符从输入流中抽取字符，输出时，<<运算符将字符串插入到输出流中

#### 2.3.2 使用cout进行拼接

```c++
cout << "Now you have " << carrots << " carrots." << endl;
```

cout可以进行拼接输出，后一条的输出紧跟前一条输出。

#### 2.3.3 类简介

类是C++中面向对象编程（OOP）的核心概念之一。

类是用户定义的一种数据类型，要顶一类，需要描述他能够表示什么信息和可对数据执行哪些操作。类之于对象就像类型之于变量。也就是说，类定义描述的是数据格式及其用法，而对象则是根据数据格式规范创建的实体。如果说类好比所有著名演员，则对象就好比某个著名演员，我们来扩展这种类比，表示演员的类中包括该类可执行的操作的定义，如念某一角色的台词，表达悲伤、威胁恫吓、接受奖励等。C++类对应于某些语言中的对象类型，而C++对象对应于对象实例或实例变量。

cout是一个ostream类对象，ostream类定义（iostream文件的另一个成员）描述了ostream对象表示的数据以及可以对它执行的操作，如将数字或字符串插入到输出流中。同样，cin是一个istream类对象，也在iostream中定义。

* 类描述了一种数据类型的全部属性（包括可使用它执行的操作），对象是根据这些描述创建的实体

类是用户定义的类型，但用户没有涉及ostream和istream类，像函数可以来自函数库一样，类可以来自类库。他们定义在iostream文件中，并没有被内置在编译器中。

类描述制定了可对类对象执行的所有操作，要对特定对象执行这些允许的操作，需要给该对象发送一条消息，例如对cout发送一个字符串。

### 2.4 函数

函数分为有返回值和没有返回值两种

#### 2.4.1 使用有返回值的函数

有返回值的函数将生成一个值，而这个值可赋给变量或在其他表达式中使用

```c++
x = sqrt(6.25); // returns the value 2.5 and assigns it to x
```

表达式sqrt(6.25)被称为函数调用，被调用的函数叫做被调用函数，包含函数调用的函数叫做调用函数（例如sqrt在main函数中，main函数叫做调用函数），6.25是发送给函数的信息，被称为参数，2.5是sqrt的结果，被称为返回值。函数执行完毕后，语句中的函数调用部分将被替换为返回的值，即x=2.5。

* C++程序应当为程序中使用的每个函数提供原型

函数原型之于函数就像变量声明之于变量————指出设计的类型。例如

```c++
double sqrt(double); // function prototype
```

提供原型的方法有两种

* 在源代码文件中输入函数原型
* 包含头文件cmath(老系统为math.h)，定义了原型

注意：不要混淆函数原型和函数定义。函数原型只描述函数接口，描述的是发送给函数的信息和返回的信息，而函数定义包含了函数的代码。c++将其分开，库文件中包含了函数的编译代码，头文件包含了原型。

```c++
// 2.4 sqrt.cpp -- using the sqrt() function

#include<iostream>
#include<cmath> // or math.h

int main()
{
	using namespace std;

	double area;
	cout << "Enter the floor area, in square feet, of your home: ";
	cin >> area;
	double side;
	side = sqrt(area);
	cout << "That's the equivalent of a square " << side
		<< " feet to the side." << endl;
	cout << "How fascinating!" << endl;
	return 0;
}
```
#### 2.4.2 函数变体

有返回值的函数被称为函数，没有返回值的函数称为过程或子程序，但在C++中，这两种变体都称为函数，例如

```c++
double pow(double, double);
answer = pow(5.0, 8.0);
int rand(void);
myGuess = rand();
void bucks(double);
bucks(1234,56);
```

#### 2.4.3 用户定义的函数

对于库函数，在使用之前必须提供其原型，通常把原型放到main定义之前，但是用户定义的函数必须提供源代码，最简单的方法是将其放在main后面

```c++
// 2.5 ourfunc.cpp -- defining your own function

#include<iostream>
void simon(int); // function prototype for simon()

int main()
{
	using namespace std;
	simon(3); // call the simon() function
	cout << "Pick an integer：";
	int count;
	cin >> count;
	simon(count); // call it again
	cout << "Done!" << endl;
	return 0;
}

void simon(int n) // define the simon() function
{
	using namespace std;
	cout << "Simon says touch your toes " << n << " times." << endl;
}
```

**函数格式**

函数头+花括号中的函数体

```c++
type functionname(argumentlist) // 函数头
{
    statements
}
```

* c++不允许将函数定义嵌套在另一个函数定义中，每个函数定义都是独立的，所有函数的创建都是平等的

```c++
#include<iostream>
using namespace std;

// 函数原型
void simon(int);
double taxes(double);

// 函数1
int main()
{
    ...
    return 0;
}

// 函数2
void simon(int n)
{
    ...
}

// 函数3
double taxes(double t)
{
    ...
    return 2 * t;
}
```

main()函数的返回值为0，计算机操作系统调用程序，main函数的返回值返回给操作系统，很多操作系统都可以使用程序的返回值。例如，UNIX外壳脚本和Windows命令行批处理文件都被设计成运行程序，并测试他们的返回值（通常叫做退出值）。通常的约定是，退出值为0则意味着程序运行成功，为非零意味着存在问题。因此如果C++程序无法打开文件，可以将它设计为返回一个非零值。然后便可以设计一个外壳脚本或批处理文件来运行该程序，如果该程序发出指示失败的消息，则采取其他措施。

**关键字**

前面使用了四个C++关键字：int、void、return和double。这些关键字不能作为他用，即不能当做变量名或者函数名，但可以作为变量名的一部分，例如a_int。

#### 2.4.4 用户定义的有返回值的函数

```c++
// 2.6 convert.cpp -- converts stone to pounds

#include<iostream>
int stonetolb(int); // function prototype

int main()
{
	using namespace std;
	int stone;
	cout << "Enter the weight in stone: ";
	cin >> stone;
	int pounds = stonetolb(stone);
	cout << stone << " stone = ";
	cout << pounds << " pounds." << endl;
	return 0;
}

int stonetolb(int sts)
{
	return 14 * sts;
}
```

函数stonetolb()包含了全部函数特性

* 有函数头和函数体
* 接受一个参数
* 返回一个值
* 需要一个原型

#### 2.4.5 在多函数程序中使用using编译指令

在2.5中，两个函数都包含有using编译指令：using namespace std
第二种方法是将编译指令放在函数外面，且位于两个函数的前面

```c++
// 2.5 ourfunc1.cpp -- defining your own function

#include<iostream>
using namespace std;
void simon(int); // function prototype for simon()

int main()
{
	simon(3); // call the simon() function
	cout << "Pick an integer：";
	int count;
	cin >> count;
	simon(count); // call it again
	cout << "Done!" << endl;
	return 0;
}

void simon(int n) // define the simon() function
{
	cout << "Simon says touch your toes " << n << " times." << endl;
}
```

让程序能够访问名称空间std的方法有多种，例如

* 将using namespace std；放在函数定义之前，让文件中所有的函数都能够使用名称空间std中的所有元素
* 将using namespace std；放在特定的函数中，让该函数能够使用名称空间std的所有元素
* 在特定的函数中使用类似using std::cout的编译指令，只让该函数使用指定的元素cout
* 完全不使用编译指令using，在需要使用名称空间std中的元素时，使用前缀std::，例如 std::cout << "I'm using cout and endl from the std namespace" << std::endl;

**命名约定**

* Myfunction()
* myfunction()
* myFunction()
* my_function()
* my_funct()

### 2.5 总结

C++程序由一个或多个被称为函数的模块组成，程序从main()函数开始。函数由函数头和函数体组成。函数头指出函数的返回值类型和函数期望通过参数传递给他的信息的类型。

**C++语句**

* 声明语句：定义函数使用的变量的名称和类型
* 赋值语句：使用赋值运算符（=）给变量赋值
* 消息语句：将消息发送给对象，激发某种行动
* 函数调用：执行函数。被调用函数执行完毕后，程序返回到函数调用语句后面的语句
* 函数原型：声明函数的返回类型、函数接受的参数数量和类型
* 返回语句：将一个值从被调用的函数那里返回到调用函数中

类是用户定义的数据类型规范，他详细描述了如何表示信息以及可对数据执行的操作。对象是根据类规范创建的实体，就像简单变量是根据数据类型描述创建的实体一样。

C++提供了两个用于处理输入和输出的预定义对象（cin和cout），他们是istream和ostream类的实例，这两个类在iostream文件中定义的。为ostream类定义的插入运算符（<<）使得将数据插入到输出流成为可能；为istream类定义的抽取运算符（>>）能够从输入流中抽取信息。cin和cout都是智能对象，能够根据程序上下文自动将信息从一种形式转换成另一种形式。

C++可以使用大量的C库函数。要使用库函数，应当包含提供该函数原型的头文件。