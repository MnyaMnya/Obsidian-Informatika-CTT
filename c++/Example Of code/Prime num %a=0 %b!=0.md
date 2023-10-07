```c++
#include <iostream>
using namespace std;
bool prime(int a)
{
	int i,m,f = 0;
	i = 2;
	m = a / 2;
	if (a == 1)
	{
		return false;
	}
	while (i <= m)
	{
		if (a % i == 0)
		{
			f = 1;
		}
		i++;
	}
	if (f == 0)
	{
		return true;
	}
	return false;
}
int main(){
    int numMin,numMax;
    int div,div2,counter;
	cout << "Ketik Nilai Terkecil: ";
    cin >> numMin;
	cout << "Ketik Nilai Terbesar: ";
    cin >> numMax;
	cout << "Bilangan ini Bisa di bagi oleh: ";
	cin >> div2;
	cout << "Bilangan ini tidak bisa dibagi Oleh: ";
    cin >> div;
    for(int i=numMin;i<=numMax;i++){
        if(i%div==0){
        }
        else{
            if(prime(i)==true||i%div2==0){
                counter++;
                cout << i<<", ";
            }
        }
    }
	cout << "Totalnya adalah: "<<counter;
    cin >> div;
}
```