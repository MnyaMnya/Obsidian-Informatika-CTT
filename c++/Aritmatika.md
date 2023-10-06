```c++
#include <iostream>
using namespace std;
long double arit(int a,int b,int n)
{
	return n/2 * (2*a + (n-1)*b);
}
int main()
	{
		int a,b,n;
		line1:
		cout << "Ketik nilai suku awal: ";
		cin >> a;
		cout << "Ketik nilai beda: ";
		cin >> b;
		cout << "Ketik nilai suku yang di tanya: ";
		cin >> n;
		cout << "Jawabanya adalah: " << arit (a,b,n) << endl;
		goto line1;
	}
```