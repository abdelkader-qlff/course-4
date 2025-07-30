problem 2:
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

problem 3:
