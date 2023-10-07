```c++
#include <iostream>
#include <string.h>
#include <cctype>
using namespace std;
int main(){
int counter=0;
char txt[5000],checker,ucheck,lcheck;
cout << "Ketik Textnya: ";
cin >> txt;
cout << "Ketik Huruf yang mau dicari: ";
cin >> checker;
ucheck = toupper(checker);
lcheck = tolower(checker);
int len = strlen(txt);
for (int i=0;i<len;i++){
    if(txt[i]==ucheck ||txt[i]== lcheck ){
        counter++;
    }
}
cout << "Jumlah Huruf ["<<ucheck<<"] Yang ada di textnya ada ("<<counter<<")";
cin >> txt;
}

```
