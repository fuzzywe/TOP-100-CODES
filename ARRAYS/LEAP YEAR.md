Program to Check Whether a Year is a Leap Year or Not in C++
Program to Check Whether a Year is a Leap Year or Not in C++
Given an integer input for a year, the objective is to write a Program to Check Whether a Year is a Leap Year or Not in C++ Language.

Example
Input : 2020
Output : 2020 is a Leap Year
Leap Year or Not in C++
Program to Check if the Year is a Leap Year or Not in C++ Language
Here we will discuss how to check whether a year is a leap year or not using the C++ programming language. In a  year there are 365 days, but once every fourth year there are 366 days that year is called a leap year. The objective is to write a Program to Check if the Year is a Leap Year or Not in C++ Language. Here are few methods to check for leap years

Method 1: Using if-else Statements 1
Method 2: Using if-else Statements 2
Method 3: Using Ternary Operator
Method 4: Complicated if-else statements (Not recommended)
We’ll discuss the above mentioned methods in detail in the sections below. Before we dive in, check the conditions for Leap Year mentioned below.

Condtions for Leap Year
Following are the rules to predict if a given is a year leap or not. If any one of the conditions below is met then it's a leap year -
1. If a year is divisible by 400, it's a leap year.
2. If a year is divisible by 4 but not by 100 then its leap year
Method 1: Using if-else Statements 1
In this method we’ll use the if-else statements to check for the above mentioned conditions one by one.

Working
For user input year check

If year % 400 == 0
Print Leap Year
Else If year % 4 == 0 && year % 100 != 0
Print Leap Year
Else, year will be not leap
Let’s implement the above logic in C++ Language.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int year;

    year=2000;

    if(year % 400 == 0)
        cout << year << " is a Leap Year";
        
    else if(year % 4 == 0  && year % 100 != 0)
        cout << year << " is a Leap Year";
        
    else
        cout << year << " is not a Leap Year";
    
    return 0;
}
```
Output
2000 is a Leap Year
Method 2: Using if-else Statements 2
In this method we’ll use the if-else statements to check for the above mentioned conditions one by one. This method is the more simplified version of the previous method.

Working
For user input year check –

If (year % 400 == 0 || (year % 4 == 0 && year % 100 != 0))

Print Leap Year

Else, year will be not leap

Let’s implement the above logic in C++ Language.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int year;

    year=2000;

    if(year % 400 == 0 || (year % 4 == 0  && year % 100 != 0))
        cout << year << " is a Leap Year";

    //not leap year
    else
        cout << year << " is not a Leap Year";
    
    return 0;
}
```
Output

2000 is a Leap Year

---
Method 3: Using Ternary Operator
In this method we’ll use the Ternary operator to check for the above mentioned conditions. For more information on Ternary operators check out Ternary operators in C.

Working
For user input year check

Using ternary operator check if the year is divisible by 400. Print it’s a leap year.
Using Ternary operator check if the year is divisible by 4 but not with 100. Print it’s a leap year.
Else print it’s not a leap year.
Let’s implement the above mentioned logic in C++ Language.

```cpp
#include 
using namespace std;

int main()
{
    int year;
    year=2000;
    int flag = (year%400 == 0) || (year%4==0 && year%100!=0 ) ? 1 : 0;
    if (flag ==1)
    {
        printf("%d is a Leap Year",year);
    }
    else
    {
        printf("%d is not a Leap Year",year);
    }

    return 0;
}
```
Output
2000 is a Leap Year
Method 4: Complicated if-else statements
```cpp
#include <iostream>
using namespace std;

int main() {

    int year;

    year=2000;
  
    if (year % 4 == 0) {
        if (year % 100 == 0) {
            if (year % 400 == 0) {
                cout << year << " is a Leap Year";
            }
            else {
                cout << year << " is not a Leap Year";
            }
        }
        else {
            cout << year << " is a Leap Year";
        }
    }
    else {
        cout << year << " is not a Leap Year";
    }
    return 0;
}

```
Output
2000 is a Leap Year
