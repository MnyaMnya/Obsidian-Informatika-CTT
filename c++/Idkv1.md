```c++
#include <iostream>
#include <math.h>
using namespace std;
int main(){
    int b,ref,digit,counter,result=0,num,timer=0,z,awal;
    cout << "Ketik Angka Awal: ";
    cin >> awal;
    cout <<"Ketik Nilai Terakhir: ";
    cin >> b;
    for (int i=awal;i<=b;i++){
        bool check=true;
        counter =0;
        int size = 0;
        num = i;
        z=i;
        while(z<0){
            z=z/10;
            timer++;
            counter =timer;
        }
        int y[counter];
        while(num>0){
        ref = num;
        digit=ref%10;
        y[size] = digit;
        size++;
        num = num / 10;
        }
        for(int x=0;x<size-1;x++){
            if(y[x]-y[x+1]==1||y[x+1]-y[x]==1||y[x]-y[x+1]==0||y[x+1]-y[x]==0){
            }
            else{
                check=false;
            }
        }
        if(check == true){
        cout << i<<", ";
        result++;
        }
    }
cout <<endl<< "Jawabanya adalah: "<<result;
cin >> digit;
}
```