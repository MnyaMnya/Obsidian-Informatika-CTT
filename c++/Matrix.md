```c++
#include <iostream>
#include <string.h>
#include <stdlib.h>
#include <windows.h>
using namespace std;
int main(){
    string exit;
    int jumlahBaris,jumlahKolom;
    string operasi;
    line1:
    cout << "Masukkan jumlah baris (Y): ";
    cin >> jumlahBaris;
    cout << "Masukkan jumlah kolom (X): ";
    cin >> jumlahKolom;
    int a[jumlahBaris][jumlahKolom];
    for(int i=0;i<jumlahBaris;i++){
        for (int x=0;x<jumlahKolom;x++){
            cout <<"Masukkan anggota baris ke "<<i+1<<" kolom ke "<<x+1<<": ";
            cin >> a[i][x];
        }
    }
    system("cls");
    for (int i=0;i<jumlahBaris;i++){
        cout << "{";
    for (int x=0;x<jumlahKolom;x++){
        if (x==jumlahKolom-1){
            cout << a[i][x] << "";
        }
        else{
        cout << a[i][x] << ", ";
        }
    }
    
cout << "}" << endl;
}
line2:
cout << "Jenis operasi: invers, tambah" << endl;
cout << "Masukkan jenis operasi: ";
cin >> operasi;
if (operasi == "invers"){
        cout << "Hasilnya adalah: "<< endl;
        for (int i=0;i<jumlahKolom;i++){
        cout << "{";
    for (int x=0;x<jumlahBaris;x++){
        if (x==jumlahBaris-1){
            cout << a[x][i] << "";
        }
        else{
        cout << a[x][i] << ", ";
        }
    }
cout << "}" << endl;
}

}
if (operasi == "tambah") {
        int b[jumlahBaris][jumlahKolom];
        int c[jumlahBaris][jumlahKolom];
        for(int i=0;i<jumlahBaris;i++){
        for (int x=0;x<jumlahKolom;x++){
            cout << "Masukkan anggota baris ke "<<i+1<<" kolom ke "<<x+1<<": ";
            cin >> b[i][x];
            c[i][x]=a[i][x]+b[i][x];
        }
    }
    cout << "Hasilnya adalah :" << endl;
    for (int i=0;i<jumlahBaris;i++){
        cout << "{";
    for (int x=0;x<jumlahKolom;x++){
        if (x==jumlahKolom-1){
            cout << c[i][x] << "";
        }
        else{
        cout << c[i][x] << ", ";
        }
    }
    
cout << "}" << endl;
}
}
else{
        cout << "Input salah";
        system("cls");
        goto line2;
    }
cout <<"apakah mau di lanjutkan?[Y / N]"<<endl;
cout << "Waiting for input: ";
cin >> exit;
if (exit == "y" || exit == "Y"){
    system("cls");
    goto line1;
}
else{
        system("cls");
    return 0;
}
}


```