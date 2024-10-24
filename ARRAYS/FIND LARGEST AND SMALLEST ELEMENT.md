Here, we will discuss the following methods to find the smallest and largest element in the given input array. Method discuss are :

Method 1 : Iterative Approach
Method 2 : Top-down recursion
Method 3 : Bottom up Recursion
Method 1 :
You can check out the following Pages to know about the iterative algorithm to find the smallest element of the array and the largest element of the array.


Largest and Smallest element
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){

    int arr[] = {10, 67, 89, 78, 34, 2, 95};
    int n = sizeof(arr)/sizeof(arr[0]);

    int smallest = INT_MAX, largest = INT_MIN;

    for(int i=0; i<n; i++){ if(smallest > arr[i])
         smallest = arr[i];
       if(largest < arr[i])
         largest = arr[i];
    }

   cout<<smallest<<endl<<largest;
}

```
Output :
2
95

Method 2 :
You can check out the following Pages to know about the top down recursive algorithm to find the smallest element of the array and the largest element of the array.

C++ Program to find Smallest Element
C++ Program to find Largest Element
Let's see How Recursive Calls were made to find the minimum element of the array.

Let's the input array is arr[5] = [45, 78, 90, 23, 10], n = 5
Initially we pass arr and 5 to min_element(arr, 5) function, then
min_element(arr, 5) return min(arr[4], min_element(arr, 4))
min_element(arr, 4) return min(arr[3], min_element(arr, 3))
min_element(arr, 3) return min(arr[2], min_element(arr, 2))
min_element(arr, 2) return min(arr[1], min_element(arr, 1))
min_element(arr, 1) return arr[0]
In this way recursive calls will help to find the minimum element among the 5 elements of the given input array.
```cpp
#include<bits/stdc++.h>
using namespace std;
int min_element(int arr[], int n)
{

   if (n == 1)
     return arr[0];

   return min(arr[n-1], min_element(arr, n-1));
}

int max_element(int arr[], int n){

   if(n==1)
    return arr[0];

   return max(arr[n-1], max_element(arr, n-1));
}

int main(){

  int arr[] = {10, 67, 89, 78, 34, 2, 95};
  int n = sizeof(arr)/sizeof(arr[0]);

  cout<<min_element(arr, n)<<endl<<max_element(arr, n);
}

```
Output :
2
95
Method 3 :
You can check out the following Pages to know about the bottom up recursive algorithm to find the smallest element of the array and the largest element of the array.

```cpp
#include<bits/stdc++.h>
using namespace std;

int minimum(int arr[], int i, int end)
{
   int min;

   if(i == end-1)
    return (arr[i] < arr[i + 1]) ? arr[i] : arr[i + 1];

   min = minimum(arr, i + 1, end);

   return (arr[i] < min) ? arr[i] : min; } int maximum(int arr[], int i, int end) { int max; if(i == end-1) return (arr[i] > arr[i + 1]) ? arr[i] : arr[i + 1];

   max = maximum(arr, i + 1, end);

   return (arr[i] > max) ? arr[i] : max;
}
int main(){

   int arr[] = {10, 67, 89, 78, 34, 2, 95};
   int n = sizeof(arr)/sizeof(arr[0]);

   cout<<minimum(arr, 0, n-1)<<endl<<maximum(arr, 0, n-1);
}

```

2
95
