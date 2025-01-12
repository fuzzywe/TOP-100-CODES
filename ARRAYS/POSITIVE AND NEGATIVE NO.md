https://www.geeksforgeeks.org/problems/positive-and-negative-elements4613/1

Here are **brute-force**, **better**, and **optimal** solutions to the given problem in **C++**.

### **Brute-Force Solution**
1. Traverse the array and store positive and negative numbers in two separate vectors.
2. Merge them into a new array by alternating elements.
3. Append remaining elements if any.

#### **Implementation**
```cpp
#include <iostream>
#include <vector>
using namespace std;

vector<int> rearrangeBruteForce(const vector<int>& arr) {
    vector<int> positive, negative;
    
    for (int x : arr) {
        if (x > 0) positive.push_back(x);
        else negative.push_back(x);
    }
    
    vector<int> result;
    int i = 0, j = 0;
    
    while (i < positive.size() && j < negative.size()) {
        result.push_back(positive[i++]);
        result.push_back(negative[j++]);
    }
    
    while (i < positive.size()) result.push_back(positive[i++]);
    while (j < negative.size()) result.push_back(negative[j++]);
    
    return result;
}

int main() {
    vector<int> arr1 = {-1, 2, -3, 4, -5, 6};
    vector<int> arr2 = {-3, 2, -4, 1};
    
    vector<int> result1 = rearrangeBruteForce(arr1);
    vector<int> result2 = rearrangeBruteForce(arr2);
    
    for (int x : result1) cout << x << " ";
    cout << endl;
    for (int x : result2) cout << x << " ";
    cout << endl;
    
    return 0;
}
```

---

### **Better Solution**
- Use a single traversal to rearrange elements using two pointers.
- Maintain the order of elements by shifting rather than directly swapping.

#### **Implementation**
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

void rearrangeBetter(vector<int>& arr) {
    int n = arr.size();
    vector<int> pos, neg;

    for (int i = 0; i < n; i++) {
        if (arr[i] >= 0) pos.push_back(arr[i]);
        else neg.push_back(arr[i]);
    }
    
    int i = 0, j = 0, k = 0;
    while (i < pos.size() && j < neg.size()) {
        arr[k++] = pos[i++];
        arr[k++] = neg[j++];
    }
    while (i < pos.size()) arr[k++] = pos[i++];
    while (j < neg.size()) arr[k++] = neg[j++];
}

int main() {
    vector<int> arr1 = {-1, 2, -3, 4, -5, 6};
    rearrangeBetter(arr1);
    for (int x : arr1) cout << x << " ";
    cout << endl;
    
    vector<int> arr2 = {-3, 2, -4, 1};
    rearrangeBetter(arr2);
    for (int x : arr2) cout << x << " ";
    cout << endl;
    
    return 0;
}
```

---

### **Optimal Solution (In-place)**
This approach rearranges elements without using extra space for positive and negative arrays.

1. Iterate over the array and place elements in alternating positions.
2. Handle shifts to maintain the order.

#### **Implementation**
```cpp
#include <iostream>
#include <vector>
using namespace std;

void rearrangeOptimal(vector<int>& arr) {
    int n = arr.size();
    int pos = 0, neg = 1;  // Position to place positive and negative numbers

    while (true) {
        while (pos < n && arr[pos] >= 0) pos += 2;
        while (neg < n && arr[neg] < 0) neg += 2;
        
        if (pos < n && neg < n) swap(arr[pos], arr[neg]);
        else break;
    }
}

int main() {
    vector<int> arr1 = {-1, 2, -3, 4, -5, 6};
    rearrangeOptimal(arr1);
    for (int x : arr1) cout << x << " ";
    cout << endl;
    
    vector<int> arr2 = {-3, 2, -4, 1};
    rearrangeOptimal(arr2);
    for (int x : arr2) cout << x << " ";
    cout << endl;
    
    return 0;
}
```

---

### **Complexities**
| **Approach**     | **Time Complexity** | **Space Complexity** |
|------------------|--------------------|----------------------|
| **Brute Force**  | O(n)               | O(n)                 |
| **Better**       | O(n)               | O(n)                 |
| **Optimal**      | O(n)               | O(1)                 |

These solutions progressively improve efficiency and space usage.


Input: arr[] = [-1, 2, -3, 4, -5, 6]
Output: [2, -1, 4, -3, 6, -5]
Explanation: Positive numbers in order are 2, 4 and 6. Negative numbers in order are -1, -3 and -5. So the arrangement we get is 2, -1, 4, -3, 6 and -5.
Input: arr[] = [-3, 2, -4, 1]
Output: [2, -3, 1, -4] 
Explanation: The positive numbers are 2,1 and negetive numbers are -3, -4  
Expected Time Complexity: O(n)
Expected Auxiliary Space: O(n)
```cpp
#include<iostream>
using namespace std;

int main()
{
    int num = -12;
    
    //Condition to check if the number is negative or positive
    if (num >= 0)
    {
        if (num == 0)
            cout << "Zero";
        else
            cout << "The number is positive";
    }
    else
            cout << "The number is negative";
    
    return 0;
}
```
Output
Enter a number: -12
The number is Negative
Algorithm
This method uses a nested if-else Statements to check whether a given number is Positive or Negative.

Step 1 – Start
Step 2 – Insert the number.
Step 3 – If the number is greater or equal move to the inner nested loop
Step 3.1 – If the number is zero, print Zero
Step 3.2 – Else print The Number is Positive
Step4 – Else the number has to be negative, Print The number is Negative
Step 6 – Stop
Method 3: Using Ternary Operator
This method uses a ternary operator to check whether a number is Positive or Negative.

Ternary Operator Syntax
( Condition ) ? ( if True : Action) : ( if False : Action) ;
C++ Code

```cpp
#include <iostream>
using namespace std;

int main()
{
    int num = -15;
    
    //Condition to check if the 0, positive or negative
    
    if(num == 0)
            cout << "Zero"; else (num > 0) ? cout << "Positive": cout << "Negative";
    
    return 0;
}

```
Output
Enter a number: -15
Negative
Algorithm
This method uses a ternary operator to check whether a number is Positive or Negative. The Algorithm for the above code is as follows,
 
Step 1 – Start
Step 2 – Insert the number.
Step 3 – If number is equal to zero, Print Number is Zero
Step 4 – Else do following –            (num > 0) ? cout << “Positive”: cout << “Negative”;
Step 6 – Stop
