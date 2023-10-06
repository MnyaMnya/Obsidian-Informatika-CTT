```c++
#include <iostream>
using namespace std;
int FPB(int a, int b){
    int r = 0;
    while(b!=0){
    r = a % b;
    a = b;
    b = r;
    }
    return a;
}
int main(){
    int num1,num2;
    cout << "Ketik Angka Ke-1: ";
    cin >> num1;
    cout << "Ketik Angka Ke-2: ";
    cin >> num2;
    cout <<"FPB nya adalah: "<<FPB(num1,num2);
    cin >> num2;
}
```