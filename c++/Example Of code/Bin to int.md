```c++
#include <iostream>
#include <string.h>
#include <math.h>
using namespace std;
int main (){
	long int a,b,res=0,bpi;
	char bin[20];
	line1:
	cout << "Ketik Nilai Binary: ";
	cin >> bin;
	cout << "Biner basis brp: ";
	cin >> b;
	
	a = strlen(bin);
	int x = a-1;
	for (int i=0;i<=a-1;i++){
		if (bin[x]== '1'){
			bpi = pow(b,i);
			res = res + bpi;
			}
			x--;
		}
		cout << "Jawabanya adalah: "<< res << endl;
		goto line1;
}
```