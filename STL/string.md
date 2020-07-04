
# String

To use string first of all you have to add this header **` #include <string> `**

## Declaring and Initializing a String 
It is very easy to declare a string. You can create a string variable nammed as MyString by typing **` string MyString ; `**

You can declare several string togather in a line. You can also _**initialize**_ a string using **` string MyString = "Hello World!" `**. 
You can also do that later in your code.

You can take a string from the user using **` cin >> MySting ; `** which only takes the string _**up to a space**_

If you want to get _**a full line including spaces**_ use this instead  **` getline( cin , MyString ) ; `**

## Basic Sting Operations

Lets say you have two strings **` string a = "Hello " , b = "World" ; `** You can add string **b** after string **a** using **` a = a + b `**
after this opatertion the value of a will be **"Hello World"**. 
That is how you can **concatenate** two strings.

You can delete last charecter on a sting using **` MyString.pop_back() `**

As you know string is an array of charecters so you can access any index (0 to length-1) and change that in constant time. _e.g:_ **` MyString[0] = 'h' ; `**

You can print a string using **` cout << MyString << endl ; `**

You can check the equality of two strings using  **` strA == strB `** and inequality using **` strA != strB `** . 
You can also check which string is lexicographically greater using **` strA > strB `** vice versa.

## String Functions :

| Function                    | Work of the function                                                           |
|-----------------------------|--------------------------------------------------------------------------------|
| **MyString.size()**         | Returns The size of the string                                                 |
| **str1.swap(str2)**         | Swaps the value of str1 and str2                                               |
| **MyString.insert(x,s)**    | Inserts s in the xth index of MyString                                         |
| **MySrting.find(s)**        | Returns initial index of first occurrence of the s in MyString else returns -1 |
| **MySrting.rfind(s)**       | Returns initial index of last occurrence of the s in MyString else returns -1  |
| **MyString.replace(i,j,s)** | Replaces j characters from ith index of MyString with new string s             |
| **stoi(MyString)**          | Returns the integer converted form of MyString                                 |
| **MyString.substr(i,k)**    | Returns a substing of length k from ith index of MyString                      |
| **MyString.erase(i)**       | Erases every element from ith index to the end of MyString                     |
| **MyString.clear()**        | Erases every element in MyStirng                                               |
| **MyString.empty()**        | Returns True if  MyString is empty else return false                           |

***

