https://www.geeksforgeeks.org/problems/second-largest3735/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=second-largest

Method 1: Uses two loops find second smallest
Method 2: Using a single loop to find second smallest
Method 1 :
Declare a variable say smallest = arr[0], that variable hold the first minimum value of the array.
Run a loop and check if(arr[i]<smallest) then set smallest = arr[i].
Now, take a variable say sec_smallest = INT_MAX
Now, run a loop over the array, and check
If(arr[i]!=smallest && arr[i] < sec_smallest), then set sec_smallest = arr[i]
At last Print(sec_smallest)
```cpp
#include<bits/stdc++.h>
using namespace std;

int secSmallest(int arr[], int n)
{
   // assigning first element as smallest temporarily
   int smallest = arr[0];

   // we find the smallest element here
   for (int i=0; i < n; i++){
     if(arr[i] < smallest)
       smallest = arr[i];
   }

   // temporarily assinging largest max value
   int sec_smallest = INT_MAX;

   // finding second smallest here
   for (int i=0; i < n; i++){
      if(arr[i] != smallest && arr[i] < sec_smallest)
        sec_smallest = arr[i];
   }

   return sec_smallest;

}
int main()
{
    int arr[] = {70, 40, 30, 20, 10, 90};

    int n = sizeof(arr)/sizeof(arr[0]); 

    cout<<secSmallest(arr, n);
}
```
Output


Find Smallest Element in an Array
 
Find the Smallest and largest element in an array

Calculate the sum of elements in an array 

Reverse an Array

Sort first half in ascending order and second half in descending 

Method 2 :

Take Two variables say first = INT_MAX and second = INT_MAX to hold the first and second smallest elements respectively.

Run a loop to iterate over the entire array.

Check if (arr[i]<first) then set second = first and first = arr[i].

Else check if(second > arr[i]) then set second = arr[i]

After complete iteration print second.
Second smallest element
```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr[] ={ 90, 78, 67, 56, 7, 61, 10};
   int n = sizeof(arr)/sizeof(arr[0]);

   int first = INT_MAX, second = INT_MAX;

   for(int i=0; i<n; i++){
       if(arr[i] < first){ second = first; first = arr[i]; } else if(second>arr[i])
           second = arr[i];
    }

    cout<<second;
}

```
Output
10
