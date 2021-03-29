### 3.6 复习题

##### 1. 为什么C++有多种整型？

有多种整形类型，可以根据特定需求选择最合适的类型。例如，可以使用short来存储空格，使用long来确保存储容量，也可以寻找可提高特定计算的速度的类型。

##### 2. 声明与下述描述相符的变量

* a.short整数，值为80
* unsigned int整数，值为42110
* 值为3000000000的整数

```c++
short rbis = 80; // or short int
unsigned int q = 42110; // or unsigned
unsigned long ants = 3000000000; // or long long
```

##### 3. C++提供了什么措施来防止超出整型的范围？

C++没有提供自动防止超出整型限制的功能，可以使用头文件climits来确定限制情况。

##### 4. 33L与33之间有什么区别？

常量33L为long类型，33类型为int。

##### 5. 下面两条C++语句是否等价？

* char grade = 65；
* char grade = ‘A’；

这两条语句并不真正等价，虽然对于某些系统来说，他们是等效的。最重要的是，只有在使用ASCII码的系统上，第一条语句才将得分设置为字母A，而第二条语句还可用于使用其他编码的系统。其次，65是一个int常量，而‘A’是一个char常量。

##### 6. 如何使用C++来找出编码88表示的字符？指出至少两种方法。

四种方式：
```c++
char c = 88;
cout << c << endl; // char type prints as character

cout.put(char(88)); // put() prints char as character

cout << char(88) << endl; // new-style type cast value to char

cout << (char)88 << endl; // old-style type cast value to char
```

##### 7. 将long值赋给float变量会导致舍入误差，将long值赋给double变量呢？将long long值赋给double变量呢？

这个问题的答案取决于这两个类型的长度。如果long为四个字节，则没有损失。因为最大的long值将是20亿，即有10位数。由于double提供了至少13位有效数字，因而不需要进行任何舍入。long long类型可提供19位有效数字，超过了double保证的13位有效数字。

##### 8. 下列C++表达式的结果分别是多少？

* a. 8 * 9 + 2；
* b. 6 * 3 / 4;
* c. 3 / 4 * 6;
* d. 6.0 * 3 / 4;
* e. 15 % 4;

##### 9. 假设x1和x2是两个double变量，您要将它们作为整数相加，再将结果赋给一个整型变量。请编写一条完成这项任务的C++语句。如果要将他们作为double值相加并转换为int呢？

```c++
int pos = (int)x1 +(int)x2;
int pos = int(x1) + int(x2);

// double类型
int pos = (int)(x1 + x2);
int pos = int(x1 + x2);
```

##### 10. 下面这条语句声明的变量都是什么类型？

* a. auto cars = 15; // int
* b. auto iou = 150.37f; // float
* c. auto level = 'B'; // char
* d. auto crat =  U'/U00002155' // char32_t
* e. auto fract = 8.25f/2.5 // double

### 3.7 编程练习

##### 1

```c++
#include<iostream>
using namespace std;
int main()
{
	const int convert = 12;
	int inch;
	cout << "Please inter your height:_____\b\b\b\b\b";
	cin >> inch;
	cout << "Your height is " << inch / convert << " feet and " << inch % convert << " inches.";
	cout << endl;
	return 0;
}
```

##### 2

```c++
#include<iostream>
using namespace std;
int main()
{
	int feet, inch;
	float pound;
	const int a = 12;
	const float b = 0.0254;
	const float c = 2.2;
	
	cout << "Please inter your height:";
	cin >> feet >> inch;
	//cout << endl;
	cout << "Please inter your weight:";
	cin >> pound;
	//cout << endl;
	cout << "Your height is " << feet * a + inch << " inches. That is to say:" << (feet * a + inch) * b << " meters.\n";
	cout << "Your weight is " << pound / c << " kilograms.\n";
	cout << "Your BMI is " << (pound / c) / ((feet * a + inch) * b) << endl;
	return 0;
}
```

##### 3

```c++
#include<iostream>
using namespace std;
int main()
{
	float degree, minute, second;
	const int a = 60;
	cout << "Enter a latitude in degrees, minutes, and seconds:" << endl;
	cout << "First, enter the degrees: ";
	cin >> degree;
	cout << "Next, enter the minutes of arc: ";
	cin >> minute;
	cout << "Finally, enter the seconds of arc: ";
	cin >> second;
	float latitude = degree + minute / 60 + second / 60 / 60;
	cout << degree << " degrees, " << minute << " minutes, " << second << " seconds = " << latitude << " degrees.\n";
	return 0;
}
```

##### 4

```c++
#include<iostream>
using namespace std;
int main()
{
	long seconds;
	const int day_hour = 24;
	const int hour_minute = 60;
	const int minute_second = 60;
	cout << "Enter the number of seconds: ";
	cin >> seconds;
	int day = seconds / (day_hour * hour_minute * minute_second);
	int hour = seconds % (day_hour * hour_minute * minute_second) / (hour_minute * minute_second);
	int minute = seconds % (day_hour * hour_minute * minute_second) % (hour_minute * minute_second) / 60;
	int second = seconds % 60;
	cout << seconds << " seconds = " << day << " days, "
		<< hour << " hours, " << minute << " minutes," << second << " seconds";
	return 0;
}
```

##### 5

```c++
#include<iostream>
using namespace std;
int main()
{
	long long pop;
	long long Ame_pop;
	cout << "Enter the world's population: ";
	cin >> pop;
	cout << "Enter the population of the US: ";
	cin >> Ame_pop;
	double proportion = Ame_pop * double(100) / pop ;
	cout << "The population of the US is " << proportion << "% of the world population.";
	return 0;
}
```

##### 6

```c++
#include<iostream>
using namespace std;
int main()
{
	double kilometer, litre;
	const int a = 100;
	cout << "Please inter the kilo and litre: ";
	cin >> kilometer >> litre;
	double b = 100 / kilometer * litre;
	cout << "100 kilometers/L:" << b << endl;
	return 0;
}
```

##### 7

```c++
#include<iostream>
using namespace std;
int main()
{
	double eu;
	cout << "Please enter the eu: ";
	cin >> eu;
	double kilo_bai_jialun = eu / 3.875;
	double kilo_bai_mile = 62.41;
	double am = kilo_bai_mile / kilo_bai_jialun;
	cout << "am: ";
	cout << am << endl;
	return 0;
}
```