### 2.6 ��ϰ��

##### 1. C++�����ģ���ʲô��

����

##### 2. �����Ԥ����������ָ������ʲô�õģ�#include< iostream>

�⽫���������յı���֮ǰ��ʹ��iostream�ļ��������滻�ñ���ָ��

##### 3. using namespace std������

��ʹ�ó������ʹ��std���ƿռ��еĶ���

##### 4. ʲô������������ӡ���Hello��world����Ȼ��ʼ�µ�һ�У�

cout << "Hello, world" << endl; ����
cout << "Hello, world\n";

##### 5. ʲô����������������Ϊcheeses������������

int cheeses;

##### 6. ʲô������������ֵ32��������cheeses��

cheeses = 32;

##### 7. ʲô�������������Ӽ��������ֵ�������cheeses�У�

cin >> cheeses;

##### 8. ʲô������������ӡ��We have X varieties of cheese��������XΪ����cheeses�ĵ�ǰֵ��

cout << "We have " << cheeses << " varieties of cheesse";

##### 9. ���溯����ԭ��ָ���˹��ں�������Щ��Ϣ��

```c++
int froop(double t);
void rattle(int n);
int prune(void);
```

�����ķ������ͣ��������������Ĳ���
���ú���froop()ʱ��Ӧ�ṩһ���������ò���������Ϊdouble�����ú���������һ��intֵ��
����rattle()����һ��int������û�з���ֵ��
����prune()�������κβ����ҷ���һ��intֵ��

##### 10. ���庯��ʱ����ʲô����²���ʹ�ùؼ���return��

main������

##### 11. ��������д��main�����������´��룬��������ָ��cout��һ��δ֪��ʶ�����������������ԭ��ܿ�����ʲô��ָ��3���޸���������ķ�����

```c++
cout << "Please enter your PIN: ";
```

��main����֮�����using namespace std
��main����֮�����using std::cout
cout��Ϊstd::cout

### 2.7 �����ϰ

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