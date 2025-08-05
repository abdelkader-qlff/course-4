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
1-first way:
#include <iostream>
using namespace std;
int readmark() {
	int mark;
	cout << "enter your mark: ";
	cin >> mark;
	return mark;
}
bool comparation(int mark) {
	return mark >= 50;
}
void result(int mark) {
	if (comparation(mark))
		cout << "Pass!";
	else
		cout << "Fail!";
}
int main() {
	result(readmark());
}
2-second way:
#include <iostream>
using namespace std;
enum enpassfail { pass = 1, fail = 0 };
int readmark(int &mark) {
	cout << "enter your mark: ";
	cin >> mark;
	return mark;
}
enpassfail checkmark(int mark) {
	if (mark >= 50)
		return enpassfail::pass;
	else
		return enpassfail::fail;
}
void printmark(int mark) {
	if (checkmark(mark) == enpassfail::pass)
		cout << "Pass!";
	else
		cout << "Fail!";
}
int main() {
	int mark;
	printmark(readmark(mark));
}

problem #9:
#include <iostream>
using namespace std;
struct numbers {
	int num1, num2, num3;
};
numbers readnumbers() {
	numbers number;
	cout << "enter first number: ";
	cin >> number.num1;
	cout << "enter second number: ";
	cin >> number.num2;
	cout << "enter last number: ";
	cin >> number.num3;
	return number;
}
int count(numbers number) {
	int result = 0;
	result = number.num1 + number.num2 + number.num3;
	return result;
}
void printsum(int result) {
	cout << "\nsum numbers: " << result << endl;
}
int main() {
	printsum(count(readnumbers()));
}

problem #10:
#include <iostream>
#include <cmath>
using namespace std;
void readmarks(int& mark1, int& mark2, int& mark3) {
	cout << "enter your first mark: ";
	cin >> mark1;
	cout << "enter second mark: ";
	cin >> mark2;
	cout << "enter third mark: ";
	cin >> mark3;
}
float calculateaverage(int mark1, int mark2, int mark3) {
	return (float)(mark1 + mark2 + mark3) / 3;
}
void printaverage(float average) {
	cout << "your average marks: " << average << endl;
}
int main() {
	int mark1, mark2, mark3; 
	readmarks(mark1, mark2, mark3);
	printaverage(calculateaverage(mark1, mark2, mark3));
}

problem #11:
#include <iostream>
using namespace std;
enum enpassfail { pass = 1, fail = 0 };
void readmarks(int& mark1, int& mark2, int& mark3) {
	cout << "enter your first mark: ";
	cin >> mark1;
	cout << "enter second mark: ";
	cin >> mark2;
	cout << "enter third mark: ";
	cin >> mark3;
}
int summarks(int mark1, int mark2, int mark3) {
	return mark1 + mark2 + mark3;
}
float calculateaverage(int mark1, int mark2, int mark3) {
	return (float)summarks(mark1,mark2,mark3) / 3;
}
enpassfail checkaverage(float average) {
	if (average >= 50)
		return enpassfail::pass;
	else
		return enpassfail::fail;
}
void printaverage(float average) {
	cout << "\n\tyour average is: " << average << endl;
	if (checkaverage(average) == enpassfail::pass)
		cout << "\nPass!\n";
	else
		cout << "\nFail!\n";
}
int main() {
	int mark1, mark2, mark3;
	readmarks(mark1, mark2, mark3);
	printaverage(calculateaverage(mark1,mark2,mark3));
}

problem #12:
#include <iostream>
#include <cmath>
using namespace std;
void readnum(int& num1, int& num2) {
	cout << "enter number 1: \n";
	cin >> num1;
	cout << "enter number 2: \n";
	cin >> num2;
}
int comparation(int num1, int num2) {
	return num1 > num2;
}
void printresult(int num1, int num2) {
	if (comparation(num1,num2))
		cout << "the first number is greater than the second number\n";
	else
		cout<< "the second number is greater than the first number\n";
}
int main() {
	int num1, num2;
	readnum(num1, num2);
	comparation(num1, num2);
	printresult(num1,num2);
}

problem #13:
#include <iostream>
#include <cmath>
using namespace std;
void readnums(int& num1, int& num2, int& num3) {
	cout << "enter number 1:\n";
	cin >> num1;
	cout << "enter number 2:\n";
	cin >> num2;
	cout << "enter number 3:\n";
	cin >> num3;
}
int comparation(int num1, int num2, int num3) {
	if (num1 >= num2 && num1 >= num3)
		return num1;
	else if (num2 >= num1 && num2 >= num3)
		return num2;
	else
		return num3;
}
void printresult(int max) {
	cout << "\nthe greater number is: " << max << endl;
}
int main() {
	int num1,num2,num3;
	readnums(num1, num2, num3);
	printresult(comparation(num1, num2, num3));
}

problem #14:
#include <iostream>
using namespace std;
void readnums(int& num1, int& num2) {
	cout << "enter the first number: \n";
	cin >> num1;
	cout << "enter the second number: \n";
	cin >> num2;
}
void swapnums(int& A, int& B) {
	/*int num1{}, num2{};*/
	int temp = A;
	A = B;
	B = temp;
}
void printswapnums(int num1, int num2) {
	cout << "The result of swap numbers: \nnumber 1 = " << num1 << endl << "number 2 = " << num2 << endl;
}
int main() {
	int num1, num2;
	readnums(num1, num2);
	printswapnums(num1, num2);
	swapnums(num1, num2);
	printswapnums(num1, num2);
}

problem #15:
#include <iostream>
using namespace std;
void readinfo(int& A, int& B) {
	cout << "enter A: ";
	cin >> A;
	cout << "enter B: ";
	cin >> B;
}
int countrectanglearea(int A, int B) {
	return A * B;
}
void printresult(int area) {
	;
	cout << "\n\tThe rectangle area: " << area << endl;
}
int main() {
	int A, B; 
 	readinfo(A, B);
	printresult(countrectanglearea(A, B));
}

problem #16:
