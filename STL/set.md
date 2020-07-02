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
    So, You can print or access the elemets of a set using iterator. 
    - _**Special Format of C++11**_ : This mathod is very easy to use and I prefer to use this type. Because, almost all the datatypes or STL containers support this type of iteration or traversal through the set or any container. Lets see the code to see the implementation :
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
    
        cout << "The Elements of the set are : " << endl;
    
        for( auto an_element : MySet ) // Taking elements from MySet to an_element ome by one
        {
            // Here an_element is a member of MySet
            cout << an_element << " ";
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
    I prefer to use this format because it is simple and easy to use. **BUT REMEMBER THIS CAN ONLY BE USED IN C++11 OR HIGHER VERSION OF CPP** .
4. **FIND :**
5. **ERASE :** This function is used to erase one perticuler element or some elements in a range in the set. So, There are **3** types of the erase function. I am includeing the codes for the **C++11**. [To see the codes for C++98 click on this link.](http://www.cplusplus.com/reference/set/set/erase/). Lets continue with the codes for C++11 and above :
    - **Using constant value :** You can erase a constant value from the set using **`erase (const value_type& val);`** See the code below for better understanding : 
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
    
        MySet.erase(23); // This will erase 23 from the set
    
        cout << "The Elements of the set are : " << endl;
    
        for( auto an_element : MySet ) // Taking elements from MySet to an_element ome by one
        {
            // Here an_element is a member of MySet
            cout << an_element << " ";
        } 
    
        cout << endl ;
    
        return 0;
    }
    ```
    **OUTPUT :**
    ```
    The Elements of the set are : 
    11 45 
    ```
    This is how you can erase a constant value from the set.
    - **Single Element using iterator :** We can also erase an element from the set using iterators. To do that we need to declare an iterator and then pass that iterator in the erase function which will cause deletation of that perticuler element. Lets see the code for better understanding : 
    ```cpp
    #include <iostream> 
    #include <set> 
    
    using namespace std; 
    
    int main(){
    
        set < int > MySet; // Declaring MySet
        set < int >::iterator it; // Declaring Iterator for MySet
    
        MySet.insert(45); // Inserting 45
        MySet.insert(23); // Inserting 23
        MySet.insert(11); // Inserting 11
        MySet.insert(45); 
        // 45 is already in the set so nothing happens
        // So, Now the set should be : 11 , 23 , 45
    
        it = MySet.find(23); // This will get the pointer to 23
        MySet.erase(it); // This will delete the pointed element which is 23
    
        cout << "The Elements of the set are : " << endl;
    
        for( auto an_element : MySet ) // Taking elements from MySet to an_element ome by one
        {
            // Here an_element is a member of MySet
            cout << an_element << " ";
        } 
    
        cout << endl ;
    
        return 0;
    }
    ```
    **OUTPUT :**
    ```
    The Elements of the set are : 
    11 45 
    ```
    - **Erasing a range of number by iterator :** You can even erase a range of numbers from set using iterator. To do that you need to pass two iterator. One is the starting iterator and another one is the ending iterator. This two iterator tells erase function the starting and ending position of the erase operation. Lets see the code for implementation.
    ```cpp
    set < int > MySet; // Declaring MySet
    set < int >::iterator it1, it2; 
    // Declaring Iterator for starting and ending position of erase function

    MySet.insert(45); // Inserting 45
    MySet.insert(23); // Inserting 23
    MySet.insert(11); // Inserting 11
    MySet.insert(17); // Inserting 17
    MySet.insert(94); // Inserting 94
    MySet.insert(45); 
    // 45 is already in the set so nothing happens
    // So, Now the set should be : 11 , 17 , 23 , 45 , 94

    it1 = MySet.find(17); // This will get the starting pointer to 17
    it2 = MySet.find(45); // This will get the ending pointer to 45
    it2++; // always remember to do 1 element increment for the ending iterator
    //because it will remove all elements before it2 not the one that is in it2
    
    MySet.erase(it1,it2); // This will delete 17 23 45 from the set

    cout << "The Elements of the set are : " << endl;

    for( auto an_element : MySet ) // Taking elements from MySet to an_element ome by one
    {
        // Here an_element is a member of MySet
        cout << an_element << " ";
    } 

    cout << endl ;
    ```
    **OUTPUT :**
    ```
    The Elements of the set are : 
    11 94 
    ```
6. **SIZE :** This is very basic function for all the datatypes and containers in STL. It will return how many elements are there in the set. Lets see the code for the implementation :
    ```cpp
    set < int > MySet; // Declaring MySet
    
    MySet.insert(45); // Inserting 45
    MySet.insert(23); // Inserting 23
    MySet.insert(11); // Inserting 11
    MySet.insert(17); // Inserting 17
    MySet.insert(94); // Inserting 94
    MySet.insert(45); 
    // 45 is already in the set so nothing happens
    // So, Now the set should be : 11 , 17 , 23 , 45 , 94

    cout << "The size of MySet is :: " << MySet.size() << endl;
    ```
    **OUTPUT :**
    ```
    The size of MySet is :: 5
    ```
7. **COUNT :** This returns the number of occurance of a perticuler element in a set. As we know default set does not allows the occurance of the same element more than once, so the count will return 1 or 0 only. But in case of _**multiset**_ ( which we will discuss later) count will return how many times you insert a perticuler element into the set. Lets now see the implementation of std::count() in the standard set : 
   ```cpp
    set < int > MySet; // Declaring MySet
    
    MySet.insert(45); // Inserting 45
    MySet.insert(23); // Inserting 23
    MySet.insert(11); // Inserting 11
    MySet.insert(17); // Inserting 17
    MySet.insert(94); // Inserting 94
    MySet.insert(45); 
    // 45 is already in the set so nothing happens
    // So, Now the set should be : 11 , 17 , 23 , 45 , 94

    cout << "45 is present in the set " << MySet.count(45) << " times" << endl;
    ```
    **OUTPUT :**
    ```
    45 is present in the set 1 times
    ``` 
8. **SWAP :**
8. **UPPER AND LOWER :** 
