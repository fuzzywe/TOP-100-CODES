https://www.geeksforgeeks.org/problems/largest-element-in-array4009/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=practice_card


Find the Greatest of the Two Numbers in C++
Iterative Approach – O(n) Time and O(1) Space
The approach to solve this problem is to traverse the whole array and find the maximum among them.




```cpp
#include <iostream>

#include <vector>

using namespace std;

​

int largest(vector<int>& arr) {

    int max = arr[0];

​

    //Traverse  from second and compare

    // every element with current max

    for (int i = 1; i < arr.size(); i++)

        if (arr[i] > max)

            max = arr[i];

​

    return max;

}

​

int main() {

    vector<int> arr = {10, 324, 45, 90, 9808};

    cout << largest(arr);

    return 0;

}
```
Output
9808
Recursive Approach – O(n) Time and O(n) Space
The idea is similar to the iterative approach. Here the traversal of the array is done recursively instead of an iterative loop. 


---

```cpp
#include <iostream>

#include <vector>

using namespace std;

​

int findMax(vector<int>& arr, int i) {

  

   // Last index returns the element

    if (i == arr.size() - 1) {

        return arr[i];

    }

​

    // Find the maximum from the rest of the vector

    int recMax = findMax(arr, i + 1);

​

    // Compare with i-th element and return

    return max(recMax, arr[i]);

}

​

int largest(vector<int>& arr) {

  return findMax(arr,0);

}

​

int main() {

    vector<int> arr = {10, 324, 45, 90, 9808};

    cout << largest(arr);

    return 0;

}
```
Output
9808
Using Library Methods – O(n) Time and O(1) Space
Most of the languages have a relevant max() type in-built function to find the maximum element, such as  std::max_element in C++. We can use this function to directly find the maximum element.  


---

```cpp
#include <iostream>

#include <vector>

#include <algorithm>

using namespace std;

​

int largest(vector<int>& arr) {

    return *max_element(arr.begin(), arr.end());

}

​

int main() {

    vector<int> arr = {10, 324, 45, 90, 9808};

    cout << largest(arr);

    return 0;

}
```
Output
9808
Find the Greatest of the Two Numbers in C++
Given two integers as input, the objective is to check both numbers for the greatest and write a code to find the greatest of the two numbers in C++.

Methods to find the greatest of the two numbers in C++
Method 1: Using if-else Statements
Algorithm
For two user inputs num1 and num2.
Step 1: Check if both numbers are equal
If true then print “Both are equal”
Step 2: Else if num1 > num2
If true then print num1 greater than num2
Step 3: Else num2 has to be thee greatest
Print num2 is greater than num1
```cpp
#include <iostream>
using namespace std;

int main ()
{
    int num1, num2;
    num1=75,num2=85;
 
    if (num1 == num2)
        cout << "both are equal"; else if (num1 > num2)
        cout << num1 << " is greater than " << num2;
    else
        cout << num2 << " is greater than " << num1;

    return 0;
}
```
// Time Complexity : O(1)
// Space Complexity : O(1)
Output
85 is greater than 75

Related Pages
Sum of N natural numbers

Sum of numbers in a given range
 
Greatest of the Three numbers

Leap year or not

Prime number

Method 2: Using Ternary Operator
Algorithm
This method uses knowledge of ternary operator in C++ For two user inputs num1 and num2.
Step 1: Check if both numbers are equal
If true then print “Both are equal”
Step 2: Use ternary operator as largest = num1 > num2? num1 : num2;
Step 3: Print the value of variable largest
```cpp
#include<bits/stdc++.h>
using namespace std;

int main ()
{
    int num1, num2, largest;
    num1=32,num2=47; 
 
    if(num1 == num2)
        cout << "Both are Equal\n"; else { largest = num1 > num2? num1 : num2;
        cout << largest << " is largest";
    }

  return 0;
}
```
// Time Complexity : O(1)
// Space Complexity : O(1)
Output
47 is largest
Method 3: Using inbuilt max() Function
Algorithm
This method uses internal inbuilt function max(a, b) which returns the larger value. For two user inputs num1 and num2.

Step 1: Check if both numbers are equal

If true then print “Both are equal”

Step 2: Use inbuilt function max as max(num1, num2)

Step 3: Print the value of returned by max function

```cpp

#include <iostream>  
// function max available in here
#include <math.h>
using namespace std;

int main ()
{
    int num1, num2;
    num1=45,num2=14;
 
    if (num1 == num2)
        cout << "both are equal";
    else
        cout << max(num1,num2) << " is greater";

    return 0;
}
```
// Time Complexity : O(1)
// Space Complexity : O(1)
Output
45 is greater
Method 4: Using Classes
This method uses classes and objects concept in C++
```cpp
#include <iostream> 
using namespace std;

class PrepInsta
{
    public:
        int calcLargest(int, int);
};

int PrepInsta::calcLargest(int a, int b)
{
    if(a>b)
        return a;
    else
        return b;
}

int main()
{
    PrepInsta obj;
    int num1, num2, largest;
    
    num1=36,num2=23;
    
    largest = obj.calcLargest(num1, num2);
    cout<<"Largest: "<<largest;

    return 0;
}

```
Output
Largest: 36
Prime Course Trailer


