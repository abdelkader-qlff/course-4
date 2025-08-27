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
#include <iostream>
#include <cmath>
using namespace std;
void readinfo(int& a, int& d) {
	cout << "enter the side of rectangle: ";
	cin >> a;
	cout << "enter tje diagonal of rectangle: ";
	cin >> d;
}
float countrectanglearea(int a, int d) {
	return a * sqrt(pow(d, 2) - pow(a, 2));
}
void printresult(float area) {
	cout << "\n\tThe rectangle area: " << area << endl;
}
int main() {
	int a,d; 
	readinfo(a,d);
	printresult(countrectanglearea(a,d));
}

problem #18:
#include <iostream>
#include <cmath>
using namespace std;
void readinfo(int& r) {
	cout << "enter r: \n";
	cin >> r;
}
float calculatecirlearea(int r) {
	const float PI = 3.14;
	float area = PI * pow(r, 2);
	return area;
}
void printcirclearea(float area) {
	cout << "\nThe circle area is: " << area << endl;
}
int main() {
	int r, area;
	readinfo(r);
	printcirclearea(calculatecirlearea(r));
}

problem #19:
#include <iostream>
#include <cmath>
using namespace std;
void readinfo(int& D) {
	cout << "enter D: \n";
	cin >> D;
}
float calculatecirlearea(int D) {
	const float PI = 3.14;
	float area = (PI * pow(D, 2)) / 4;
	return area;
}
void printcirclearea(float area) {
	cout << "\nThe circle area is: " << area << endl;
}
int main() {
	int r, area;
	readinfo(r);
	printcirclearea(calculatecirlearea(r));
}

problem #20:
#include <iostream>
using namespace std;
float readinfo() {
	int A;
	cout << "enter A: \n";
	cin >> A;
	return A;
}
float calculatecircleareabysquare(int A) {
	const float PI = 3.1415;
	float circlearea = (PI * pow(A, 2)) / 4;
	return circlearea;
}
void printcirclearea(float circlearea) {
	cout << "\n\tThe circle area inscribed in a square: " << circlearea << endl;
}
int main() {
	printcirclearea(calculatecircleareabysquare(readinfo()));
}

problem #21:
#include <iostream>
using namespace std;
#include <iostream>
#include <cmath>
using namespace std;
int readinfo() {
	int L;
	cout << "enter L: \n";
	cin >> L;
	return L;
}
float calculatecirclearea(int L) {
	const float PI = 3.1415;
	float circlearea = pow(L, 2) / (4 * PI);
	return circlearea;
}
void printresult(float area) {
	cout << "\n\tCircle area along the circumference: " << area << endl;
}
int main() {
	printresult(calculatecirclearea(readinfo()));
}

problem #22:
#include <iostream>
#include <cmath>
using namespace std;
void readinfo(int& A,int& B) {
	cout << "enter A: \n";
	cin >> A;
	cout << "enter B: \n";
	cin >> B;
}
float calculatecirclearea(float A, float B) {
	const float PI = 3.1415;
	float circlearea = PI * (pow(B,2)/4)*((2*A-B)/(2*A+B));
	return circlearea;
}
void printresult(float area) {
	cout << "\n\tCircle area inscribed in an isosceles triangle: " << area << endl;
}
int main() {
	int A, B;
	readinfo(A, B);
	printresult(calculatecirclearea(A,B));
}

problem #23:
#include <iostream>
#include <cmath>
using namespace std;
void readinfo(float& A, float& B, float& C) {
	cout << "enter A: \n";
	cin >> A;
	cout << "enter B: \n";
	cin >> B;
	cout << "enter C: \n";
	cin >> C;
}
float calculatecirclearea(float A, float B,float C) {
	const float PI = 3.1415;
	float p = (A + B + C) / 2;
	float area = PI * pow((A * B * C) / (4 * sqrt(p * (p - A) * (p - B) * (p - C))),2);
	return area;
}
void printresult(float area) {
	cout << "\n\tCircle area inscribed in an isosceles triangle: " << area << endl;
}
int main() {
	float A,B,C;
	readinfo(A, B, C);
	printresult(calculatecirclearea(A,B,C));
}

problem #24:


problem #25:
#include <iostream>
using namespace std;
int readage(int& age) {
	cout << "enter your age(must be between 18 and 45):\n";
	cin >> age;
	return age;
}
bool checkage(int age, int from, int to) {
	return age >= from && age <= to;
}
int loopchecking(int from, int to) {
	int age = 0;
	do {
		age = readage(age);
	} while (!checkage(age, from, to));
	return age;
}
void printage(int age) {
	cout << "\n\tyour age: " << age << endl;
}
int main() {
	printage(loopchecking(18, 45));
}

problem #26:
#include <iostream>
using namespace std;
int readnumber(int &N) {
	cout << "enter a number: \n";
	cin >> N;
	return N;
}
void from1toNbyfor(int N) {
	cout << "with for loop:\n";
	for (int i = 1; i <= N; i++) {
		cout << i << endl;
	}
}
void from1toNbywhile(int N) {
	int i = 1;
	cout << "with while loop:\n";
	while (i <= N) {
		cout << i << endl;
		i++;
	}
}
void from1toNbydowhile(int N) {
	int i = 1;
	cout << "with do while loop:\n";
	do {
		cout << i << endl;
		i++;
	} while (i <= N);
}
int main() {
	int N;
	readnumber(N);
	from1toNbyfor(N);
	from1toNbywhile(N);
	from1toNbydowhile(N);
}

problem #27:
#include <iostream>
using namespace std;
enum enoddoreven { odd = 1, even = 2 };
void readnum(int& N) {
	cout << "enter your number: ";
	cin >> N;
}
enoddoreven checkoddoreven(int N) {
	if (N % 2 != 0)
		return enoddoreven::odd;
	else
		return enoddoreven::even;
}
void sumoddnumberbyfor(int N) {
	int sum = 0;
	cout << "\tsum odd numbers by for loop: ";
	for (int i = 1; i < N; i++) {
		if (checkoddoreven(i) == enoddoreven::odd)
			sum += i;
	}
	cout << sum << endl;
}
void sumoddnumbersbywhile(int N) {
	int i = 0;
	int sum = 0;
	cout << "\tsum odd numbers by while loop: ";
	while (i < N) {
		i++;
		if (checkoddoreven(i) == enoddoreven::odd)
			sum += i;
	}
	cout << sum << endl;
}
void sumoddnumbersbydowhile(int N) {
	int i = 0;
	int sum = 0;
	cout << "\tsum odd numbers by do while loop: ";
	do {
		i++;
		if(checkoddoreven(i)==enoddoreven::odd)
			sum += i;
	} while (i < N);
	cout << sum << endl;
}
int main() {
	int N;
	readnum(N);
	sumoddnumberbyfor(N);
	sumoddnumbersbywhile(N);
	sumoddnumbersbydowhile(N);
}

problem #28:
#include <iostream>
using namespace std;
enum enoddoreven { odd = 1, even = 2 };
int readnum() {
	int N;
	cout << "enter a number: ";
	cin >> N;
	return N;
}
enoddoreven checknum(int N) {
	if (N % 2 == 0)
		return enoddoreven::even;
	else
		return enoddoreven::odd;
}
void sumevennumsbyfor(int N) {
	int sum = 0;
	cout << "sum of even numbers by for loop: ";
	for (int counter = 0; counter < N; ) {
		counter++;
		if (checknum(counter) == enoddoreven::even) {
			sum += counter;
		}
	}
	cout << sum << endl;
}
void sumevennumsbywhile(int N) {
	int sum = 0;
	int counter = 0;
	cout << "sum of even numbers by while loop: ";
	while (counter < N) {
		counter++;
		if (checknum(counter) == enoddoreven::even) {
			sum += counter;
		}
	}
	cout << sum << endl;
}
void sumevennumsbydowhile(int N) {
	int sum = 0;
	int counter = 0;
	cout << "sum of even numbers by do while loop: ";
	do {
		counter++;
		if (checknum(counter) == enoddoreven::even)
			sum += counter;
	} while (counter < N);
	cout << sum << endl;
}
int main() {
	int N = readnum();
	sumevennumsbyfor(N);
	sumevennumsbywhile(N);
	sumevennumsbydowhile(N);
}

problem #30:
#include <iostream>
using namespace std;
enum enoddoreven { odd = 1, even = 2 };
int readnum() {
	int N;
	do {
		cout << "enter a number: ";
		cin >> N;
	} while (N <= 0);
	return N;
}
void sumevennumsbyfor(int N) {
	int factorial = 1;
	cout << "factorial of numbers by for loop: ";
	for (int counter = N; counter >= 1; counter--) {
		factorial *= counter;
	}
	cout << factorial << endl;
}
void sumevennumsbywhile(int N) {
	int factorial= 1;
	int counter = 0;
	cout << "factorial of numbers by while loop: ";
	while (counter < N) {
		counter++;
		factorial *= counter;
	}
	cout << factorial << endl;
}
void sumevennumsbydowhile(int N) {
	int factorial = 1;
	int counter = 0;
	cout << "factorial of numbers by do while loop: ";
	do {
		counter++;
		factorial *= counter;
	} while (counter < N);
	cout << factorial << endl;
}
int main() {
	int N = readnum();
	sumevennumsbyfor(N);
	sumevennumsbywhile(N);
	sumevennumsbydowhile(N);
}

problem #31:
#include <iostream>
using namespace std;
int readnumber(int& N) {
	cout << "enter a number: ";
	cin >> N;
	return N;
}
int powof2(int N) {
	return N * N;
}
void powof3(int N) {
	int pow = N * N * N;
	cout << N << " power 3 is: " << pow << endl;
}
int powof4(int N) {
	return N * N * N * N;
}
int main() {
	int N;
	readnumber(N);
	
	cout << N << " power 2 is: " << powof2(N) << endl;
	powof3(N);
	cout << N << " power 4 is: " << powof4(N) << endl;
}

problem #32:
#include <iostream>
using namespace std;
void readnumber(int& N,int& M) {
	cout << "enter a number: ";
	cin >> N;
	cout << "enter M: ";
	cin >> M;
}
int powofM(int N,int M) {
	int count = 1;
	while (M >= 1) {
		count *= N;
		M--;
	}
	return count;
}
int main() {
	int N,M;
	readnumber(N,M);
	cout << N << " power " << M << " is: " << powofM(N,M) << endl;
}

problem #34:
#include <iostream>
using namespace std;
//int readgrade(int& grade) {
//	cout << "enter your grade: ";
//	cin >> grade;
//	return grade;
//}
int rangeofgrades(int from, int to) {
	int grade;
	do {
		cout << "put a grade between 0 to 100: ";
		cin >> grade;
	} while (grade < from || grade > to);
	return grade;
}
char translategradetoword(int grade) {
	//if (grade > 100 || grade < 0) {
	//	cout << "wrong\nTry again: ";
	//	cin >> grade;
	//}
	if (grade == 100) 
		return 'A';
	else if (grade >= 90)
		return 'B';
	else if (grade >= 80)
		return 'C';
	else if (grade >= 70)
		return 'D';
	else if (grade >= 50)
		return 'E';
	else if (grade >= 0 && grade <= 50)
		return 'F';
}
void printgrade(char chargrade) {
	cout << "\n\tyour grade is: " << chargrade << endl;
}
int main() {
	int grade,from,to; 
	/*readgrade(grade);*/
	/*rangeofgrades(0,100);
	char(translategradetoword(grade));
	printgrade(translategradetoword(grade));*/
	printgrade(translategradetoword(rangeofgrades(0, 100)));
}

problem #35:
#include <iostream>
#include <cmath>
using namespace std;
int readtotalsales() {
	int sales;
	cout << "enter your total sales amount: ";
	cin >> sales;
	return sales;
}
float calculatewithpercentage(float sales) {
	if (sales >= 1000000)
		return (sales * 1) / 100;
	else if (sales >= 500000)
		return (sales * 2) / 100;
	else if (sales >= 100000)
		return (sales * 3) / 100;
	else if (sales >= 50000)
		return (sales * 5) / 100;
	else
		return (sales * 0) / 100;
}
float printtotalcomission(float sales) {
	cout << "\n\ttotal comission: " << sales << endl;
	return sales;
}
int main() {
	float sales = readtotalsales();
	printtotalcomission(calculatewithpercentage(sales));
}

problem #36:
#include <iostream>
using namespace std;
void readinfo(int& num1, int& num2, char& operationtype) {
	cout << "enter number 1: ";
	cin >> num1;
	cout << "enter number 2: ";
	cin >> num2;
	cout << "enter the operation type: ";
	cin >> operationtype;
}
char operationtypechoice(char operationtype) {
	if (operationtype == '+')
		return '+';
	else if (operationtype == '-')
		return '-';
	else if (operationtype == '*')
		return '*';
	else
		return '/';
}
void printresultofcalculation(int num1, int num2, char operationtype) {
	double result = 0;
	switch (operationtype) {
	case '+':
		result = num1 + num2;
		break;
	case '-':
		result = num1 - num2;
		break;
	case '*':
		result = num1 * num2;
		break;
	case '/':
		if (num2 != 0)
			result = num1 / num2;
		else
			cout << "Error!\nDevision by zero!\n";
		break;
	default:
		cout << "Invalid operation\n" << result;
	}
	cout << "\n\tThe result: " << result << endl;
}
int main() {
	int num1, num2;
	char operationtype;
	readinfo(num1,num2,operationtype);
	operationtypechoice(operationtype);
	printresultofcalculation(num1, num2,operationtype);
}

other solution:
#include <iostream>
using namespace std;
float readinfo(string message) {
	int number;
	cout << message;
	cin >> number;
	return number;
}
enum enoperationtype { Add = '+', subtract = '-', multiply = '*', devide = '/' };
enoperationtype readopty() {
	char opty = '+';
	cout << "enter an operation type(+,-,*,/): ";
	cin >> opty;
	return (enoperationtype)opty;
}
float calculation(float number1, float number2, enoperationtype opty) {
	switch (opty) {
	case enoperationtype::Add:
		return number1 + number2;
	case enoperationtype::subtract:
		return number1 - number2;
	case enoperationtype::multiply:
		return number1 * number2;
	default:
		return number1 / number2;
	}
}
int main() {
	float number1 = readinfo("enter your first number: ");
	float number2 = readinfo("enter the second number:");
	enoperationtype opty = readopty();
	cout << "\n\tthe result: " << calculation(number1, number2, opty);
}


problem #37:
#include <iostream>
using namespace std;
void readnumbers(int& numbers) {
	cout << "enter number ";
	
	/*return numbers;*/
}
float calculateresult(int numbers) {
	int x = -99;
	float sum = 0;
	int num = 1;
	while (numbers != -99) {
		if (numbers != -99)
			sum += numbers;
		readnumbers(numbers);
		cout << num++ << " : ";
		cin >> numbers;
	}
	return sum;
}
void printresult() {
	int numbers{};
	cout << endl << "\tThe result: " << calculateresult(numbers) << endl;
}
int main() {
	printresult();
}

problem #38:
#include <iostream>
#include <string>
using namespace std;
enum enprimenotprime { Impair = 1, Pair = 2 };
int readnums(string message) {
	int number;
	cout << message << endl;
	cin >> number;
	return number;
}
enprimenotprime checknums(int number) {
	//int M = round(number / 2);
	for (int counter = 2; counter <= number; counter++) {
		if (number % counter == 0)
			return enprimenotprime::Pair;
		else
			return enprimenotprime::Impair;
	}
}
void printresult(int number) {
	switch (checknums(number)) {
	case enprimenotprime::Impair:
		cout << "\n\tthe number is Impair\n";
		break;
	case enprimenotprime::Pair:
		cout << "\n\tthe number is Pair";
		break;
	}
}
int main() {
	printresult(readnums("enter your number: "));
}

problem #39:
#include <iostream>
#include <string>
using namespace std;
int readnum(string message) {
	int number;
	cout << message << endl;
	cin >> number;
	return number;
}
float calculatepaidback(int number1, int number2) {
	return number1 - number2;
}
void printresult(float paidback) {
	cout << "\n\tPaid Back: " << paidback << endl;
}
int main() {
	int number1 = readnum("enter Total Bill number: ");
	int number2 = readnum("enter Cash Paid number: ");

	printresult(calculatepaidback(number1, number2));
}

problem #39:
#include <iostream>
#include <string>
using namespace std;
int readnum(string message) {
	int number;
	do {
		cout << message << endl;
		cin >> number;
	} while (number <= 0);
	return number;
}
float calculatepaidback(int number1, int number2) {
	return number2 - number1;
}
void printresult(float paidback) {
	cout << "\n\tPaid Back: " << paidback << endl;
}
int main() {
	int number1 = readnum("enter Total Bill: ");
	int number2 = readnum("enter Cash Paid: ");

	cout << "***************" << endl;
	cout << "Total Bill: " << number1 << endl;
	cout << "Total Cash: " << number2 << endl;
	cout << "***************" << endl;

	printresult(calculatepaidback(number1, number2));
}

problem #40:
#include <iostream>
#include <string>
using namespace std;
int readinfo(string message) {
	int billvalue;
	do {
		cout << message << endl;
		cin >> billvalue;
	} while (billvalue <= 0);
	return billvalue;
}
float calculateservicefee(int billvalue) {
	float servicefee = (billvalue * 10) / 100;
	return servicefee;
}
float calculatesalestax(int billvalue) {
	float salestax = ((billvalue + calculateservicefee(billvalue)) * 16) / 100;
	return salestax;
}
float calculatebillvalue(int billvalue) {
	return billvalue + calculateservicefee(billvalue) + calculatesalestax(billvalue);
}
void printtotalbillvalue(int billvalue) {
	cout << "\n\tTotal Bill Value: " << calculatebillvalue(billvalue) << endl;
}
int main() {
	int billvalue = readinfo("enter Bill Value: ");
	printtotalbillvalue(billvalue);
}

problem #41:
#include <iostream>
#include <string>
using namespace std;
int readnumberofhours(string message) {
	int numberofhours;
	do {
		cout << message;
		cin >> numberofhours;
	} while (numberofhours <= 0);
	return numberofhours;
}
float calculatenumberofweeks(float numberofhours) {
	return numberofhours / 24 / 7;
}
float calculatenumberofdays(float numberofhours) {
	return numberofhours / 24;
}
void printdaysandweeks(float numberofhours) {
	cout << "************************" << endl;
	cout << "Total Of Hours: " << numberofhours << endl;
	cout << "Total Of Weeks: " << calculatenumberofweeks(numberofhours) << endl;
	cout << "Total Of Days: " << calculatenumberofdays(numberofhours) << endl;
	cout << "************************" << endl;
}
int main() {
	int numberofhours = readnumberofhours("enter the number of hours: ");
	printdaysandweeks(numberofhours);
}

problem #42:
#include <iostream>
#include <string>
using namespace std;
int enterduration(string message) {
	int duration = 0;
	do {
		cout << message;
		cin >> duration;
	} while (duration <= 0);
	return duration;
}
float calculatedaystoseconds(int days) {
	return days * 60 * 60 * 24;
}
float calculatehourstoseconds(int hours) {
	return hours * 60 * 60;
}
float calculateminutestoseconds(int minutes) {
	return minutes * 60;
}
float calculateseconds(int seconds) {
	return seconds;
}
void printtotalseconds(int days,int hours,int minutes,int seconds) {
	int totalduration = calculatedaystoseconds(days)
		+ calculatehourstoseconds(hours)
		+ calculateminutestoseconds(minutes)
		+ calculateseconds(seconds);
	cout << "\n\tTotal Of Seconds: " << totalduration << endl;
}
int main() {
	int days = enterduration("enter total of days: ");
	int hours = enterduration("enter total of hours: ");
	int minutes = enterduration("enter total of minutes: ");
	int seconds = enterduration("enter total of seconds: ");
	printtotalseconds(days,hours,minutes,seconds);
}

other solution:
#include <iostream>
#include <string>
using namespace std;
struct sttimes{int numofseconds,numofminutes,numofhours,numofdays;};
int readpositivenum(string message) {
	int number;
	do {
		cout << message;
		cin >> number;
	} while (number <= 0);
	return number;
}
sttimes sttransfertnums() {
	sttimes times;
	times.numofseconds = readpositivenum("Enter number of seconds: ");
	times.numofminutes = readpositivenum("Enter number of minutes: ");
	times.numofhours = readpositivenum("Enter number of hours: ");
	times.numofdays = readpositivenum("Enter number of days: ");
	
	return times;
}
int totalduration(sttimes times) {
	int durationinseconds = 0;
	durationinseconds += times.numofseconds;
	durationinseconds += times.numofminutes * 60;
	durationinseconds += times.numofhours * 60 * 60;
	durationinseconds += times.numofdays * 60 * 60 * 24;

	return durationinseconds;
}
int main() {
	cout << "\n\tThe total duration is: " << totalduration(sttransfertnums()) << endl;
}

problem #43:
#include <iostream>
#include <string>
using namespace std;
struct sttimes { int numofdays, numofhours, numofminutes, numofseconds; };
int readpositivenum(string message) {
	int number;
	do {
		cout << message;
		cin >> number;
	} while (number <= 0);
	return number;
}
sttimes sttransfertnums(int totalseconds) {
	sttimes times;
	const int secondsperdays = 24 * 60 * 60;
	const int secondsperhours = 60 * 60;
	const int secondsperminutes = 60;

	int remainder = 0;
	times.numofdays = floor(totalseconds / secondsperdays);
	remainder = totalseconds % secondsperdays;
	times.numofhours = floor(remainder / secondsperhours);
	remainder %= secondsperhours;
	times.numofminutes = floor(remainder / secondsperminutes);
	remainder %= secondsperminutes;
	times.numofseconds = remainder;

	return times;
}
void totalduration(sttimes times) {

	cout << "\n\ttotal durations: ";
	cout << times.numofdays << ":";
	cout << times.numofhours << ":";
	cout << times.numofminutes << ":";
	cout << times.numofseconds << endl;

}
int main() {
	int totalseconds = readpositivenum("enter total seconds: ");
	totalduration(sttransfertnums(totalseconds));
}

problem #44:
