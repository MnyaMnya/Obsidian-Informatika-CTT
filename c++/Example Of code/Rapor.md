```c++
#include <iostream>
#include <string>
#include <time.h>
#include <math.h>
#include <stdlib.h>
#include <cwchar>
#include <windows.h>
#include <fstream>
#include <unistd.h>
using namespace std;

void quit(){
	 string load;
	 system("cls");
	 load = "Quitting";
	 cout << "\r" << load << flush;
	 sleep (1);
	 load = "Quitting.";
	 cout << "\r" << load << flush;
	 sleep (1);
	 load = "Quitting..";
	 cout << "\r" << load << flush;
	 sleep (1);
	 load = "Quitting...";
	 cout << "\r" << load << flush;
	 sleep (1);
	 exit(1);
}
void wrgpass(){
system("cls");
cout << "Password anda salah";
sleep(1);
quit();
}

int main(){
	string mapel[4]={"Mtk","Biologi","Fisika","Kimia"};
	string user,pass,mypass,reg;
	string cpass,newuser,newlist,newsize;
	string file = "Nilai", other = "Lainya";
	string uFolder="Nilai\\";
	string oFolder="Lainya\\";
	bool x;
	if (CreateDirectoryA(file.c_str(), NULL) ||
    ERROR_ALREADY_EXISTS == GetLastError()){
	}
	else{
		cout <<"Error Failed to Create User Directory";
		sleep(2);
		quit();
	}
	if (CreateDirectoryA(other.c_str(), NULL) ||
    ERROR_ALREADY_EXISTS == GetLastError()){
	}
	else{
		cout <<"Error Failed to Create Other Directory";
		sleep(2);
		quit();
	}
	fstream txtsize(oFolder+"size.txt");
	if(!txtsize.is_open()){
		ofstream newsize(oFolder+"size.txt");
		newsize<<"1";
		newsize.close();
	}
	else{}
	string ssize,line;
	getline (txtsize, ssize);
	if(ssize==""){
		ssize="0";
	}
	else{}
	int size = stoi(ssize);
	string username[size+1];
	fstream txtuser;
	txtuser.open(oFolder+"user.txt");
	if(!txtuser.is_open()){
		txtuser.close();
		ofstream newlist(oFolder+"user.txt");
		newlist.close();
		txtuser.open(oFolder+"user.txt");
	}
	else{}
	
	for(int i=0;i<size;i++)
	{
		getline(txtuser,line);
		username[i]=line;
	}
	line1:
	cout << "Apakah anda ingin Input Nilai atau Print atau melihat list[I/P/L]"<<endl;
	cout << "Ketik Input anda: ";
	cin >> reg;
	system("cls");
	
	if (reg =="I" || reg=="i")
	{
		cout << "Ketik Username yang akan diinput: ";
		cin >> user;
		for(int i=0;i<size;i++)
		{
		if (user == username[i])
		{
			x=true;
		}
		else{}
		}
		if (x == true)
		{
			line2:
			cout << "Siswa ini Sudah memiliki nilai"<<endl<<"Apakah anda mau mengganti nilainya? [Y/N]"
			<<endl<<"Ketik input anda:";
			cin >> cpass;
			system("cls");
			if (cpass == "n" || cpass == "N")
			{
				quit();
			}
			else if (cpass == "y" || cpass == "Y")
			{
				fstream txt(uFolder+user+".txt");
				txt.clear();
				txt.seekg(0);
				for(int index=0;index<4;index++){
				cout << "Ketik Nilai "<<mapel[index]<<" Baru: ";
				cin >> pass;
				txt <<pass<<endl;
				}
			}
			else
			{
				cout << "Input ini tidak bisa dipakai"<<endl;
				sleep(1);
				system("cls");
				goto line2;
			}
			
		}
		else 
		{
			ofstream txt(uFolder+user+".txt");
			for(int index=0;index<4;index++){
				cout << "Ketik Nilai "<<mapel[index]<<" Baru: ";
				cin >> pass;
				txt <<pass<<endl;
				}
			size += 1;
			ofstream txtsizes(oFolder+"size.txt");
			txtsizes<<size;
			txtsizes.close();
			txtuser.close();
			username[size-1]= user;
			txtuser.open(oFolder+"user.txt");
			for(int i=0;i<size;i++)
			{
				txtuser<<username[i]<<endl;
			}
		}
	}
	else if (reg =="L" ||reg=="l")
	{
		cout << "List siswa yang sudah di input:"<<"["<<size<<"]" <<endl;
		for(int i=0;i<size;i++)
		{
			cout << username[i]<<endl;
		}
		cout <<"Nilai Siapa yang mau dicek: ";
		cin >> reg;
		system("cls");
		fstream nl(uFolder+reg+".txt");
		string nilai[4];
		for(int index=0;index<4;index++){
			string ref;
			getline (nl,ref);
			nilai[index]=ref;
		}
		for (int index=0;index<4;index++){
			cout << "Nilai "<<reg<<" Dalam "<<mapel[index]<<" : "<<nilai[index]<<endl;
		}
		cin >> reg;
	}
	else if (reg == "P"|| reg=="p"){
		string nilai[4];
		cout<<"Siswa,Mtk,Biologi,Fisika,Kimia,";
		for(int i=0;i<size;i++){
			cout<<username[i]<<",";
			fstream nl(uFolder+username[i]+".txt");
			for(int index=0;index<4;index++){
				string ref;
				getline (nl,ref);
				nilai[index]=ref;
			}
			for(int index=0;index<3;index++){
				cout << nilai[index]<<",";
			}
			if(i!=size-1)cout << nilai[3]<<",";
			else cout << nilai[3];
			nl.seekg(0);
			nl.close();
		}
		cin >> reg;
	}
	else {
		cout << "Input ini tidak bisa dipakai"<<endl;
		sleep(1);
		system("cls");
		goto line1;
	}
	system("cls");
	cout << "Input Nilai "<<user<<" Sukses!"<< endl;
	sleep(2);
	system("cls");
	quit();
}
```
