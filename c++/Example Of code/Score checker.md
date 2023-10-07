```c++
#include <iostream>
#include <string.h>
using namespace std;


int main() {
    int size,nilai[size];
    int ref,counter=1;
    //int nilai [8] : (81,90,78,97,85,97,97,88);
    cin >> size;
    for (int i=0;i<size;i++){
        cin >> nilai[i];
    }
    for (int i=0;i<size;i++){
        for (int j=i+1;j<size;j++){
            if(nilai[j]<nilai[i]){
                ref = nilai[i];
                nilai[i] = nilai[j];
                nilai[j] = ref;
            }
        }
    }
    for (int i=0;i<size-1;i++){
        if(nilai[size-1]==nilai[i]){
            counter+= 1;
            cout << "counter added"<<endl;
        }
    }
cout << counter;
 cin >> counter;
  return 0;
}
```
