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
    
      	return 0;
    }
    ```
2. **ITERATOR :**  
3. **PRINTING A SET :** 
4. **ERASE :**
5. **SIZE :**
6. **FIND AND COUNT :**
7. **SWAP :**
8. **UPPER AND LOWER :** 
