Method 1: Simple iterative
Method 2: Top Down recursive
Method 3: Bottom Up Recursive
 
Method 1:-
Declare a variable say mini and initialize it with INT_MAX value.

Run a loop from i=0 to i<n and check,

If arr[i] < mini, then set mini = arr[i].

After complete iteration print the value of mini.
```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){

  int arr[] = { 34, 5, 89, 90, 56};
  int n = sizeof(arr)/ sizeof(arr[0]);

  int mini = INT_MAX;

  for(int i=0; i<n; i++){
    if(arr[i]<mini)
      mini = arr[i];
  }

  cout<<mini;
}
```
Output
The smallest : 5



Method 2 (Using Recursion)
In this method we will discuss the recursive approach to find the smallest element in the given array.

Create a recursive function say min_element(int arr[], int n)
Base Condition : If(n==1) return arr[0]
Otherwise, return min(arr[n-1], min(arr, n-1))
```cpp
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int min_element(int arr[], int n)
{
  // if size = 0 means whole array has been traversed
  if (n == 1)
    return arr[0];
  return min(arr[n-1], min_element(arr, n-1));
}

// driver code 
int main()
{
   int arr[] = { 34, 5, 89, 90, 56};
   int n = sizeof(arr)/ sizeof(arr[0]);
   cout << min_element(arr, n);
   return 0;
}
```

// Time complexity: O(N)
// Space complexity: O(1)

Method 3 (Using Bottom up recursion)

Call a function : minimum(int arr[], int i, int end)

With initial call up values as minimum(arr, 0, end)

Initially passing end as the index of last array element

Initially passing ‘i’ as 0

Recursively reach iteration where reading 2nd last element

Find smaller between 2nd last and last array elements

And return the result to min value of the previous recursive iteration

In each of the remaining recursive callups find the smaller b/w current array index element and current min value

Pass final min value from last recursive callup to main and print

```cpp
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int minimum(int arr[], int i, int end)
{
   int min;

   if(i == end-1)
     return (arr[i] < arr[i + 1]) ? arr[i] : arr[i + 1];

   min = minimum(arr, i + 1, end);

   return (arr[i] < min) ? arr[i] : min;
}

// driver code 
int main()
{
   int arr[] = { 34, 5, 89, 90, 56};
   int end = sizeof(arr)/ sizeof(arr[0]) - 1;
   cout << minimum(arr, 0, end);
   return 0;
} 
```
