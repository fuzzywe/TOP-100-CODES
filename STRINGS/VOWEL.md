C++ program to check whether Character is a vowel or consonant
Check Character is Vowel or Consonant in C++
Here, in this section, we will discuss the program to check whether the Character is Vowel or Consonant in C++.


While loop in C
Working:-
Accept character input from the user
Check if the character is any of the vowels in both Lower and Upper case
If yes the print Vowel else print Consonant
We will discuss a few methods. Let us look at method 1 below –

```cpp
// C++ Program to check whether alphabet is vowel or consonant
#include<iostream>
using namespace std;

// main function
int main()
{
    char c;

    c='U';
        
    //checking for vowels	
    if(c=='a'||c=='e'||c=='i'||c=='o'||c=='u'||
    c=='A'||c=='E'||c=='I'||c=='O'||c=='U')
    {
        cout << c << " is a vowel";  //condition true input is vowel
    }
    else
    {
        cout << c << " is a consonant";  //condition false input is consonant
    }

    return 0;
}

```
Output
U is a vowel
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Check whether a character is a alphabet or not

Find the ASCII value of a character

Length of the string without using strlen() function

Method 2
The above method didn’t check for the case where you may have entered a non-alphabet character. Like ‘7’ or ‘[‘ etc.

It would have printed consonant in the above case. Also, we will look at an alternate approach as well.
```cpp
#include<iostream>
using namespace std;

bool isLowercaseVowel(int c){
    // returns true if char matches any of below
    return (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u');
}

bool isUppercaseVowel(int c){
    // returns true if char matches any of below
    return (c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U');
}
int main() {
    char c;
    
    cout << "Enter an alphabet: "; cin >> c;

    // show error message if c is not an alphabet
    if (!isalpha(c))
      printf("Non alphabet");
      
    else if (isLowercaseVowel(c) || isUppercaseVowel(c))
        cout << c << " is a vowel";
        
    else
        cout << c << " is a consonant";

    return 0;
}

```
Output
Enter an alphabet: P
P is a consonant
Method 3
The above function had 2 conditions one for checking if it’s a lowercase vowel and another for checking uppercase vowel.

We can reduce it down to just one single function by forcefully converting the character to uppercase if it wasn’t uppercase already and checking condition only for uppercases.

```cpp
#include<iostream>
using namespace std;

// single function for both uppercase and lowercase
bool isVowel(int c){
    // converts to uppercase if it wasn't already
    c = toupper(c);
    
    // returns true if char matches any of below
    return (c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U');
}

int main() {
    char c;
    
    cout << "Enter an alphabet: "; cin >> c;

    // show error message if c is not an alphabet
    if (!isalpha(c))
      printf("Non alphabet");
      
    else if (isVowel(c))
        cout << c << " is a vowel";
        
    else
        cout << c << " is a consonant";

    return 0;
}

```
Output
Enter an alphabet: e
e is a vowel
While loop in C
Prime Course Trailer

Related Banners
Get PrepInsta Prime & get Access to all 200+ courses offered by PrepInsta in One Subscription

Get Prime
For similar Question click on given button

Top 100 Question
While loop in C
