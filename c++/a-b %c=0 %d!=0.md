```c++
#include <iostream>
using namespace std;
int main(){
	int i, j, k, l, m;
	line1:
	cout << "Ketik nilai terkecil: ";
	cin >> j;
	cout << "Ketik nilai terbesar: ";
	cin >> i;
	cout << "Ketik nilai pembagi: ";
	cin >> k;
	cout << "Ketik nilai tidak dibagi oleh: ";
	cin >> m;
	l = 0;
	while(i >= j){
		if(i % k == 0){
			l++;
			if (i % m == 0){
				l = l - 1;
			}
			else {
				l = l + 0;
			}
		}
		else{
			l = l + 0;
		}
		i--;
	}
	cout << "Totalnya adalah: " << l << endl;
	goto line1;
}
```