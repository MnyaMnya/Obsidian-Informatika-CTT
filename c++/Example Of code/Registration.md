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
void six(){
system("cls");
cout << "Password anda salah";
sleep(1);
quit();
}

int main(){
	string user,pass,mypass,reg;
	string cpass,newuser,newlist,newsize;
	string file = "User", other = "Other";
	string uFolder="User\\";
	string oFolder="Other\\";
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
		ssize="1";
	}
	else{}
	int size = stoi(ssize);
	string username[size+1];
	fstream txtuser;
	txtuser.open(oFolder+"user.txt");
	if(!txtuser.is_open()){
		txtuser.close();
		ofstream newlist(oFolder+"user.txt");
		newlist << "default";
		ofstream newuser(uFolder+"default.txt");
		newuser << "1234";
		newlist.close();
		newuser.close();
		txtuser.open(oFolder+"user.txt");
	}
	else{}
	
	for(int i=0;i<size;i++)
	{
		getline(txtuser,line);
		username[i]=line;
	}
	line1:
	cout << "Apakah anda ingin register atau check akun atau melihat list[R/C/L]"<<endl;
	cout << "Ketik Input anda: ";
	cin >> reg;
	system("cls");
	if (reg =="C" || reg=="c")
	{
		linec:
		cout << "Ketik Username anda: ";
		cin >> user;
		for(int i=0;i<size;i++)
		{
		if (user == username[i])
		{
			x=true;
		}
		else{}
		}
		if (x != true){
			system("cls");
			cout << "User Ini Belum Registrasi";
			sleep(2);
			system("cls");
			goto linec;
		}
		else{}
		ifstream txt(uFolder+user+".txt");
		cout << "Ketik Password anda: ";
		cin >> pass;
		getline (txt, mypass);
		if (pass != mypass)
		{
		system("cls");
        system("color 4e");
		six();
		}
		else {
			system("cls");
			cout<< "Username dan password anda benar";
			sleep(2);
			exit(1);
		}
	}
	else if (reg =="R" || reg=="r")
	{
		cout << "Ketik Username anda: ";
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
			cout << "User ini sudah register"<<endl<<"Apakah anda mau mengganti Password? [Y/N]"
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
				cout << "Ketik Password anda: ";
				cin >> pass;
				getline (txt, mypass);
				if (pass != mypass)
				{
					system("cls");
       				system("color 4e");
					six();
				}
				else
				{
					txt.clear();
					txt.seekg(0);
					cout << "Ketik Password Baru anda: ";
					cin >> pass;
					txt <<pass;
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
			cout << "Ketik Password anda: ";
			cin >> pass;
			txt << pass;
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
		cout << "list user yang diregistrasi:"<<"["<<size<<"]" <<endl;
		for(int i=0;i<size;i++)
		{
			cout << username[i]<<endl;
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
	cout << "Login Sukses "<<user<<"!"<< endl;
	sleep(2);
	system("cls");
	quit();
}
```