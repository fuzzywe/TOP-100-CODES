Find the Sum of Numbers in a Given Range in C++
Find the Sum of Numbers in a given range in C++
Given two integer inputs num1 and num2, the objective is to write a code to Find the Sum of Numbers in a Given Range in C. To do so we’ll keep iterating and adding the numbers from num1 until num2 to the Sum variable.

Example
Input : 2 5
Output : 2 + 3 + 4 + 5 + 6 = 20

Find the Sum of Numbers in a Given Interval in C++
Here we will discuss how to find the Sum of Natural Numbers in a range defined by user using c++ programming language. Given two integer inputs the objective is to Find the Sum of all the integers that lay within the given interval input by writing a code in C Language. Some Methods for solving the above problem are mentioned below,

Method 1 : Using Brute Force
Method 2 : Using the Formula
Method 3 : Using Recursion 1
Method 4 :  Using Recursion 2
We’ll discuss about the above mentioned methods in the sections below in detail.




Method 1 : Using Brute Force
Algorithm and Working
For input num1 (smaller) and num2(larger), The algorithm for the above problem is as follows,

Initialize sum = 0
Run an iterative loop between [num1, num2] in iteration of (i)
In each iteration do sum = sum + i;
Print sum value
Let’s try and implement the algorithm in C++ Language.

```cpp
#include<iostream>
#include<vector>
#include<bits/stdc++.h>
#include<cstdio>
using namespace std;
int main()
{
    int num1 = 5;
    int num2 = 10;
    int sum = 0;
    for (int i = num1; i <= num2; i++)
        sum = sum + i;
    cout << sum;
    return 0;
}
// Time complexity : O(N)
// Space complexity : O(1)
Output
45
```
Method 2 : Using the Formula
Explanation
Given two integer inputs num1 and num2, the objective is to write a code to Find the Sum of Numbers in a Given Range in C. To do so we’ll keep iterating and adding the numbers from num1 until num2 to the Sum variable. The Sum of N natural numbers can be found using formula – n(n+1)/2.

Using the same approach sum between two intervals [x, y] can be found using

sum = y*(y+1)/2 – x*(x+1)/2 + x;

Why did we add the extra x at the end ?

An extra x is added to offset because of overalpping interval

Example -
Assume you had to calculate sum b/w (3, ). Doing y * (y+1) / 2 – x * (x+1) / 2

We would have done is subtracted (1, 2, 3) from (1, 2, 3, 4, 5).

Thus only calculating the sum between (4, 5) not (3, 5).

So extra 3 i.e. a is added in the formula
```cpp
#include<iostream>
#include<vector>
#include<bits/stdc++.h>
#include<cstdio>
using namespace std;
int main()
{
    int x = 5;
    int y = 10;
    int sum = y*(y+1)/2 - x*(x+1)/2 + x;
    cout << sum;
    return 0;
}
// Time complexity : O(1)
// Space complexity : O(1)

```
Method 3 : Using Recursion 1
Algorithm and Explanation
This method uses recursion in C++

For inputs, a, b where a is smaller number and b is larger.

Call a recursive function calcSum(a, b)

In each recursive call add the current ‘a’ value and call the next iteration with ‘a+1’ value

That is, do this : return a + calcSum(i + 1, b);

In base case when a becomes greater than b  return 0

Print value returned by the recursive function in main
---

```cpp
#include<iostream>
#include<vector>
#include<bits/stdc++.h>
#include<cstdio> 
using namespace std;
int calcSum(int a, int b){
    // stop when any recursion call tries to go over b (larger number)
    if (a > b)
        return 0;
    return a + calcSum(a + 1, b);
}
int main()
{
    int a = 10;
    int b = 15;   
    int sum = calcSum(a, b);
    cout << sum;
    return 0;
}
```
// Time complexity : O(N)
// Space complexity : O(1)
// Auxiliary Space complexity : O(1)
// Because of function call stack
Output
75


Method 4 : Using Recursion 2

Algorithm and Explanation

This method uses recursion in C++. For inputs, a, b where a is the smaller number and b is larger.

In the previous method, recursion went from a -> b. In this we will do the opposite that is it will go from b -> a


Call a recursive function calcSum(a, b)

In each recursive call add the current ‘b’ value and call the next iteration with ‘b-1’ value

That is, do this : return b + calcSum(a, b-1);

In base case when b becomes smaller than a return 0

Print value returned by the recursive function in main

Let’s try and implement the Algorithm in C++ Language.

```cpp
#include<iostream>
#include<vector>
#include<bits/stdc++.h>
#include<cstdio>
using namespace std;
int calcSum(int a, int b){      
    // stop when any recursion call tries to go under a (smaller number)
    if (b < a)
        return 0;
    return b + calcSum(a, b-1);
}
int main()
{
    int a = 10;
    int b = 15;   
    int sum = calcSum(a, b);
    cout << sum;
    return 0;
}
```
// Time complexity : O(N)
// Space complexity : O(1)
// Auxiliary Space complexity : O(1)
// Because of function call stack
Prime Course Trailer


