https://www.naukri.com/code360/problems/largest-element-in-the-array-largest-element-in-the-array_5026279?utm_source=striver&utm_medium=website&utm_campaign=codestudio_a_zcourse&leftPanelTabValue=PROBLEM


https://www.geeksforgeeks.org/problems/largest-element-in-array4009/0?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=largest-element-in-array

Here, we will discuss three different  methods to find the maximum element among the given elements of the array. Method discussed in this page are given below,

Method 1: Simple iterative solution

Method 2: Top-Down recursive approach

Method 3: Bottom-Up recursive approach

Method 1 :-
Take a variable say max_element and assign it with value INT_MIN.

Run a loop form [0, N-1] and check,

If(arr[i]>max_element) then, set max_element = arr[i]

At last print the value of max_element.

Largest number in an array in C++

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){

  int arr[]={10, 89, 67, 56, 45, 78};
  int n = sizeof(arr)/sizeof(arr[0]);
  int max_element = INT_MIN;

  for(int i=0; i<n; i++){ if(arr[i]>max_element)
      max_element = arr[i];
  }

  cout<<max_element;
}

```
Output :
89

 Let's go through a **dry run** of your code step by step. We’ll trace the function for the input array `{10, 89, 67, 56, 45, 78}` to understand how the recursion works.

### Dry Run:

1. **Driver Code:**
   - **Line 12:**  
     `int arr[] = {10, 89, 67, 56, 45, 78};`  
     - Array `arr[]` is initialized with 6 elements.
   
   - **Line 13:**  
     `int n = sizeof(arr) / sizeof(arr[0]);`  
     - `sizeof(arr)` gives the total size of the array in bytes. In this case, `sizeof(arr)` is `6 * 4 = 24` bytes (assuming `int` is 4 bytes).
     - `sizeof(arr[0])` gives the size of one element, which is 4 bytes.
     - `n = 24 / 4 = 6`. Hence, `n = 6`.

   - **Line 15:**  
     `cout << getmax(arr, n);`  
     - Calls the function `getmax(arr, 6)`. 

---

2. **Function Call: `getmax(arr, 6)`**
   - **Line 5:**  
     `if (n == 1) return arr[0];`  
     - Since `n != 1` (n = 6), we proceed to the next line.
   
   - **Line 7:**  
     `return max(arr[n-1], getmax(arr, n-1));`  
     - `arr[n-1] = arr[5] = 78`. Now the function recursively calls `getmax(arr, 5)`.

---

3. **Function Call: `getmax(arr, 5)`**
   - **Line 5:**  
     `if (n == 1) return arr[0];`  
     - Since `n != 1` (n = 5), we proceed to the next line.

   - **Line 7:**  
     `return max(arr[n-1], getmax(arr, n-1));`  
     - `arr[n-1] = arr[4] = 45`. Now the function recursively calls `getmax(arr, 4)`.

---

4. **Function Call: `getmax(arr, 4)`**
   - **Line 5:**  
     `if (n == 1) return arr[0];`  
     - Since `n != 1` (n = 4), we proceed to the next line.

   - **Line 7:**  
     `return max(arr[n-1], getmax(arr, n-1));`  
     - `arr[n-1] = arr[3] = 56`. Now the function recursively calls `getmax(arr, 3)`.

---

5. **Function Call: `getmax(arr, 3)`**
   - **Line 5:**  
     `if (n == 1) return arr[0];`  
     - Since `n != 1` (n = 3), we proceed to the next line.

   - **Line 7:**  
     `return max(arr[n-1], getmax(arr, n-1));`  
     - `arr[n-1] = arr[2] = 67`. Now the function recursively calls `getmax(arr, 2)`.

---

6. **Function Call: `getmax(arr, 2)`**
   - **Line 5:**  
     `if (n == 1) return arr[0];`  
     - Since `n != 1` (n = 2), we proceed to the next line.

   - **Line 7:**  
     `return max(arr[n-1], getmax(arr, n-1));`  
     - `arr[n-1] = arr[1] = 89`. Now the function recursively calls `getmax(arr, 1)`.

---

7. **Function Call: `getmax(arr, 1)`**
   - **Line 5:**  
     `if (n == 1) return arr[0];`  
     - Since `n == 1`, the function returns `arr[0] = 10`.

---

### Returning the Values (Unwinding the Recursion):

Now that the base case is reached and the recursion starts to unwind, each step will compare values and return the maximum.

8. **Back to `getmax(arr, 2)`**
   - `max(arr[1], getmax(arr, 1))`  
   - `max(89, 10)`  
   - Returns `89`.

9. **Back to `getmax(arr, 3)`**
   - `max(arr[2], getmax(arr, 2))`  
   - `max(67, 89)`  
   - Returns `89`.

10. **Back to `getmax(arr, 4)`**
    - `max(arr[3], getmax(arr, 3))`  
    - `max(56, 89)`  
    - Returns `89`.

11. **Back to `getmax(arr, 5)`**
    - `max(arr[4], getmax(arr, 4))`  
    - `max(45, 89)`  
    - Returns `89`.

12. **Back to `getmax(arr, 6)`**
    - `max(arr[5], getmax(arr, 5))`  
    - `max(78, 89)`  
    - Returns `89`.

### Final Output:
- The maximum element in the array is `89`, and this value is printed by the `cout` statement in the `main()` function.

---

### Summary of Recursive Steps:

- `getmax(arr, 1)` returns 10.
- `getmax(arr, 2)` returns max(89, 10) = 89.
- `getmax(arr, 3)` returns max(67, 89) = 89.
- `getmax(arr, 4)` returns max(56, 89) = 89.
- `getmax(arr, 5)` returns max(45, 89) = 89.
- `getmax(arr, 6)` returns max(78, 89) = 89.

Thus, the maximum element `89` is found using recursion.

**
Method 2 (Using Recursion):**

Create a recursive function say getmax(int arr[], int n)

Base condition : If(n==1) return arr[0]

Otherwise return max(arr[n-1], getmax( arr, n-1))
```cpp
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int getmax(int arr[], int n){
   if(n==1) return arr[0];

   return max(arr[n-1], getmax(arr, n-1));
}
//Driver Code
int main(){

   int arr[]={10, 89, 67, 56, 45, 78};
   int n = sizeof(arr)/sizeof(arr[0]);

   cout<<getmax(arr, n);
}
```
Output :
89
---




---
**Method 3 (Using Recursion)**

Call a function : maximum(int arr[], int i, int end)

With initial call up values as maximum(arr, 0, end)

Initially passing end as the index of last array element

Initially passing ‘i’ as 0

Recursively reach iteration where reading 2nd last element

Find larger between 2nd last and last array elements

And return the result to max value of the previous recursive iteration

In each of the remaining recursive callups find the largest b/w current array index element and current max value

Pass final max value from last recursive callup to main and print
---
Method 3 : Code in C++

```cpp
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int maximum(int arr[], int i, int end)
{
   int max;

   if(i == end-1)
     return (arr[i] > arr[i + 1]) ? arr[i] : arr[i + 1];

   max = maximum(arr, i + 1, end);

   return (arr[i] > max) ? arr[i] : max;
}
//Driver Code
int main(){

   int arr[]={10, 89, 67, 56, 45, 78};
   int n = sizeof(arr)/sizeof(arr[0]);

   cout<<maximum(arr, 0, n-1);
}

```
Output :
89
