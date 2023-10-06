```c++
#include <iostream>
#include <string.h>
using namespace std;
int main(){
	line1:
	int a,b,ref;
	string bin="";
	cout << "Ketik nilai yang mau di biner kan:";
	cin >> a;
	cout << "Biner basis brp: ";
	cin>>b;
	while (a >= 1){
			ref = a;
			a= a/b;
			back:
			if (ref % b <= b){
					bin =  toHexString(ref%b)+ bin;
				}
				if(ref >= b && ref%b >= b){
					ref= ref/10;
					goto back;
				}
	}
		cout << "Jawabanya adalah: "<<bin<<endl;
		goto line1;
}
```
