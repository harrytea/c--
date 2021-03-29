### 2.6 复习题

##### 1. C++程序的模块叫什么？

函数

##### 2. 下面的预处理器编译指令是做什么用的？#include< iostream>

这将导致在最终的编译之前，使用iostream文件的内容替换该编译指令

##### 3. using namespace std的作用

它使得程序可以使用std名称空间中的定义

##### 4. 什么语句可以用来打印短语“Hello，world”，然后开始新的一行？

cout << "Hello, world" << endl; 或者
cout << "Hello, world\n";

##### 5. 什么语句可以用来创建名为cheeses的整数变量？

int cheeses;

##### 6. 什么语句可以用来将值32赋给变量cheeses？

cheeses = 32;

##### 7. 什么语句可以用来将从键盘输入的值读入变量cheeses中？

cin >> cheeses;

##### 8. 什么语句可以用来打印“We have X varieties of cheese”，其中X为变量cheeses的当前值。

cout << "We have " << cheeses << " varieties of cheesse";

##### 9. 下面函数的原型指出了关于函数的那些信息？

```c++
int froop(double t);
void rattle(int n);
int prune(void);
```

函数的返回类型，函数名，函数的参数
调用函数froop()时，应提供一个参数，该参数的类型为double，而该函数将返回一个int值。
函数rattle()接受一个int参数且没有返回值。
函数prune()不接受任何参数且返回一个int值。

##### 10. 定义函数时，在什么情况下不必使用关键字return？

main函数中

##### 11. 假设您编写的main函数包含如下代码，而编译器指出cout是一个未知标识符。导致这种问题的原因很可能是什么？指出3种修复这种问题的方法。

```c++
cout << "Please enter your PIN: ";
```

在main函数之外加上using namespace std
在main函数之外加上using std::cout
cout变为std::cout

### 2.7 编程练习

##### 1

```c++
// 2.7.1
#include<iostream>

int main()
{
	std::cout << "My name is harry" << std::endl;
	std::cout << "My adress is Qingdao 123" << std::endl;
    return 0;
}
```

##### 2

```c++
// 2.7.2
#include<iostream>
using namespace std;

int main()
{
	int dis;
	cout << "Please enter a distance of long:";
	cin >> dis;
	cout << "After converting, the distance is " << dis * 220 << endl;
    return 0;
}
```

##### 3

```c++
// 2.7.3
#include<iostream>
using namespace std;
void sen1(void);
void sen2(void);

int main()
{
	sen1();
	sen1();
	sen2();
	sen2();
    return 0;
}
void sen1()
{
	cout << "Three blind mice" << endl;
}
void sen2()
{
	cout << "See how they run" << endl;
}
```

##### 4

```c++
// 2.7.4
#include<iostream>
using namespace std;

int main()
{
	int age;
	cout << "Enter your age: ";
	cin >> age;
	cout << "The total month is: " << age * 12;
	return 0;
}
```

##### 5

```c++
// 2.7.5
#include<iostream>
using namespace std;
double convert(int n);

int main()
{
	int celsius;
	cout << "Please enter a Celsius value: ";
	cin >> celsius;
	cout << celsius << " degress Celsius is " << convert(celsius) << " degrees Fahrenheit";
	return 0;
}
double convert(int n)
{
	return 1.8 * n + 32.0;
}
```

##### 6

```c++
// 2.7.6
#include<iostream>
using namespace std;
double convert(double n);

int main()
{
	double light;
	cout << "Enter the number of light years: ";
	cin >> light;
	cout << light << " light years = " << convert(light) << " astronomical units.";
	return 0;
}
double convert(double n)
{
	return n * 63240;
}
```

##### 7

```c++
// 2.7.6
#include<iostream>
using namespace std;
void display(int m, int n);

int main()
{
	int hour, minute;
	cout << "Enter the number of hours: ";
	cin >> hour;
	cout << "Enter the number of minutes: ";
	cin >> minute;
	display(hour, minute);
	return 0;
}
void display(int m, int n)
{
	cout << "Time: " << m << ":" << n;
}
```