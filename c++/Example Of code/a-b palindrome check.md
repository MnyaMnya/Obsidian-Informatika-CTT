```c++
#include <iostream>
using namespace std;

bool isPalindrome(int num)
{
	int ref = 0, digit, n;
	n = num;
	do
	{
		digit = num % 10;
		ref = (ref * 10) + digit;
		num = num / 10;
	} 
	while (num != 0);
	if (n == ref)
	{
		return true;
	}
	else
	{
		return false;
	}
}
int main()
{
	line1:
	int x,y,z=0,i = 0;
	cout << "Ketik nilai awal: ";
	cin >> x;
	cout << "Ketik nilai akhir: ";
	cin >> y;
	while (x <= y )
	{
		if (isPalindrome(x) == true)
		{
			z++;
			i = i + x;
			cout << x << ", ";
		}
		x++;
	}
	cout << endl << "Totalnya adalah: " << z <<endl;
	cout << "Jumlan nilai nya adalah: " << i << endl;
	goto line1;
}
```