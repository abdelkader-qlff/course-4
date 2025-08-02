problem #2:
#include <iostream>
#include <string>
using namespace std;
string readname() {
	string name;
	cout << "enter your name: " << endl;
	getline(cin, name);
	return name;
}
void printname(string name) {
	cout << endl << " your name is: " << name << endl;
}
int main() {
	printname(readname());
}

problem #3:
#include <iostream>
using namespace std;
enum entypeofnumber { odd = 1, even = 2 };
int readnumber(int &number) {
	cout << "enter a number: ";
	cin >> number;
	return number;
}
entypeofnumber checktypenumber(int number) {
	int result = number % 2;
	if (result == 0) 
		return entypeofnumber::even;
	else
		return entypeofnumber::odd;
}
void PrintTypeOfNumber(entypeofnumber typeofnumber) {
	if (typeofnumber == entypeofnumber::even)
		cout << "\nNumber is even\n";
	else
		cout << "\nNumber is odd\n";
}
int main() {
	int number;
	PrintTypeOfNumber(checktypenumber(readnumber(number)));
}

problem #4:
#include <iostream>
using namespace std;
struct strInfo {
	int age;
	bool drivinglicense;
};
strInfo readinfo() {
	strInfo info;
	cout << "Enter your age: ";
	cin >> info.age;
	cout << "Do you have a driver license? ";
	cin >> info.drivinglicense;
	return info;
}
bool comparation(strInfo info) {
	return (info.age >= 18 && info.drivinglicense == 1);
}
void printresult(strInfo info) {
	if (comparation(info)) {
		cout << "\nHired!\n";
	}
	else
		cout << "\nRejecred\n";
}
int main() {
	printresult(readinfo());
}

problem #5:
#include <iostream>
using namespace std;
struct strInfo {
	int age;
	bool drivinglicense;
	string mediation;
};
strInfo readinfo() {
	strInfo info;
	cout << "Enter your age: ";
	cin >> info.age;
	cout << "Do you have a driver license? ";
	cin >> info.drivinglicense;
	cout << "Did you have a mediation?\nAnswer whith yes or no: ";
	cin >> info.mediation;
	return info;
}
bool comparation(strInfo info) {
	return (info.age >= 18 && info.drivinglicense == 1 || info.mediation == "yes");
}
void printresult(strInfo info) {
	if (comparation(info)) {
		cout << "\nHired!\n";
	}
	else
		cout << "\nRejecred\n";
}
int main() {
	printresult(readinfo());
}

problem #6:
#include <iostream>
using namespace std;
struct stname {
	string firstname;
	string lastname;
};
stname readname() {
	stname name;
	cout << "enter your first name: ";
	cin >> name.firstname;
	cout << "enter your last name:";
	cin >> name.lastname;
	return name;
}
string getfullname(stname name) {
	string fullname = "";
	fullname = name.firstname + " " + name.lastname;
	return fullname;
}
void printfullname(string fullname) {
	cout << "\n\tyour full name: " << fullname << endl;
}
int main() {
	printfullname(getfullname(readname()));
}

problem #7:
#include <iostream>
using namespace std;
int readnumber(int &number) {
	cout << "enter a number: ";
	cin >> number;
	return number;
}
void counthalf(int number) {
	int half = 0;
	half = number / 2;
	cout << "the half of " << number << " is " << half;
}
int main() {
	int number;
	counthalf(readnumber(number));
}

problem #8:
