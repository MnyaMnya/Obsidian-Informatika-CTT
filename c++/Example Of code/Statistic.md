```c++
#include <iostream>
#include <stdlib.h>
using namespace std;
int main(){
    int size;
    float first,interval;
    cout <<"Ketik Ukuran table: ";
    cin >> size;
    float intA[size],intB[size];
    float freq[size];
    cout <<"Ketik nilai awal: ";
    cin >>first;
    cout <<"Ketik nilai interval: ";
    cin >> interval;
    for(int i=0;i<size;i++){
        intA[i]=first+(i*interval);
        intB[i]=intA[i]+interval-1;
        cout<<"Ketik nilai Frekuensi ke ["<<i+1<<"]: ";
        cin >> freq[i];
    }
    float FXi[size];
    float Xi[size];
    float TFXi=0,TFi=0;
    for(int i=0;i<size;i++){
        Xi[i]=intA[i]+((intB[i]-intA[i])/2);
        FXi[i]=freq[i]*Xi[i];
        TFi+=freq[i];
        TFXi+=FXi[i];
    }
    float mean=TFXi/TFi;
    float median;
    int count1=0;
    int Tfiref=TFi/2;
    while(Tfiref>0){
        Tfiref=Tfiref-freq[count1];
        count1++;
    }
    int fk=0;
    for(int i=0;i<count1;i++){
        fk+=freq[i];
    }
    float Quartil[3];
    median = (intA[count1]-0.5)+(interval*(TFi/2-fk)/freq[count1]);
    for(int i=0;i<3;i++){
        int count1=0;
    int Tfiref=TFi*((i+1)/4);
    while(Tfiref>0){
        Tfiref=Tfiref-freq[count1];
        count1++;
    }
    int fk=0;
    for(int i=0;i<count1;i++){
        fk+=freq[i];
    }
    Quartil[i]=(intA[count1]-0.5)+(interval*((TFi*(i+1/4))-fk)/freq[count1]);
    }
    /*For Desil*/
    float Desil[9];
    for(int i=0;i<9;i++){
        int count1=0;
    int Tfiref=TFi*((i+1)/10);
    while(Tfiref>0){
        Tfiref=Tfiref-freq[count1];
        count1++;
    }
    int fk=0;
    for(int i=0;i<count1;i++){
        fk+=freq[i];
    }
    Desil[i]=(intA[count1]-0.5)+(interval*((TFi*(i+1/10))-fk)/freq[count1]);
    }
    /*
    for printing the table;
    */
   system("cls");
   cout <<"No,Interval,Fi,Xi,Fi.Xi,";
   for(int i=0;i<size-1;i++){
    cout<<i+1<<","<<intA[i]<<"-"<<intB[i]<<","<<freq[i]<<","<<Xi[i]<<","<<FXi[i]<<",";
   }
   cout<<size<<","<<intA[size-1]<<"-"<<intB[size-1]<<","<<freq[size-1]<<","<<Xi[size-1]<<","<<FXi[size-1];
   cout <<endl<<"Rata-Rata:"<<mean;
   cout <<endl<<"Median:"<<median;
   for(int i=0;i<3;i++){
    cout <<endl<<"Quartil"<<i+1<<": "<<Quartil[i];
   }
   for(int i=0;i<9;i++){
    cout <<endl<<"Desil"<<i+1<<": "<<Desil[i];
   }
   cin >> size;
}
```