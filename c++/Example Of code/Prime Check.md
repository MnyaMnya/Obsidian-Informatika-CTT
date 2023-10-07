```c++
#include <iostream>
using namespace std;
bool prime(int a)
{
	int i,m,f = 0;
	i = 2;
	m = a / 2;
	while (i <= m)
	{
		i++;
		if (a % i == 0)
		{
			f = 1;
		}
	}
	if (f == 0)
	{
		return true;
	}
}
int main()
{
	int a;
	line1:
	cin >> a;
	if (prime(a)== true)
	{
		cout  << a << ", Adalah bilangan prima" << endl;
	}
	else
	{
		cout << a << "Bukan Bilangan Prima" << endl;
	}
	goto line1;
}
```