# C-notes-
C++ problems and answers

Chapter 2 
2-1
#include <iostream>

using namespace std;

int main() 
{
    cout << "**********************************" << endl;
    cout << "*    Programming Assignment 1    *" << endl;
    cout << "*     Computer Programming I     *" << endl;
    cout << "*      Author: Justin Banks      *" << endl;
    cout << "*   Due Date: Thursday, Jan. 24  *" << endl;
    cout << "**********************************" << endl;

    return 0;
}

2-2

#include <iostream>

using namespace std;

int main() {
    // Write your main here
    cout << "CCCCCCCCC       ++              ++"<< endl;
    cout << "CC              ++              ++"<< endl;
    cout << "CC        ++++++++++++++  +++++++++++++++"<<endl;
    cout << "CC        ++++++++++++++  +++++++++++++++"<<endl;
    cout << "CC              ++              ++"<<endl;
    cout << "CCCCCCCCC       ++              ++"<<endl;



    return 0;
}


2-3

//include statement(s)
#include <iostream>

//using namespace statement
using namespace std;

int main()
{

    //variable declaration
    int num1,num2,num3,average;

    //executable statements
    num1 = 125;
    num2 = 28;
    num3 = -25;
    average = 0;

    average = (num1 + num2 + num3) / 3;
    cout << num1 << endl;
    cout << num2 << endl; 
    cout << num3 << endl; 
    cout << average <<endl;

    return 0;
}

Chapter 3

3-1
#include <iostream>
#include <fstream>
#include <string> 
#include <iomanip>

using namespace std;

int main() {
    // Write your main here
    ifstream inFile;
    ofstream outFile;

    string firstName, lastName, department;
    double grossSalary, bouns, taxRate;

    double distanceTraveled, travelTime;
    int numOfCoffeeCupsSold;
    double coffeeCupCost;
    
    inFile.open("inData.txt");
    outFile.open("outData.txt");

    outFile << fixed << showpoint << setprecision(2);

    inFile >>  firstName >> lastName >> department;
    inFile >> grossSalary >> bouns >> taxRate;
    
    outFile << "Name" << firstName << " " << lastName << ", " 
            << "Department: " << department << endl;
    
    outFile << "Monthly Gross Salary: $" << grossSalary
            << ", Monthly Bonus: " << bouns << "%, Taxes: "
            << taxRate << "$" << endl
            << "Paycheck: $"
            << grossSalary * (1 + bouns / 100) * (1 - taxRate / 100)
            << endl << endl;
    
    inFile >> distanceTraveled >> travelTime;

    outFile << "Distance Traveled: " << distanceTraveled
            << " miles, Traveling Time: " << 9.00 << " hours" << endl;

    outFile << "Average Speed: " << distanceTraveled / travelTime
            << " miles per hour" << endl << endl;
    
    inFile >> numOfCoffeeCupsSold >> coffeeCupCost;

    outFile << "Number of Coffee Cups Sold: " << numOfCoffeeCupsSold
            << ", Cost: $" << coffeeCupCost << " per cup" << endl;

    outFile << "Sales Amount = $" << numOfCoffeeCupsSold * coffeeCupCost
            << endl;
    
    inFile.close();
    outFile.close();



    return 0;
}

3-2
#include <iomanip>
#include <cmath>
#include <iostream>

using namespace std;
int main(){

    const double PI = 3.14159;
    double radius;
    double height;

    cout << "Enter the height of the cylinder: ";
    cin >> height;

    cout << "Enter the radius of the base of the cylinder: ";
    cin >> radius;
    cout << endl;

    cout << fixed << showpoint << setprecision(2);
    cout << "Volume of the cylinder = "
        << PI * pow(radius, 2.0) * height << endl;

    cout << endl;

    cout << "Surface area: "
    << 2 * PI * radius * height + 2 * PI * pow(radius, 2.0)
    << endl;

    return 0;
}

3-3
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    // Write your main here
    double weight;
    const double POUNDS = 2.2;
    cout << "Enter your weight: ";
    cin >> weight;
    cout << showpoint << setprecision(2)<< fixed << endl;

    // calculate weight in pounds

    cout << "Your weight is: " << POUNDS * weight << "lbs.";

    return 0;
}

Chapter 4

4-1
#include <iostream>

using namespace std;

int main() {
    // Write your main here
    double num;

    cout << "Enter a number: ";
    cin >> num; 
    cout << endl;
    cout << "The number you entered is " << num << \
    " and this is ";

    if (num == 0)
        cout << "zero." << endl;
    else if (num >= 0)
        cout << "a positive number." << endl;
    else
        cout << "a negative number." << endl;

    return 0;
}


4-2
#include <iostream>

using namespace std;

int main() {
    // Write your main here
    double num1, num2, num3;
    double temp; 

    cout << "Enter three numbers: ";
    cin >> num1 >> num2 >> num3;
    cout << endl;


    if (num1 > num2); 
    { 
        temp = num1;
        num1 = num2;
        num2 = temp;
    }
    // Now num1 is less than or equal to num2

    cout << "The numbers in the ascending order are: ";

    if (num3 <= num1)
        cout << num3 << " " << num1 << " " << num2 << endl;
    else if (num1 <= num3 && num3 <= num2)
        cout << num1 << " " << num3 << " " << num2 << endl;  
    else 
        cout << num1 << " " << num2 << " " << num3 << endl;

    return 0;
}

4-3

#include <iostream>

using namespace std;

int main() {
    // Write your main here
    int num;

    cout << "Enter an integer between 0 and 35: ";
    cin >> num;
    if (num >= 0 and num <= 9)
        cout << num << endl;

    else if (num >= 10 and num <= 35)
        cout << static_cast<char>(num + 55) << endl;
    
    else
        cout << "invaild output";
    return 0;
}



chapter 5

5-1

#include <iostream>
#include <cmath>
using namespace std;

int main() {

    int num;
    int digit;
    int sum = 0;
    int pwr = 1;

    cout << "Enter an integer: ";
    cin >> num;
    cout << endl;

    cout << "The digits of " << num << "are";

    if (num < 0)
        num = -num;
	
	//Find the highest power of 10 that divides the number 

    while (num / static_cast<int>(pow(10.0, pwr)) >= 10) {
        pwr++;
    }

    while (num > 0) {
        digit = num / static_cast<int>(pow(10.0,pwr));
        cout << digit << " ";
        sum += digit;
        num = num % static_cast<int>(pow(10.0,pwr));
        pwr--;
    }
    if (pwr != -1) //Either num is 0 or there are trailing zeros in num 
	while (pwr != -1)
	{
		cout << 0 << " ";
		pwr--; 
	}

    cout << endl;

    cout << "The sum of the digits = " << sum << endl;

    return 0;
}

5-2
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    double pi = 0;
    long i;
    long n;

    cout << "Enter the value of n: ";
    cin >> n;
    cout << endl;
    
    for (i = 0; i < n; i++)
    {
        if (i % 2 == 0)
            pi += (1.0 / (2 * i + 1));
        else
            pi -= (1.0 / (2 * i + 1));
    }
    pi = 4 * pi;
    cout << endl << "pi = " << pi << endl;
    return 0;
}

5-3

//**********************************************************
// Program: Telephone Digits
// This is an example of a sentinel-controlled loop. This
// program converts uppercase letters to their corresponding
// telephone digits.
//**********************************************************
#include <iostream>

using namespace std;

int main()
{
    char letter;
    int digit, num;
    
    cout << "Program to convert uppercase and lowercase letters to "
         << "their corresponding telephone digits."
         << endl;
    
    cout << "To stop the program enter #." << endl;
    
    cout << "Enter a uppercase or lowercase letter: ";
    cin >> letter;
    cout << endl;
    
    while (letter != '#')
    {
        cout << "Letter: " << letter;
        cout << ", Corresponding telephone digit: ";
        
        if (static_cast<int>(letter) < 97){
            num = static_cast<int>(letter) - static_cast<int>('A');
        }
        else{
            num = static_cast<int>(letter) - static_cast<int>('a');
        }
        
        if (0 <= num && num < 26)
        {
            digit = (num / 3) + 2;
            
            if (((num / 3 == 6 ) || (num / 3 == 7))
                  && (num % 3 == 0))
                digit = digit - 1;
            
            if (digit > 9)
                digit = 9;
            
            cout << digit << endl;
        }       
        else
            cout << "Invalid input." << endl;
        
        cout << "\nEnter another uppercase or lowercase "
             << "letter to find its corresponding "
             << "telephone digit." << endl;       
        cout << "To stop the program enter #."
             << endl;
        
        cout << "Enter a letter: ";
        cin >> letter;
        cout << endl;
    } //end while
    
    return 0;
}


Chapter 6 

6-2
#include <iostream>
#include <list>
#include <string>
#include <cctype>

using namespace std;

bool isVowel(char ch);

bool isVowel (char ch){
    list<char> vowels;

    if (isupper(ch))
        vowels = {'A','E','I','O','U'};
    else
        vowels = {'a','e','i','o','u'};

    for (char c: vowels){
        //cout << c << endl;
        if (c == ch)
        {
            return true;;
        }
    }
    return false;
}

int main() {
    char ch;

    cout << "Enter a letter: ";
    cin >> ch;
    //letter = tolower(letter);

    cout << ch << " is a vowel: " << isVowel(ch);

    return 0;
}

6-3

#include <iostream>
#include <list>
#include <string>
#include <cctype>

using namespace std;

bool isVowel(char ch);

bool isVowel (char ch){
    list<char> vowels = {'a','e','i','o','u'};
    ch = tolower(ch);
    for (char c : vowels){
        if (c == ch)
        {
            //cout << ch << " is a vowel." << endl;
            return true;
        }   
    }
    return false;
}   

int main() {
    string sentence;
    int count = 0;

    cout << "Enter a sequence of characters: ";
    //letter = tolower(letter);
    getline(cin,sentence);
    for (char ch : sentence)
    {
        if (isVowel(ch))
        {
            //cout << ch << " is a vowel." << endl;
            count++;
        }
    }
    cout << "There are " << count << " vowels in this sentence." << endl;
    return 0;
}

Chapter 7

7-1

#include <iostream>

using namespace std;

enum triangleType {scalene, isosceles, equilateral, noTriangle};
triangleType triangleShape(double side1, double side2, double side3);
void printShape(triangleType triangle);

int main()
{
	double lenSide1, lenSide2, lenSide3;
	cout << "Enter the lengths of the three sides of a triangle."
	     << endl;
	cin >> lenSide1 >> lenSide2 >> lenSide3;
	cout << endl;

	cout << "The shape of the triangle is: ";
	printShape(triangleShape(lenSide1, lenSide2, lenSide3));
	cout << endl;
	
	return 0;	
}

triangleType triangleShape(double side1, double side2, double side3)
{
	if (side1 == side2 && side2 == side3)
		return equilateral;
	else if ((side1 + side2 > side3 && 
		  side2 + side3 > side1 &&
         	  side1 + side3 > side2))
	     if (side1 == side2 || side2 == side3 || side1 == side3)
		return isosceles;

	     else 
		 return scalene;
	else
	    return noTriangle;
}

void printShape(triangleType triangle)
{
	switch(triangle)
	{
        case scalene:
             cout << "scalene";
             break;
        case isosceles:
             cout << "isosceles";
             break;
        case equilateral:
             cout << "equilateral";
             break;
        case noTriangle:
            cout << "noTriangle";
            break;
          
    }  
}

7-2
#include <iostream>
#include <iomanip>

using namespace std;

namespace royaltyRates
{
	const double OPTION_1_DOWN_PAY = 5000;
	const double OPTION_1_BOOK_DEL_PAY = 20000;

	const double OPTION_2_ROYALTY_RATE = 0.125;
	const double OPTION_3_ROYALTY_RATE_1 = 0.10;
	const double OPTION_3_ROYALTY_RATE_2 = 0.14;
}

using namespace royaltyRates;

int main()
{
	int numberOfCopiesSold;
	double netPriceOfABook;
	
	int bestOption = 0;
	double bestRoyalty = 0;
	
	double royaltyOption1;
	double royaltyOption2;
	double royaltyOption3;
	
	cout << fixed << showpoint;
	cout << setprecision(2);

	cout << "Enter the num of copies sold: ";
	cin >> numberOfCopiesSold; 
	cout << endl;

	cout << "Enter the net price of one book: ";
	cin >> netPriceOfABook;
	cout << endl;

	royaltyOption1 = OPTION_1_DOWN_PAY + OPTION_1_BOOK_DEL_PAY;
	royaltyOption2 = numberOfCopiesSold * netPriceOfABook * OPTION_2_ROYALTY_RATE;
	 
	if (numberOfCopiesSold <= 4000)
		 royaltyOption3 = numberOfCopiesSold * netPriceOfABook * OPTION_3_ROYALTY_RATE_1;
	
	else 
        royaltyOption3 = 4000 * netPriceOfABook * OPTION_3_ROYALTY_RATE_1 + (numberOfCopiesSold - 4000) * netPriceOfABook * OPTION_3_ROYALTY_RATE_2;        
    
    if (bestRoyalty < royaltyOption1)
    {
        bestOption = 1;
        bestRoyalty = royaltyOption1;
    }    
	
	if (bestRoyalty < royaltyOption2)
	{
		bestOption = 2;
		bestRoyalty = royaltyOption2;
	}

	if (bestRoyalty < royaltyOption3)
	{
		bestOption = 3;
		bestRoyalty = royaltyOption3;
	}
	
	if (bestOption == 1)
	{
		if (royaltyOption1 == royaltyOption2)
			if (royaltyOption1 == royaltyOption3)
				cout << "All three options are the same and the royalty is: " << bestRoyalty << endl;

			else
				cout << "Options 1 and 2 are the same and give the best royalty, which is: " << bestRoyalty << endl;

		else if (royaltyOption1 == royaltyOption3)
			cout << "Options 1 and 3 are the same and give the best royalty, which is: " << bestRoyalty << endl;

		else
			cout << "Option 1 is the best and the royalty is: " << bestRoyalty << endl;
	}
	
	else if (bestOption == 2)
	{
		if (royaltyOption2 == royaltyOption3)
			cout << "Options 2 and 3 are the same and give the best royalty, which is: " << bestRoyalty << endl;
		else 
			cout << "Option 2 is the best and the royalty is: " << bestRoyalty << endl;
	}

	else
    {
        cout << "Option 3 is the best and the royalty is: " << bestRoyalty << endl;
    }
    cout << "Royalty option1: " << royaltyOption1 << endl; 
    cout << "Royalty option2: " << royaltyOption2 << endl;
    cout << "Royalty option3: " << royaltyOption3 << endl;
	
	return 0;
}

7-3


Chapter 8

8-1
#include <iostream>

using namespace std;

double alpha[50];
int i, count;

int main() {
    for (i = 0; i < 50; i++){
        if (i < 25){
            alpha[i] = i * i;
            cout << alpha[i] << " ";
            count++;
            if (count % 10 == 0){
                cout << endl;
            }
        }
        else{
            alpha[i] = i * 3;
            cout << alpha[i] << " ";
            count++;
            if (count % 10 == 0){
                cout << endl;
            }
        }
         
    }
    return 0;
}

8-2
#include <iostream>

using namespace std;

int smallestIndex(const int list[], int listSize){
    list[listSize];
    int smallIndx = 0;
    for (int i=0; i < listSize; i++){
        if (list[smallIndx] > list[i]){
            smallIndx = i;  
        }
    }
    for (int i = 0; i < listSize; i++){
        cout << list[i] << " ";
    }
    return smallIndx;
}

int main() {
    int list[15];
    cout << "Enter 15 integers: " << endl;
    for (int i=0; i < 15; i++){
        cin >> list[i];
        }
    int index = smallestIndex(list, 15);
    cout << endl;
    
    cout << "The position of the first occurrence of the smallest element in list is: " 
            << index << endl;
    cout << "The smallest element in the list is: " << list[index] << endl;

    return 0;
}

8-3

#include <iostream>

using namespace std;

int lastLargestIndex(const int list[], int listSize){
    list[listSize];
    int largeIndx = 0;
    for (int i=0; i < listSize; i++){
        if (list[largeIndx] <= list[i]){
            largeIndx = i;  
        }
    }
    for (int i = 0; i < listSize; i++){
        cout << list[i] << " ";
    }
    return largeIndx;
}

int main() {
    int list[15];
    cout << "Enter 15 integers: " << endl;
    for (int i=0; i < 15; i++){
        cin >> list[i];
        }
    int index = lastLargestIndex(list, 15);
    cout << endl;
    
    cout << "The position of the first occurrence of the largest element in list is: " 
            << index << endl;
    cout << "The largest element in the list is: " << list[index] << endl;

    return 0;
}


Chapter 9

9-1
#include <iostream>
#include <iomanip>

using namespace std;

struct computerType
{
    string manufacturer;
    string modelType;
    string processorType;
    int ram;
    int hardDriveSize;
    int yearBuilt;
    double price;
};

int main() {
    // Write your main here
    computerType computer;

    cout << fixed << showpoint << setprecision(2);

    cout << "Enter the name of the manufacturer: ";
    getline(cin, computer.manufacturer);
    cout << endl;

    cout << "Enter the model of the computer: ";
    getline(cin, computer.modelType);
    cout << endl;

    cout << "Enter processor type: ";
    getline(cin, computer.processorType);
    cout << endl;

    cout << "Enter the size of RAM (In GB): ";
    cin >> computer.ram;
    cout << endl;

    cout << "Enter the size of hard drive (In GB): ";
    cin >> computer.hardDriveSize;
    cout << endl;

    cout << "Enter the year the computer was built: ";
    cin >> computer.yearBuilt;
    cout << endl;

    cout << "Enter the price: ";
    cin >> computer.price;
    cout << endl;

    cout << "Manufacturer: " << computer.manufacturer << endl;
    cout << "Model: " << computer.modelType << endl;
    cout << "Processor: " << computer.processorType << endl;
    cout << "Ram: " << computer.ram << endl;
    cout << "Hard Drive Size: " << computer.hardDriveSize << endl;
    cout << "Year Built: " << computer.yearBuilt << endl;
    cout << "Price: $" << computer.price << endl; 
    return 0;
}


9-2

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>

using namespace std;

struct studentType {
    string studentFName;
    string studentLName;
    int testScore;
    char grade;
};

string stuData;
studentType students[20]; //array
int SIZE = sizeof(students) / sizeof(students[0]);
ifstream MyReadFile("Ch9_Ex2Data.txt");
ofstream MyWriteFile("Ch9_Ex2Out.txt");

int readStuData(){ //inputs data from file into array
    for (int i = 0; i< SIZE; i++ ) {
        MyReadFile >> students[i].studentFName
                   >> students[i].studentLName
                   >> students[i].testScore;
    }
    MyReadFile.close();
    return 0;
}

int writeStuData(){
    for (int i = 0; i< SIZE; i++ ) {
        MyWriteFile << left 
                    << students[i].studentLName 
                    << ", " << students[i].studentFName << " "
                    << setw(5)
                    << students[i].testScore
                    << students[i].grade
                    << endl;
    }
    MyWriteFile.close();
    return 0;
}

int giveStuGrades(){
    readStuData();
    for(int i=0; i<SIZE; i++){
        if (students[i].testScore < 70){
            students[i].grade = 'F';
            //cout << students[i].grade << endl;
            //cout << students[i].studentFName << " " << students[i].studentLName << endl;
        }
        else if (students[i].testScore < 80){
            students[i].grade = 'C';
            //cout << students[i].grade << endl;
            //cout << students[i].studentFName << " " << students[i].studentLName << endl;

        }
        else if (students[i].testScore < 90){
            students[i].grade = 'B';
            //cout << students[i].grade << endl;
            //cout << students[i].studentFName << " " << students[i].studentLName << endl;
        }
        else if (students[i].testScore <= 100){
            students[i].grade = 'A';
            //cout << students[i].grade << endl;
            //cout << students[i].studentFName << " " << students[i].studentLName << endl;
        }
    }
    return 0;
}

int highestGrade(){
    giveStuGrades();
    int highest = students[0].grade;
    for (int i = 0; i < SIZE; i++){
        if (students[i].testScore > highest){
            highest = students[i].testScore;
            cout << "Student: " 
                 << students[i].studentFName << " " 
                 << students[i].studentLName << " " << endl
                 << "Grade: " << students[i].testScore << endl;
        }
        
    }
    MyWriteFile << "Highest Grade: " << highest << endl;
    cout << "Highest Score: " << highest << endl;
     
    return 0;
}

int readArray(){ //output data from array
    for (int i = 0; i< SIZE; i++){
        cout << students[i].studentLName << ", "
             << students[i].studentFName << ", "
             << students[i].testScore << ", "
             << students[i].grade << endl;
    }
    return 0;
}

int main() {
    readStuData();
    readArray();
    giveStuGrades();
    highestGrade();
    writeStuData();
    return 0;
}

9-3
#include <iostream>
#include <string>

using namespace std;

struct menuItemType{
    string menuItem;
    double menuPrice;
};
int main() {
    // Write your main here
    return 0;
}


Chapter 10
10-1

//Main program
   
#include <iostream>
#include <string>
#include "studentType.h"

using namespace std;

int main()
{
    studentType student;
    studentType newStudent("Brain", "Johnson", '*', 85, 95, 3.89);

    student.print();
    cout << "***************" << endl << endl;

    newStudent.print();
    cout << "***************" << endl << endl;

    return 0;
}

// Write your code here
#ifndef STUDENTTYPE_H
#define STUDENTTYPE_H

#include <iostream>
#include <string>

using namespace std;
class studentType 
{
    public:
        studentType();
        studentType(string fName, string lName, char grade, int tScore, int pScore, double gpaVal);

        void setFirstName(string first);
        void setLastName(string last);
        void setGrade();
        void setTestScore(int tVal);
        void setProgScore(int progScore);
        void setGPA(double gpa);
        
        string getFirstName() const;
        string getLastName() const;
        char getGrade() const;
        int getTestScore() const;
        int getProgScore() const;
        double getGPA() const;
        
        void print();

    private:
        string firstName;
        string lastName;
        char courseGrade;
        int testScore;
        int programmingScore;
        double GPA;

};

#endif
 
// Write your code here
#include <iostream>
#include <string>
#include "studentType.h"

using namespace std;

studentType::studentType()
{
    firstName = "";
    lastName = "";
    courseGrade = 'F';
    testScore = 0;
    programmingScore = 0;
    GPA = 0.0;
}

studentType::studentType(string fName, string lName, char grade, int tScore, int pScore, double gpaVal)
{
    firstName = fName;
    lastName = lName;
    testScore = tScore;
    programmingScore = pScore;
    GPA = gpaVal;

    setGrade();
}

void studentType::setFirstName(string first)
{
    firstName = first; 
}

void studentType::setLastName(string last)
{
    lastName = last;
}

void studentType::setTestScore(int tVal)
{
    testScore = tVal;
    setGrade();
    
}

void studentType::setProgScore(int progScore)
{
    programmingScore = progScore;
}

void studentType::setGPA(double gpa)
{
    GPA = gpa;
}

void studentType::setGrade()
{
    double average = (testScore + programmingScore) / 2.0;

    if (average >= 90.0)
    {
        courseGrade = 'A';
    }
    else if (average >= 80.0)
    {
        courseGrade = 'B';
    }
    else if (average >= 70.0)
    {
        courseGrade = 'C';
    }
    else if (average >= 60.0)
    {
        courseGrade = 'D';
    }
    else{
        courseGrade = 'F';
    }
} 

string studentType::getFirstName() const {return firstName;}
string studentType::getLastName() const {return lastName;}
char studentType::getGrade() const {return courseGrade;}
int studentType::getTestScore() const {return testScore;}
int studentType::getProgScore() const {return programmingScore;}
double studentType::getGPA() const {return GPA;}


void studentType::print()
{
    cout << "Name: " << firstName << " " << lastName << endl;
    cout << "Grade: " << courseGrade << endl;
    cout << "Test Score: " << testScore << endl;
    cout << "Programming Score: " << programmingScore << endl;
    cout << "GPA: " << GPA << endl;
} 

10-2
#include <string> 

using namespace std;

class productType                               
{                                               
public:                                         
    productType()
    {
        productName = "";                         
        id = "";                                  
        manufacturer = "";                        
        quantitiesInStock = 0;                      
        price = 0.0;                               
        discount = 0.0; 
    };      

    productType(int quantity, double p, double d)
    {
        productName = "";                         
        id = "";                                  
        manufacturer = "";  
        if (quantity >= 0)
            quantitiesInStock = quantity; 
        else
            quantitiesInStock = 0;        
        
        if (p >= 0)
            price = p;
        else
            price = 0;
        
        if (d >= 0)
            discount = d;
        else
            discount = 0;
    };     

    productType(string i, int quantity, double p, double d)
    {
        productName = "";                         
        id = i;                                  
        manufacturer = "";  
        if (quantity >= 0)
            quantitiesInStock = quantity; 
        else
            quantitiesInStock = 0;        
        
        if (p >= 0)
            price = p;
        else
            price = 0;
        
        if (d >= 0)
            discount = d;
        else
            discount = 0;
    };

    productType(string pN, string i, string mF, int quantity, double p, double d)
    {
        productName = pN;                         
        id = i;                                  
        manufacturer = mF;  
        if (quantity >= 0)
            quantitiesInStock = quantity; 
        else
            quantitiesInStock = 0;        
        
        if (p >= 0)
            price = p;
        else
            price = 0;
        
        if (d >= 0)
            discount = d;
        else
            discount = 0;
    };           

    void set(string pN, string i, string mF, int quantity, double p, double d);                  
    void print() const;                         

    void setQuantitiesInStock(int x);           
    void updateQuantitiesInStock(int x);       
    int getQuantitiesInStock() const;           

    void setPrice(double x);                    
    double getPrice() const;                    
    void setDiscount(double d);                 
    double getDiscount() const;                 
     
private:                                        
    string productName;                         
    string id;                                  
    string manufacturer;                        
    int quantitiesInStock;                      
    double price;                               
    double discount;                            
};                                              

// Write your code here
#include <iostream>
#include "productType.h"
#include <string>

using namespace std;

void productType::set(string pN, string i, string mF, int quantity, double p, double d) 
{
    productName = pN;                         
    id = i;                                  
    manufacturer = mF;  
    if (quantity >= 0)
        quantitiesInStock = quantity; 
    else
        quantitiesInStock = 0;        
    
    if (p >= 0)
        price = p;
    else
        price = 0;
    
    if (d >= 0)
        discount = d;
    else
        discount = 0;
};
         
void productType::print() const
{
    cout << productName << endl;
    cout << id << endl;
    cout << manufacturer << endl;
    cout << quantitiesInStock << endl;
    cout << price << endl;
    cout << discount<< endl;
};


void productType::setQuantitiesInStock(int quantity)
{
    if (quantity >= 0)
        quantitiesInStock = quantity;
    else
        quantitiesInStock = 0;
};     
   
void productType::updateQuantitiesInStock(int nQ)
{
    quantitiesInStock += nQ;

    if (quantitiesInStock < 0)
        quantitiesInStock = 0;

};   
       
int productType::getQuantitiesInStock() const
{
    return quantitiesInStock;
};    

void productType::setPrice(double p)
{
    price = p;
}; 

           
double productType::getPrice() const
{
    return price;
};    

                    
void productType::setDiscount(double d)
{
    discount = d;
};  

double productType::getDiscount() const
{
    return discount;
};

10-3

#include <iostream>
#include "houseType.h"

using namespace std;


int main() {
    houseType newHouse("ranch", 3,2,2,2005,1300,185000,3600.0);
    newHouse.print();
    // Write your main here
    return 0;
}

#include <string>

using namespace std;

class houseType
{
public:
    void set(string, int, int, int, int, int, double, double); 
    void print() const;
    void setStyle(string);
    string getStyle() const; 
    void setNumOfBedrooms(int);
    int getNumOfBedrooms() const; 
    void setNumOfBathrooms(int);
    int getNumOfBathrooms() const; 
    void setNumOfCarsGarage(int);
    int getNumOfCarsGarage() const; 
    void setYearBuilt(int);
    int getYearBuilt() const; 
    void setFinishedSquareFootage(int);
    int getFinishedSquareFootage() const; 
    void setPrice(double);
    double getPrice() const; 
    void setTax(double);
    double getTax() const; 

    houseType(string sty = "", int numBeds = 0, int numBaths = 0, int numCars= 0, int year = 0, 
              int sqFoot= 0, double p = 0, double t = 0)
    {
        style = sty;
        numOfBedrooms = numBeds;
        numOfBathrooms = numBaths;
        numOfCarsGarage = numCars;
        yearBuilt = year;
        finishedSquareFootage = sqFoot;
        price = p;
        tax = t;
    };
private:

    string style;
    int numOfBedrooms;
    int numOfBathrooms;
    int numOfCarsGarage;
    int yearBuilt;
    int finishedSquareFootage;
    double price;
    double tax;
};

// Write your code here
#include <iostream>
#include "houseType.h"

using namespace std;

void houseType::set(string sty, int numBeds, int numBaths, int numCars, int year, int sqFoot, double p, double t)
{
    style = sty;
    numOfBedrooms = numBeds;
    numOfBathrooms = numBaths;
    numOfCarsGarage = numCars;
    yearBuilt = year;
    finishedSquareFootage = sqFoot;
    price = p;
    tax = t;
}; 

void houseType::print() const
{
    cout << style << endl;
    cout << numOfBedrooms << endl;
    cout << numOfBathrooms << endl;
    cout << numOfCarsGarage << endl;
    cout << yearBuilt << endl;
    cout << finishedSquareFootage << endl;
    cout << price << endl;
    cout << tax << endl; 
};
void houseType::setStyle(string sty)
{
    style = sty;
};

string houseType::getStyle() const
{
    return style;
}; 
void houseType::setNumOfBedrooms(int numBeds)
{   
    numOfBedrooms = numBeds;
};
int houseType::getNumOfBedrooms() const
{
    return numOfBedrooms;
}; 
void houseType::setNumOfBathrooms(int numBaths)
{
    numOfBathrooms = numBaths;
};
int houseType::getNumOfBathrooms() const
{
    return numOfBathrooms;
}; 
void houseType::setNumOfCarsGarage(int numCars)
{
    numOfCarsGarage = numCars;
};
int houseType::getNumOfCarsGarage() const
{
    return numOfCarsGarage;
}; 
void houseType::setYearBuilt(int year)
{
    yearBuilt = year;
};
int houseType::getYearBuilt() const
{
    return yearBuilt;
}; 
void houseType::setFinishedSquareFootage(int sqFoot)
{
    finishedSquareFootage = sqFoot;
};
int houseType::getFinishedSquareFootage() const
{
    return finishedSquareFootage;
}; 
void houseType::setPrice(double p)
{
    price = p;
};
double houseType::getPrice() const
{
    return price;
}; 
void houseType::setTax(double t)
{
    tax = t;
};
double houseType::getTax() const
{
    return tax;
};


Chapter 11 
11-1

#ifndef h_ClockType
#define h_ClockType
//clockType.h, the specification file for the class clockType
   
class clockType 
{
public:
    void setTime(int hours, int minutes, int seconds);
       //Function to set the time.
       //The time is set according to the parameters. 
       //Postcondition: hr = hours; min = minutes; 
       //               sec = seconds
       //   The function checks whether the values of 
       //   hours, minutes, and seconds are valid. If a 
       //   value is invalid, the default value 0 is 
       //   assigned.

    void getTime(int& hours, int& minutes, int& seconds) const;
       //Function to return the time.
       //Postcondition: hours = hr; minutes = min;
       //               seconds = sec

    void printTime() const;
       //Function to print the time.
       //Postcondition: The time is printed in the form
       //               hh:mm:ss.

    void incrementSeconds();
       //Function to increment the time by one second.
       //Postcondition: The time is incremented by one 
       //               second.
       //   If the before-increment time is 23:59:59, the 
       //   time is reset to 00:00:00.

    void incrementMinutes();
       //Function to increment the time by one minute.
       //Postcondition: The time is incremented by one 
       //               minute. 
       //   If the before-increment time is 23:59:53,
       //   the time is reset to 00:00:53.

    void incrementHours();
       //Function to increment the time by one hour.
       //Postcondition: The time is incremented by one
       //               hour. 
       //   If the before-increment time is 23:45:53, the 
       //   time is reset to 00:45:53.

    bool equalTime(const clockType& otherClock) const;
       //Function to compare the two times.
       //Postcondition: Returns true if this time is 
       //               equal to otherClock; otherwise, 
       //               returns false.

    clockType(int hours, int minutes, int seconds);
       //constructor with parameters
       //The time is set according to the parameters.
       //Postcondition: hr = hours; min = minutes; 
       //               sec = seconds
       //   The constructor checks whether the values of 
       //   hours, minutes, and seconds are valid. If a 
       //   value is invalid, the default value 0 is 
       //   assigned.

    clockType();
       //default constructor 
       //The time is set to 00:00:00.
       //Postcondition: hr = 0; min = 0; sec = 0
 
private:
    int hr;  //variable to store the hours
    int min; //variable to store the minutes
    int sec; //variable to store the seconds
};

#endif
//Program that uses the class extClockType 

#include <iostream>
#include "extClockType.h"

using namespace std;

int main()
{
	extClockType time1(5,10,34,"CST");
	extClockType time2;
	
	cout << "Time 1: ";
	time1.printTime();
	cout << endl;

	time2.setTime(12, 45, 59, "PST");

	cout << "Time 2: ";
	time2.printTime();
	cout << endl;

	time2.incrementSeconds();

	cout << "After incrementing time2 by one second, Time 2: ";
	time2.printTime();
	cout << endl;

	return 0;


} //end main


#ifndef H_ClockType
#define H_ClockType 

#include <string> 

#include "clockType.h"

using namespace std;

class extClockType:public clockType
{
public:
	void setTime(int hours, int minutes, int seconds, string tZone);
	void printTime();

	extClockType(int = 0, int = 0, int = 0, string = "EST");

private:
	string timeZone;

};

#endif


#include <iostream> 
#include <string>
#include "extClockType.h"

using namespace std;

void extClockType::setTime(int hours, int minutes, int seconds, string tZone)
{
	clockType::setTime(hours, minutes, seconds);
	timeZone = tZone;
}

void extClockType::printTime()
{
	clockType::printTime();
	cout << " " << timeZone; 
}

extClockType::extClockType(int hours, int minutes, int seconds, string tZone):clockType(hours, minutes, seconds)

{
	timeZone = zone;
}


//Implementation File for the class clockType 

#include <iostream>
#include "clockType.h"

using namespace std;

void clockType::setTime(int hours, int minutes, int seconds)
{
	if (0 <= hours && hours < 24)
		hr = hours;
	else
		hr = 0;

	if(0<=minutes && minutes < 60)
		min = minutes;
	else
		min = 0;

	if ( 0 <= seconds && seconds < 60)
		sec = seconds;
	else
		sec = 0;
}

void clockType::getTime(int& hours, int& minutes, int& seconds) const

{
	hours = hr;
	minutes = min;
	seconds = sec;
}


void clockType::incrementHours()
{
	hr++;
	if (hr > 23)
	    hr = 0;
}

void clockType::incrementMinutes()
{
	min++;
	if (min > 59)
	{
	    min = 0;
	    incrementHours();
	}
}

void clockType::incrementSeconds()
{
	sec++;
	if (sec > 59)
	{
	    sec = 0;
	    incrementMinutes();
	}
}

void clockType::printTime() const
{
	if (hr < 10)
	    cout << "0";
	cout << hr << ":";
	
	if (min < 10)
	    cout << "0";
	cout << min << ":";
	
	if (sec < 10)
	    cout << "0";
	cout << sec << ":";

}

bool clockType::equalTime(const clockType& otherClock) const
{
	return (hr == otherClock.hr
		&& min == otherClock.min
		&& sec == otherClock.sec);
}


clockType::clockType(int hours, int minutes, int seconds)
{
	if (0 <= hours && hours < 24)
	    hr = hours;
	else
	    hr = 0;

	if (0 <= minutes && minutes < 60)
	    min = minutes;
	else
	    min = 0;

	if (0 <= seconds && seconds < 60)
	    sec = seconds;
	else
	    sec = 0;
}


clockType::clockType() // default constructor
{
	hr = 0;
	min = 0;
	sec = 0;
}



11-2

#include <iostream>
#include "dateType.h"

using namespace std;

int main() 
{
    dateType newDate(2,30,2008);
    dateType otherDate(3,15,2008);
    dateType someDate(1,20,2008);

    otherDate.printDate();
    someDate.printDate();
    newDate.printDate();
    
    if (newDate.isLeapYear()){
        cout << "this is a leap year" << endl;
    }

    else{
        cout << "this is not a leap year" << endl;
    }
    return 0;
}


#ifndef date_H 
#define date_H
 
class dateType
{
public:
    void setDate(int month, int day, int year);
      //Function to set the date.
      //The member variables dMonth, dDay, and dYear are set 
      //according to the parameters
      //Postcondition: dMonth = month; dDay = day;
      //               dYear = year 

    int getDay() const;
      //Function to return the day.
	    //Postcondition: The value of dDay is returned.

    int getMonth() const;
      //Function to return the month.  
	  //Postcondition: The value of dMonth is returned.

    int getYear() const;
      //Function to return the year.     
	  //Postcondition: The value of dYear is returned.

    void printDate() const;
      //Function to output the date in the form mm-dd-yyyy.

	bool isLeapYear();
	    //Function to determine whether the year is a leap year.

    dateType(int month = 1, int day = 1, int year = 1900)
      //Constructor to set the date
      //The member variables dMonth, dDay, and dYear are set 
      //according to the parameters
      //Postcondition: dMonth = month; dDay = day; 
      //               dYear = year
      //If no values are specified, the default values are 
      //used to initialize the member variables.
    {
        if (month >= 1 && month <= 12)
            dMonth = month;
        else
            dMonth = 1;

        if (month == 2 && day >= 30)
            dDay = 1;
        else if (day >= 1 && day <= 31)
            dDay = day;
        else
            dDay = 1;

        if (year >= 1)
            dYear = year;
        else
            dYear = 1900;
    };  

private:
    int dMonth;      //variable to store the month
    int dDay;        //variable to store the day
    int dYear;       //variable to store the year
};

#endif


#include "dateType.h"
#include <iostream>

using namespace std;

void dateType::setDate(int month, int day, int year)
{
    if (month >= 1 && month <= 12)
        dMonth = month;
    else
        dMonth = 1;

    if (month == 2 && day >= 30)
        dDay = 1;
    else if (day >= 1 && day <= 31)
        dDay = day;
    else
        dDay = 1;

    if (year >= 1)
        dYear = year;
    else
        dYear = 1900;
};

int dateType::getDay() const
{
    return dDay;
};

int dateType::getMonth() const
{
    return dMonth;
};

int dateType::getYear() const
{
    return dYear;  
};

void dateType::printDate() const
{
    cout << dMonth << "-" << dDay << "-" << dYear << endl; 
};

bool dateType::isLeapYear() 
{
    cout << dMonth << "-" << dDay << "-" << dYear << endl;; 
    if (dYear % 4 == 0)
    {
        return true;
    } 
    else 
        return false;
};

11-3

#ifndef circleType_H
#define circleType_H

class circleType
{
public:
    void print();

    void setRadius(double r);
      //Function to set the radius. 
      //Postcondition: if (r >= 0) radius = r;
      //               otherwise radius = 0;

    double getRadius();
      //Function to return the radius.
      //Postcondition: The value of radius is returned.

    double area();
      //Function to return the area of a circle.
      //Postcondition: Area is calculated and returned.

    double circumference();
      //Function to return the circumference of a circle.
      //Postcondition: Circumference is calculated and returned.

    circleType(double r = 0);
      //Constructor with a default parameter.
      //Radius is set according to the parameter.
      //The default value of the radius is 0.0;
      //Postcondition: radius = r;
    
    double getPriRadius() const;
 
private:
    double radius;
};

#endif

//Implementation File for the class circleType
 
#include <iostream>
#include "circleType.h"

using namespace std;

void circleType::print()
{
    cout << "Radius = " << radius
         << ", area = " << area()
         << ", circumference = " << circumference();
} 

void circleType::setRadius(double r)
{
    if (r >= 0)
        radius = r;
    else
        radius = 0;
}

double circleType::getRadius()
{
    return radius;
}

double circleType::area()
{
    return 3.1416 * radius * radius;
}

double circleType::circumference()
{
    return 2 * 3.1416 * radius;
}

circleType::circleType(double r)
{
    setRadius(r);
}

double circleType::getPriRadius() const
{
    return radius;
};

#ifndef CYLINDERTYPE_H
#define CYLINDERTYPE_H

#include <string>
#include "circleType.h"

using namespace std;

class cylinderType:public circleType
{
public:
    double volume();
    double surface_area();
    //void getPriRadius();
    void setHeight(int h);
    int getHeight();
    void setBaseRadius(double r);
    double getBaseRadius();
    void setBaseCenter(double x, double y);
    double getBaseCenterX();
    double getBaseCenterY();

    cylinderType(int h = 0, double x = 0, double y = 0, double r = 0);

private:
    int height;
    double centerX;
    double centerY;
};

#endif

#include <string>
#include "cylinderType.h"

using namespace std;

cylinderType::cylinderType(int h, double x, double y, double r):circleType(r)
{
    height = h;
    centerX = x;
    centerY = y;
};

double cylinderType::volume()
{
    return 3.14149 *(getPriRadius()*getPriRadius()) * height;
};
double cylinderType::surface_area()
{
    return 2 *(3.14159 * getPriRadius() * height) + 2 * 3.14159*(getPriRadius()*getPriRadius());
};
void cylinderType::setHeight(int h)
{
    height = h;
};
int cylinderType::getHeight()
{
    return height;
};
void cylinderType::setBaseRadius(double r)
{
    setRadius(r);
};
double cylinderType::getBaseRadius()
{
    return getRadius();
};
void cylinderType::setBaseCenter(double x, double y)
{
    centerX = x;
    centerY = y;
};
double cylinderType::getBaseCenterX()
{
    return centerX;
};

double cylinderType::getBaseCenterY()
{
    return centerY;
};

#include <iostream>
#include "cylinderType.h"

using namespace std;

int main() {
    // Write your main here

    cylinderType cylinder1(2,2,2,2);
    cout << "Volume: " << cylinder1.volume() << endl;
    cout << "Surface Area: " << cylinder1.surface_area() << endl;
    return 0;
}

14-1
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    float feetNum, inchNum;
    float centiNum;
    bool valid = false;
    cout << fixed << setprecision(2);

    while(!valid)
    {
        try
        {
            cout << "Enter a length in feet: ";
            cin >> feetNum;
            if (cin.fail() || feetNum <= 0) 
                throw feetNum;

            cout << "Enter a length in inches: ";
            cin >> inchNum;
            if (cin.fail() || inchNum <= 0)
                throw inchNum;

            centiNum = ((feetNum * 12) + inchNum) * 2.54;

            cout << centiNum << "cm" << endl;
            

            valid = true;
        }
        catch(float caught_exception)
        {
            cout << "A non positive number is entered." << endl;

            cin.clear();
            cin.ignore(1000,'\n');
        }
    }
    return 0;
}

14-2

#include <iostream>
#include <iomanip>
#include <string>
#include "divisionByZero.h"

using namespace std;

int main()
{ 
    int num1, num2;
    char opr;
    bool done = false;

    string str = "Invalid input. You must enter numbers.";

    cout << fixed << showpoint << setprecision(2); 

    try
    {
        cout << "Enter two integers: ";
        cin >> num1 >> num2;
        cout << endl;

        if (!cin)
                throw str;

        cout << "Enter operator: + (addition), - (subtraction),"
                << " * (multiplication), / (division): ";
        cin >> opr;
        cout << endl;

        cout << num1 << " " << opr << " " << num2 << " = ";

        switch (opr)
        {
                case '+': 
                cout << num1 + num2 << endl;
                break;
                case '-': 
                cout << num1 - num2 << endl;
                break;
                case '*': 
                cout << num1 * num2 << endl;
                break;
                case '/':
                
                do
                {
                        try
                        {
                                if (num2 == 0) 
                                        throw divisionByZero();

                                cout << num1 / num2 << endl;
                        done = true;
                        }
                        catch (divisionByZero divByZeroObj)
                        {
                                cout << divByZeroObj.what() << endl;
                                cin.clear();
                                cin.ignore(100, '\n');
                                cout << "Enter the divisor: ";
                                cin >> num2;
                                cout << endl;

                                cout << num1 << " " << opr << " " << num2 << " = ";
                        }

                } 
                while (!done);
                
                break;
                default:
                cout << "Illegal operation" << endl;
                }
    }
    catch (string messageStr)
    {
        cout << messageStr << endl;
        cout << "Program terminates" << endl;
    }
        return 0;
}

//User-Defined exeception class.

#include <iostream>
#include <string>

using namespace std;

class divisionByZero
{
    public:
        divisionByZero()
        {
            message = "Division by zero";
        }

        divisionByZero(string str)
        {
            message = str;
        }
        string what()
        {
            return message;
        }

    private:
        string message;
        
};

14-3

#include <iostream> 
#include "divisionByZero.h"

using namespace std;

void addFractions(int num1, int num2, int den1, int den2, 
				  int& numfrac, int& denfrac);
void subtractFractions(int num1, int num2, int den1, int den2, 
				       int& numfrac, int& denfrac);
void multiplyFractions(int num1, int num2, int den1, int den2, 
				       int& numfrac, int& denfrac);
void divideFractions(int num1, int num2, int den1, int den2, 
				     int& numfrac, int& denfrac);

void menu();
void getFraction(int choice,int fractNo, int& numerator, int& denominator);

void showResult(char operation, int num1, int num2, int den1, int den2, 
				  int numfrac, int denfrac);

int main()
{
    int numerator1, numerator2, denominator1, denominator2;
    int resultnum, resultdeno;

    int choice;

    menu();
    cin >> choice;

    while (choice != 9)
    {
        cout << "For fraction 1" << endl;
        getFraction(choice, 1, numerator1, denominator1);
        cout << endl;

        cout << "For fraction 2" << endl;
        getFraction(choice, 2, numerator2, denominator2);
        cout << endl;

        switch (choice)
        {
		case 1: 
            addFractions(numerator1, numerator2,
                         denominator1, denominator2,
                         resultnum, resultdeno);
            showResult('+', numerator1, numerator2,
                            denominator1, denominator2,
                            resultnum, resultdeno);
            break;
        case 2: 
            subtractFractions(numerator1, numerator2,
                              denominator1, denominator2,
                              resultnum, resultdeno);
            showResult('-', numerator1, numerator2,
                            denominator1, denominator2,
                            resultnum, resultdeno);
            break;
		case 3: 
            multiplyFractions(numerator1, numerator2,
                             denominator1, denominator2,
                             resultnum, resultdeno);
            showResult('*', numerator1, numerator2,
                            denominator1, denominator2,
                            resultnum, resultdeno);
            break;
        case 4: 
            divideFractions(numerator1, numerator2,
                            denominator1, denominator2,
                            resultnum, resultdeno);
            showResult('/', numerator1, numerator2,
                            denominator1, denominator2,
                            resultnum, resultdeno);
            break;
        default: 
            cout << "Invalid selection." << endl;
        }
		
        menu();
        cin >> choice;
    }

    return 0;
}

void addFractions(int num1, int num2, int den1, int den2, 
				  int& numfrac, int& denfrac)
{
    numfrac = num1 * den2 + num2 * den1;
    denfrac = den1 * den2;
}

void subtractFractions(int num1, int num2, int den1, int den2, 
                       int& numfrac, int& denfrac)
{
    numfrac = num1 * den2 - num2 * den1;
    denfrac = den1 * den2;
}

void multiplyFractions(int num1, int num2, int den1, int den2, 
                       int& numfrac, int& denfrac)
{
    numfrac = num1 * num2;
    denfrac = den1 * den2;
}

void divideFractions(int num1, int num2, int den1, int den2, 
                     int& numfrac, int& denfrac)
{
    numfrac = num1 * den2;
    denfrac = num2 * den1;
}

void menu()
{
    cout << "This program performs operations on fraction. Enter" 
         << endl;
    cout << "1 : To add fraction" << endl;
    cout << "2 : To subtract fraction" << endl;
    cout << "3 : To multiply fraction" << endl;
    cout << "4 : To divide fraction" << endl;
    cout << "9 : To exit the program" << endl;
}

void getFraction(int choice, int fractNo, int& numerator, int& denominator)
{
    bool valid = false;
    cout << "Enter the numerator: ";
    cin >> numerator;
    cout << endl;

    if (choice == 4 && fractNo == 2 && numerator == 0)
    {
		cout << "To divide, the second fraction must be nonzero." 
             << endl;
        while (numerator == 0)
        {
            cout << "Enter a nonzero number for the numerator: ";
            cin >> numerator;
            cout << endl;
        }
    }

    cout << "Enter the denominator: ";
    cin >> denominator;
    do
    {
        try
        {
            if (denominator == 0)
                throw divisionByZero();
            valid = true;
        } 
            catch (divisionByZero divByZeroObj)
            {
                cout << divByZeroObj.what() << endl;
                cin.clear();
                cin.ignore(100, '\n');
                cout << "Enter the denominator: ";
                cin >> denominator;

            }
        
    } while (!valid);
    
    cout << endl;
}

void showResult(char operation, int num1, int num2, int den1, int den2, 
				int numfrac, int denfrac)
{
    cout << num1 << "/" << den1;

    switch (operation)
    {
    case '+': 
        cout << " + ";
        break;
    case '-': 
        cout << " - ";
        break;
    case '*': 
        cout << " * ";
        break;
    case '/': 
        cout << " / ";
        break;
    default: 
        cout << "Invalid operation." << endl;
    }

    cout << num2 << "/" << den2 << " = " << numfrac << "/" 
         << denfrac << endl;
}


//User-Defined exeception class.

#include <iostream>
#include <string>

using namespace std;

class divisionByZero
{
    public:
        divisionByZero()
        {
            message = "Denominator must be nonzero";
        }

        divisionByZero(string str)
        {
            message = str;
        }
        string what()
        {
            return message;
        }

    private:
        string message;
        
};





15-1

#include <iostream>

using namespace std;

void printStars(int lines);

int main() {
    int lines;

    cout << "Enter the number of lines in the grid: ";
    cin >> lines;
    cout << endl;

    printStars(lines);
    
    cout << endl;
    
    return 0;
}

void printStars(int lines){
    int i;

    if (lines > 0)
    {
        for (i = 0; i < lines; i++)
            cout << "*";
        cout << endl;

        printStars(lines - 1);

        for (i = 0; i < lines; i++)
            cout << "*";
        cout << endl;
    }
}
