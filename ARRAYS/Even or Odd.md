Check Whether a Number is Even or Odd in C++

https://www.geeksforgeeks.org/problems/odd-or-even3618/1

Given an integer input the objective is to write a C++ code to Check Whether a Number is Even or Odd. To do so the main idea is to divide the number by 2 and check if it’s divisible or not. It’s an Even number is it’s perfectly divisible by 2 or an Odd number otherwise.

Here are the Methods to solve the above mentioned problem,

Method 1 : Using Brute Force
Method 2 : Using Ternary Operator
Method 3 : Using Bitwise Operators
We’ll discuss the above mentioned methods in detail in the next section.
While loop in C
Related Pages
Sum of First N Natural numbers

Sum of N natural numbers

Sum of numbers in a given range

Greatest of the Three numbers

Prime number within a given range

Method 1 : Using Brute Force
This method simply checks if the given input integer is divisible by 2 or not. If it’s divisible then print Even or Odd otherwise.

```cpp
#include <iostream>
using namespace std;
int main ()
{
    int number;
    cout << "Enter a number:"; cin >> number;
 
    //checking whether the number is even or odd
    if (number % 2 == 0)
        cout << number << " : Even";
    else
        cout << number << " : Odd";
        
    return 0;
}
```
Output
Enter a number: 4
24 : Even
Working
The working of the above code is mentioned below

Input an integer input “number“
Check whether the number is divisible by 2
This means using modulo/remainder operator leaves 0 as a remainder
Do : if (number % 2 == 0)
if yes, print “Even number”
if not, print “Odd number”
Method 2 : Using Ternary Operator
This Method uses the ternary operator to check if the integer input is divisible by 2, If true print Even or Odd otherwise.

Ternary Operator Syntax
( Condition ) ? ( if True : Action ) : ( if False : Action ) ;
```cpp
#include <iostream>
namespace std;

int main ()
{
    int number;
    cout << "Enter a number:"; cin >> number;

    
    //Checking if the number is divisible by 2
    number % 2 == 0 ? cout << "Even":cout << "Odd";
    
    return 0;
}
```
Output
Enter a number: 17
Odd
Working
The working of the above code is as follows,

Input an integer input “number“
Check whether the number is divisible by 2 using the ternary operator
(number % 2) ? (cout <<“Even”) : (cout << “Odd”)
Method 3 : Using Bitwise Operator
This Method uses bitwise operators to check if a given number is Even or Odd.

Bitwise Operators
In computer programming, a bitwise operation operates on a bit string, a bit array or a binary numeral at the level of its individual bits. It is a fast and simple action, basic to the higher-level arithmetic operations and directly supported by the processor.
```cpp
#include <iostream>
using namespace std;
 
// Returns true if n is even, else odd
bool isEven(int number)
{
     
    // n & 1 is 1, then odd, else even
    return (!(number & 1));
}
 
// Driver code
int main()
{
    int number;
    
    cout << "Enter the number: "; cin >> number;

    if(isEven(number))
        cout << "Even";
    else
        cout << "Odd";

    //below can also be used instead of if else conditions
    //isEven(number)? cout << "Even" : cout << "Odd";
 
    return 0;

}

```
Output
Enter a number: 13
Odd
Working
The working of the above code is as follows,

If we have any number ‘n‘ doing bitwise ‘&‘ operation will give resultant as
1: If n is odd
0: if n is even
