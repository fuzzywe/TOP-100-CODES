Method 1 : Using Iteration
Method 2 : Top-down recursive approach
Method 3 : Bottom-up recursive approach.

 ---
Method 1 :
Declare a variable sum and initialize it to 0 i.e, sum=0
Run a loop from 0 to n,
Set sum = sum + arr[i]
```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr[] = {10, 20, 30, 50, 89};

   int n = sizeof(arr)/sizeof(arr[0]); 

   int sum =0;

   for(int i=0; i<n; i++){
      sum += arr[i];
   }

   cout<<sum;
}
```
Output :
199


---
Method 2 :
Create a recursive function say getSum(int arr[], int index, int len)

If(index==len-1) return arr[index]

Otherwise, return (arr[index] + getSum(arr, index+1, len))

```cpp
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int getSum(int arr[], int index, int len){

     if(index==len-1)
      return arr[index];

     return arr[index] + getSum(arr, index+1, len);
}
int main(){

   int arr[] = {10, 20, 30, 50, 89};

   int n = sizeof(arr)/sizeof(arr[0]); 

   cout<<getSum(arr, 0, n);
}
```
Output :
199

---
Create a recursive function say getSum(int arr[], int index)

If(index==0) return arr[index]

Otherwise, return (arr[index] + getSum(arr, index-1))

```cpp
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int getSum(int arr[], int index){

   if(index==0)
     return arr[index];

   return arr[index] + getSum(arr, index-1);
}
int main(){

   int arr[] = {10, 20, 30, 50, 89};

   int n = sizeof(arr)/sizeof(arr[0]); 

   cout<<getSum(arr, n-1);
}

```
Output :
199
