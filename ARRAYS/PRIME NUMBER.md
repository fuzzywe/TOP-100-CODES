Prime Number Program in C++
C++ Program to Check Whether the Number is Prime or Not
A prime number is a number that can be divided by 1 and itself i.e. a number that can not be divided by any other number other than 1 or itself is a prime number.
 
Example 
Input : 5
Output : 5 is a Prime
C++ program to check whether a number is prime or not
Check Whether the Number is a Prime or Not in C++
The objective of the above problem statement is to write a C++ program to check whether or not the given integer input is a Prime number or not. To do so we’ll check if the number is divisible by 2, if so it’s not a prime. Similarly, we’ll keep dividing the number input with all the numbers until square root of the number input, if divisible with any of those, it’s not a Prime. Here are some of the methods mentioned below to solve the above mentioned problem

Method 1: Simple iterative solution
Method 2: Optimization by break condition
Method 3: Optimization by n/2 iterations
Method 4: Optimization by √n
Method 5: Optimization by skipping even iteration
Method 6: Basic Recursion technique
We’ll discuss the above mentioned methods in detail in the sections below.

While loop in C
Method 1: Simple iterative solution
Any prime number would not be divisible by more than 2 numbers (1 and itself). We run a loop between [1, n] and check if number of divisors of n are greater than 2 or not.

```cpp

#include<iostream>
using namespace std;

int main()
{
    int a = 0, count = 0;
    int n = 21;
    
    // checking the number of divisors b/w 1 and the number n
    for(int i=1;i < n+1; i++) { if(n % i == 0) count += 1; } //if the number of divisors are > 2 then its not prime else its prime 
// 0 and 1 are not prime numbers 
if (n == 0 || n == 1) {
cout << "The given is number " << n <<" is not prime";} else if(count > 2)
    { cout<<"The given number " << n <<" is not prime";} 
else 
    {cout<<"The given number " << n <<" is prime";}
return 0;
 } 
```
// Time Complexity : O(N) 
// Space Complexity : O(1)
Output
The given number 21 is not prime
Method 2: Optimization by break condition
This method works on the following observation –

Any prime number n would not be divisible in the range [2, n-1]
1, 0 and negative numbers are not prime
```cpp

#include<iostream>

using namespace std;

int main()
{
    int i,n = 13;
    bool isprime= true;
    
    // 0 and 1 are not prime numbers also, negative numbers are not prime
    if(n < 2)
    {
        isprime = false;
    }
    else
    {
        for(i=2;i < n;i++)
        {
            if(n % i == 0)
            {
                isprime = false;
                break;
            }
        }
    }

    string result = isprime ? "Prime" : "not Prime";
    cout<<"The number " << n << " is : " << result;
    
    return 0;
}
```
// Time Complexity : O(N)
// Space Complexity : O(1)
// This program is better than previous version as :
// Condition for 0, 1 and negative numbers checked earlier
// Loops runs b/w [2, n-1] rather than [1, n]
Output
The number 13 is : Prime
Method 3: Optimization by n/2 iterations
This method works on the following observation –

Any Prime number doesn’t have any divisors in range [n/2+1, n-1]
Example – 33 won’t have any divisors in range [19, 32]
```cpp
#include<iostream>

using namespace std;

int main()
{
    int i,n = 33;
    bool isprime= true;
    
    // 0 and 1 are not prime numbers also, negative numbers are not prime
    if(n < 2)
    {
        isprime = false;
    }
    else
    {
    // running loop till n is wasteful because for any number n the numbers in
    // the range(n/2 + 1, n) won't be divisible anyways.
        for(i=2; i < n/2; i++)
        {
            if(n % i == 0)
            {
                isprime = false;
                break;
            }
        }
    }

    string result = isprime ? "Prime":"not Prime";
    cout<<"The number " << n << " is : " << result;
    
    return 0;
}
```
// Time Complexity : O(N)
// Space Complexity : O(1)
// This program is better than previous version as :
// Loops runs b/w [2, n/2] rather than [2, n-1]
Output
The number 33 is : Prime
Method 4: Optimization by √n
This method works on the following observation –

We can check for prime numbers by running iterative loop only b/w [2, sqrt(n)]
Detailed explanation given in the code

```cpp

#include<iostream>
#include<math.h>
using namespace std;

int main()
{
    int i,n = 29;
    bool isprime= true;
    
    // 0 and 1 are not prime numbers also, negative numbers are not prime
    if(n < 2)
    {
        isprime = false;
    }
    else
    {
    // If a number n is not a prime, it can be factored into two factors a and b:
    // n = a * b

    /*Now a and b can't be both greater than the square root of n, 
    since then the product a * b would be greater than sqrt(n) * sqrt(n) = n.
    So in any factorization of n, at least one of the factors must be smaller 
    than the square root of n, and if we can't find any factors less than or equal to 
    the square root, n must be a prime.*/
        for(i=2; i < sqrt(n); i++)
        {
            if(n % i == 0)
            {
                isprime = false;
                break;
            }
        }
    }

    string result = isprime ? "Prime":"not Prime";
    cout<<"The number " << n << " is : " << result;
    
    return 0;
}
```
// Time Complexity : O(√N)
// Space Complexity : O(1)
// This program is better than previous version as :
// Loops runs b/w [2, √n] rather than [2, n/2]
Output
The number 29 is : Prime
Method 5: Optimization by skipping even iteration
This method works on the following observation –

2 is the only even prime number
We can skip all even iterations if we check for divisibility with 2 earlier than iterative loop
```cpp
#include<bits/stdc++.h>
using namespace std;

bool isPrime(int n){
    // 0 and 1 are not prime numbers
    // negative numbers are not prime
    if (n <= 1)
        return false;

    // special case as 2 is the only even number that is prime
    else if (n == 2)
        return true;

    // Check if n is a multiple of 2 thus all these won't be prime
    else if (n % 2 == 0)
        return false;

    // If not, then just check the odds
    for (int i = 3; i <= sqrt(n); i += 2)
    {
        if (n % i == 0)
            return false;
    }
    
    return true;
}

int main() {
    int n = 29;
    
    if (isPrime(n))
        cout << n << " is a Prime Number";
    else
        cout << n << " is not a Prime Number";

    return 0;
}
```
//Time complexity : O(√N)
//Space complexity : O(1)
//This code is better than previous code
//We skipping all even iterations b/w [3, √num]
Output
The number 29 is : Prime
Method 6: Basic Recursion technique
In this method we’ll use the knowledge of recursion in C++ to solve the above mentioned problem.

```cpp

#include<iostream>
using namespace std;

bool checkPrime(int n, int i)
{
    // 0, 1 and negative numbers are not prime
    if (n < 2)
        return false;

    // if this satisfies then its prime as we
    // have completed recursion from 2 to n
    if (i == n)
        return true;

    // Base cases
    if (n % i == 0)
        return false;

    i += 1;
    return checkPrime(n, i);
}

int main()
{
    int i = 2;
    bool isprime= true;
    
    int n = 37;
    isprime=checkPrime(n, i);
    
    string result = isprime ? "Prime":"not Prime";
    cout<< n << " is : "<< result;
    
    return 0;
}

```
// Time Complexity : O(N)
// Space Complexity : O(1)
// Auxillary Space complexity : O(N)
// Due to function call stack
Output
The number 37 is : Prime
R
