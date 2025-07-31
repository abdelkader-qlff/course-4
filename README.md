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
