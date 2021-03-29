### 3.6 ��ϰ��

##### 1. ΪʲôC++�ж������ͣ�

�ж����������ͣ����Ը����ض�����ѡ������ʵ����͡����磬����ʹ��short���洢�ո�ʹ��long��ȷ���洢������Ҳ����Ѱ�ҿ�����ض�������ٶȵ����͡�

##### 2. ������������������ı���

* a.short������ֵΪ80
* unsigned int������ֵΪ42110
* ֵΪ3000000000������

```c++
short rbis = 80; // or short int
unsigned int q = 42110; // or unsigned
unsigned long ants = 3000000000; // or long long
```

##### 3. C++�ṩ��ʲô��ʩ����ֹ�������͵ķ�Χ��

C++û���ṩ�Զ���ֹ�����������ƵĹ��ܣ�����ʹ��ͷ�ļ�climits��ȷ�����������

##### 4. 33L��33֮����ʲô����

����33LΪlong���ͣ�33����Ϊint��

##### 5. ��������C++����Ƿ�ȼۣ�

* char grade = 65��
* char grade = ��A����

��������䲢�������ȼۣ���Ȼ����ĳЩϵͳ��˵�������ǵ�Ч�ġ�����Ҫ���ǣ�ֻ����ʹ��ASCII���ϵͳ�ϣ���һ�����Ž��÷�����Ϊ��ĸA�����ڶ�����仹������ʹ�����������ϵͳ����Σ�65��һ��int����������A����һ��char������

##### 6. ���ʹ��C++���ҳ�����88��ʾ���ַ���ָ���������ַ�����

���ַ�ʽ��
```c++
char c = 88;
cout << c << endl; // char type prints as character

cout.put(char(88)); // put() prints char as character

cout << char(88) << endl; // new-style type cast value to char

cout << (char)88 << endl; // old-style type cast value to char
```

##### 7. ��longֵ����float�����ᵼ����������longֵ����double�����أ���long longֵ����double�����أ�

�������Ĵ�ȡ�������������͵ĳ��ȡ����longΪ�ĸ��ֽڣ���û����ʧ����Ϊ����longֵ����20�ڣ�����10λ��������double�ṩ������13λ��Ч���֣��������Ҫ�����κ����롣long long���Ϳ��ṩ19λ��Ч���֣�������double��֤��13λ��Ч���֡�

##### 8. ����C++���ʽ�Ľ���ֱ��Ƕ��٣�

* a. 8 * 9 + 2��
* b. 6 * 3 / 4;
* c. 3 / 4 * 6;
* d. 6.0 * 3 / 4;
* e. 15 % 4;

##### 9. ����x1��x2������double��������Ҫ��������Ϊ������ӣ��ٽ��������һ�����ͱ��������дһ��������������C++��䡣���Ҫ��������Ϊdoubleֵ��Ӳ�ת��Ϊint�أ�

```c++
int pos = (int)x1 +(int)x2;
int pos = int(x1) + int(x2);

// double����
int pos = (int)(x1 + x2);
int pos = int(x1 + x2);
```

##### 10. ����������������ı�������ʲô���ͣ�

* a. auto cars = 15; // int
* b. auto iou = 150.37f; // float
* c. auto level = 'B'; // char
* d. auto crat =  U'/U00002155' // char32_t
* e. auto fract = 8.25f/2.5 // double

### 3.7 �����ϰ

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