Find the Sum of N Natural Numbers in C++


https://www.geeksforgeeks.org/problems/stuti-and-her-problem5846/0


This problem involves finding the largest number `k` such that the sum of the first `k` natural numbers is exactly equal to a given `N`. If no such `k` exists, return `-1`. The sum of the first `k` natural numbers is given by:

\[
S_k = \frac{k \times (k + 1)}{2}
\]

We need to check if there exists a `k` such that \( S_k = N \). Below are **brute-force**, **better**, and **optimal** approaches in C++.

---

### **Brute Force Solution**
- Iterate from `k = 1` to `N`, compute the sum of the first `k` numbers, and check if it matches `N`.

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

int findLargestKBruteForce(int N) {
    int sum = 0;
    for (int k = 1; k <= N; k++) {
        sum += k;
        if (sum == N) return k;
    }
    return -1;
}

int main() {
    int N1 = 10;
    int N2 = 17;
    cout << findLargestKBruteForce(N1) << endl;  // Output: 4
    cout << findLargestKBruteForce(N2) << endl;  // Output: -1
    return 0;
}
```

---

### **Better Solution**
- Compute sums iteratively, stopping if the sum exceeds `N`.

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

int findLargestKBetter(int N) {
    int sum = 0, k = 0;
    while (sum < N) {
        k++;
        sum += k;
        if (sum == N) return k;
    }
    return -1;
}

int main() {
    int N1 = 10;
    int N2 = 17;
    cout << findLargestKBetter(N1) << endl;  // Output: 4
    cout << findLargestKBetter(N2) << endl;  // Output: -1
    return 0;
}
```

---

### **Optimal Solution (Mathematical)**
- Use the formula for the sum of the first `k` natural numbers:  
  \[
  k \times (k + 1) / 2 = N
  \]
- Solve the quadratic equation:
  \[
  k^2 + k - 2N = 0
  \]
- Calculate the discriminant, ensuring it is a perfect square, and check if `k` is a positive integer.

#### **Implementation**
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int findLargestKOptimal(int N) {
    double discriminant = 1 + 8 * N;  // From k^2 + k - 2N = 0
    double sqrtVal = sqrt(discriminant);
    
    if (sqrtVal == (int)sqrtVal) {  // Check if sqrtVal is a perfect square
        int k = (-1 + (int)sqrtVal) / 2;
        if (k * (k + 1) / 2 == N) return k;
    }
    return -1;
}

int main() {
    int N1 = 10;
    int N2 = 17;
    cout << findLargestKOptimal(N1) << endl;  // Output: 4
    cout << findLargestKOptimal(N2) << endl;  // Output: -1
    return 0;
}
```

---

### **Complexities**
| **Approach**     | **Time Complexity** | **Space Complexity** |
|------------------|--------------------|----------------------|
| **Brute Force**  | O(N)               | O(1)                 |
| **Better**       | O(sqrt(N))         | O(1)                 |
| **Optimal**      | O(1)               | O(1)                 |

The optimal solution uses the quadratic formula for direct computation, making it the most efficient.

Given an integer input the objective is to write a code to Find the Sum of N Natural Numbers in C++. To do so we simply keep adding the value of the iter variable using a for loop.


Input : num = 8

Output : 36

Where first 8 number is 1, 2, 3, 4, 5, 6, 7, 8

Sum of numbers = 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 = 36

sum of n natural numbers

Find the Sum of N Natural Numbers in C++

Given an integer input of N, the objective is to find the sum of all the natural numbers until the given input integer. To do so we can use different approaches to write the C++ code and some such methods are mentioned below,

Method 1: Using for Loop
Method 2: Using Formula for the Sum of Nth Term
Method 3: Using Recursion
We’ll discuss and learn more about each above-mentioned method in detail in the sections below.

While loop in C
Related Pages
Sum of numbers in a given range

Greatest of two numbers

Greatest of the Three numbers

Prime number within a given range

Leap year or not

 

Method 1 : Using for Loop
In this method we’ll add all the natural numbers until the given integer input using for loop in C++.

```cpp
#include<bits/stdc++.h> 
using namespace std;

int main()
{
    int n;
    cout << "Enter a number : "; 
    cin >> n;
    
    int sum=0;
    
    for(int i=1;i<=n;i++) 
        sum+=i;

    cout << sum;

    return 0;
}
```
Output
Enter a number : 10
55
Working
For a user input num.

 Initialize a variable sum = 0.

Using a for loop in iteration ‘i’ iterate between [1, num].

Each time add ‘i’ to current sum as sum = sum + i.

Print sum.


Explanation

Given an integer input N, the objective is to calculate the sum of all the natural numbers until the integer N. 

To do so we iterate through all the numbers that lay within N and keep incrementing the sum value.

The algorithm for the above code is as follows,


 Include the required header files using the include keyword.

In the main() function initialize the required variables.

Run a for loop with range as N+1.

Keep adding the iter values to the Sum variable.

Print Sum variable using cout keyword.

The output for the above mentioned code is the sum of all the natural numbers until the given value.

Method 2 : Using Formula for the Sum of Nth Term

In this Method we use the formula for finding the sum of N term.

Formula to Find the Sum of N terms
Sum = ( Num * ( Num + 1 ) ) / 2

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    int n;
    
    cout << "Enter a number : "; 
    cin >> n;
    
    cout << n*(n+1)/2;
    
    return 0;
}
```
Output
Enter a number : 10
55
Working
For a user input n.

Step 1: Initialize a variable sum = 0.
Step 2: Use formula sum = n(n+1)/2
Step 3: Print sum
Explanation
Given an integer input N, the objective is to calculate the sum of all the natural numbers until the integer N. To do so we iterate through all the numbers that lay within N and keep incrementing the sum value.

The algorithm for the above code is as follows,

 Include the required header files using the include keyword.
In the main() function initialize the required variables.
Run a for loop with range as N+1.
Keep adding the iter values to the Sum variable.
Print Sum variable using cout keyword.
This algorithm uses the formula n(n+1)/2 that can be used to find sum of first N natural numbers. This also reduces the time complexity from O(n) to O(1). The output for the above mentioned code is the sum of all the natural numbers until the given value.

While loop in C
Method 3 : Using Recursion
This method uses Recursion to recursively add the natural numbers up to the given integer input using recursion in c++.

```cpp
#include<bits/stdc++.h>
using namespace std;

int getSum(int n)
{
    if(n==0) 
        return n;
        
    return n + getSum(n-1);
}

int main()
{
    int n;
    cout << "Enter a number : "; 
    cin >> n;
    
    int sum = getSum(n);
    
    cout << sum;
    
    return 0;
}
```
Output
Enter a number : 10
55
Working
For a user input n.

Initialize a variable sum = 0.
Call function getSum (n).
In each recursive call add the current value of n and call for lower recursion call using return n + getSum(n-1);
Print sum value
Explanation
Given an integer input N, the objective is to calculate the sum of all the natural numbers until the integer N. To do so we recursively call a function  iterate through all the numbers that lay within N and keep incrementing the sum value.

