# Set in C++

## Introduction
Set is a container which has very special for its functionality. This have some variants which are also discussed here later on.  The main features of default set is :
- It stores each element once and don't allow repeated elements. Which means default set stores only distinct elements.
- It keeps elements in sorted order. You can customize how the elements will be sorted. But By default it keeps the elements in ascending order. 
- You can use other variants of the set like multiset, unordered_set, unordered_multiset as you need.

## Declaration:
First of all you need to add the header file of set to use any functionality of set. To do that you have to add the following header :
```cpp
#include <set>
```
After adding the header you can declare your set using this code:
```cpp
set < data_type > MySet;
// For example you may declare a set of integers nemmed MyIntSet using :
set < int > MyIntSet;
```
In the place of data_type you may use any data type like integer, double, charecter, string, pair etc.

## Basic operations 
The often used operations in set are : 
- Insert
- Iterator
- Printing a set
- Erase
- Size
- Find and Count
- Swap
- Upper and Lower Bound

## Implementation of the basic operations in set
1. **INSERT :** Insertion is a very basic operation of set. Using this operation you can insert a new element into your set. But remember insersion will add a new element if that element was absent there before because set do not allows same element's occurance twice. So lets see the implementation : 
    ```cpp
    #include <iostream> 
    #include <set> 
  
    using namespace std; 

    int main(){
   	
       	set < int > MySet; // Declaring MySet
    
       	MySet.insert(45); // Inserting 45
       	MySet.insert(23); // Inserting 23
       	MySet.insert(11); // Inserting 11
       	MySet.insert(45); 
       	// 45 is already in the set so nothing happens
        // So, Now the set should be : 11 , 23 , 45
        
      	return 0;
    }
    ```
    Here you can see when we tried to insert 45 for the second time it was not inserted into the set. You can also insert variables which are taken from the user.   
2. **ITERATOR :**  
3. **PRINTING A SET :** Printing of a set can be done in two ways. First one is using iterator and the second one is using C++11 short cut feature. We will include both here. Lets see: 
    - _**Using Iterator**_ : As you know iterator is a poiunter for the STL datatype or containers, It is very useful to access the elements in a set. First of all you need to declare an iterator of the type of the set that you want to work with.  Then you have to iterate through the set using that iterator that you declared. Lest see the code for better understanding.
    ```cpp
    #include <iostream> 
    #include <set> 
    
    using namespace std; 
    
    int main(){
    
        set < int > MySet; // Declaring MySet
        set < int >::iterator it; 
        // Declaring an iterator to point to the elements of MySet
    
        MySet.insert(45); // Inserting 45
        MySet.insert(23); // Inserting 23
        MySet.insert(11); // Inserting 11
        MySet.insert(45); 
        // 45 is already in the set so nothing happens
        // So, Now the set should be : 11 , 23 , 45
    
        cout << "The Elements of the set are : " << endl;
    
        for( it=MySet.begin() ; it != MySet.end() ; it++ )
        {
            // Dereferencing the pointer( Iterator ) to see the value
            cout << *it << " ";
        } 
    
        cout << endl ;
    
        return 0;
    }
    ```
    **OUTPUT :**
    ```
    The Elements of the set are : 
    11 23 45 
    ```
    - _**Special Format of C++11**_ :
4. **ERASE :**
5. **SIZE :**
6. **FIND AND COUNT :**
7. **SWAP :**
8. **UPPER AND LOWER :** 
