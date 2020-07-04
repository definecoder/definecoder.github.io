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
- Find
- Erase
- Size
- Count
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
2. **ITERATOR :**  Iterators are used to point out an element in the set as well as any other container in STL. [You can check this link to know more about iterators](https://definecoder.github.io/STL/iterator). Iterators are very important to access any element in the set. Lets see the list of the iterators for set and the code: 

    |                Function                 |                     Work of the function                     |
    |:--------------------------------------:|:-------------------------------------------------------------:|
    |     begin() <br> **MySet.begin()**     |   returns iterator to the **begin** of the set                |
    |       end() <br> **MySet.end()**       |    returns iterator to the **end** of the set                 |
    | advance() <br> **MySet.advance(it,x)** | _increments_ the position of the **it** by **x**              |
    |    prev() <br> **MySet.prev(it,x)**    | returns _decrement_ of the position of the **it** by **x**    |
    |    next() <br> **MySet.next(it,x)**    |    returns _increment_ of the position of the **it** by **x** |   
    
    **Implementation :**
    
    ```cpp
    #include <iostream> 
    #include <set> 
    #include <iterator> 
    // remember to include the header of iterator when you will use these functions

    using namespace std; 
    
    void print_set (set < int > temp){
    for( auto an_element : temp ) 
    // Taking elements from temp set to an_element one by one
    {
        // Here an_element is a member of temp set
        cout << an_element << " ";
    } 
    cout << endl;
    }
    
    int main(){
    
        set < int > MySet; // Declaring MySet
        set < int >::iterator it; // Declaring an iterator of integer set
    
        MySet.insert(45); // Inserting 45
        MySet.insert(23); // Inserting 23
        MySet.insert(11); // Inserting 11
        MySet.insert(17); // Inserting 17
        MySet.insert(45); 
        // 45 is already in the set so nothing happens
        // So, Now the set should be : 11 , 17 , 23 , 45
        
        cout << "The Elements of the set are : " << endl;
        print_set(MySet); // Printing MySet (will be disscussed below)
        cout << endl;
    
        it = MySet.begin();
        cout << "value of MySet.begin() is : " << *it << endl;
        
        it = MySet.end();
        it--; // decrementing it because end pointer does not contain any value
        cout << "value of [MySet.end() - 1] is : " << *it << endl;
    
        it = MySet.begin();
        advance(it,2);
        cout << "value of advance(MySet.begin(),2) is : " << *it << endl;
    
        it = MySet.begin();
        it = next(it,3);
        cout << "value of next(MySet.begin(),3) is : " << *it << endl;
    
        it = MySet.end();
        it = prev(it,4);
        cout << "value of prev(MySet.end(),4) is : " << *it << endl;
    
        return 0;
    }
    ```
    
    **OUTPUT :**
    
    ```cpp
    The Elements of the set are : 
    11 17 23 45 

    value of MySet.begin() is : 11
    value of [MySet.end() - 1] is : 45
    value of advance(MySet.begin(),2) is : 23
    value of next(MySet.begin(),3) is : 45
    value of prev(MySet.end(),4) is : 11
    ```

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
    
    ```cpp
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
    
    ```cpp
    The Elements of the set are : 
    11 23 45 
    ``` 
    
    I prefer to use this format because it is simple and easy to use. **BUT REMEMBER THIS CAN ONLY BE USED IN C++11 OR HIGHER VERSION OF CPP** . 
    - **User-defined function to print a set :** Now we will write an user-defined function which will print a set on its own. As a perameter it will take the set (call by value). As it will sent a copy of the set,  it won't do any change to the original set in the main function. Lets see the function's implementation: 
    
    ```cpp
    void print_set (set < int > temp){
    for( auto an_element : temp ) 
    // Taking elements from temp set to an_element one by one
    {
        // Here an_element is a member of temp set
        cout << an_element << " ";
    } 
    cout << endl;
    }
    
    int main(){
    
        set < int > MySet; // Declaring MySet
        
        MySet.insert(45); // Inserting 45
        MySet.insert(23); // Inserting 23
        MySet.insert(11); // Inserting 11
        MySet.insert(45); 
        // 45 is already in the set so nothing happens
        // So, Now the set should be : 11 , 23 , 45
        
        cout << "The Elements of the set are : " << endl;
    
        print_set(MySet); // Printing MySet
    
        return 0;
    }
    ```
        
    **OUTPUT :** 
    
    ```cpp
    The Elements of the set are : 
    11 23 45 
    ``` 
    
4. **FIND :** This function is used to search an element from the set. It returns an iterator which points to the element in the set. If the element is not present in the set it will return the ending positon (` which is called std::end() `) of the set. You can also find the distance of the element using `std::distance(start_iterator,ending_iterator)` function. So, Lets see the implementation of the concepts mentioned above :

    ```cpp
    void print_set (set < int > temp){
    for( auto an_element : temp ) 
    // Taking elements from temp set to an_element one by one
    {
        // Here an_element is a member of temp set
        cout << an_element << " ";
    } 
    cout << endl;
    }
    
    int main(){
    
        set < int > MySet; // Declaring MySet
        set < int >::iterator it; // Declaring an iterator of integer set
    
        MySet.insert(45); // Inserting 45
        MySet.insert(23); // Inserting 23
        MySet.insert(11); // Inserting 11
        MySet.insert(17); // Inserting 17
        MySet.insert(45); 
        // 45 is already in the set so nothing happens
        // So, Now the set should be : 11 , 17 , 23 , 45
        
        cout << "The Elements of the set are : " << endl;
        print_set(MySet); // Printing MySet
        cout << endl;
    
        it = MySet.find(23); // it will now point to 23 in the set
        cout << *it << " is present in index no: " << distance( MySet.begin() , it ) << endl;
        // You can see the value of it by using *it (This is also known as dereferencing)
        // Here distance functions returns the distance between two iterators 
        
        it = MySet.find(25); // it will now point to the end of the set as it is absent in the set
        if(it == MySet.end()) {
            // As 25 is not present it will point to MySet.end()
            cout << "25 is not present in the set" << endl;
        }
    
        return 0;
    }
    ```
    
    **OUTPUT :**
    
    ```cpp
    The Elements of the set are : 
    11 17 23 45 
    
    23 is present in index no: 2
    25 is not present in the set
    ```
    
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
    
    ```cpp
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

8. **SWAP :** Swap is a very simple function. It swaps the elements between two sets. Lets see the code to see the implementation : 
    
    ```cpp
    //Function to print set
    void print_set (set < int > temp){
        for( auto an_element : temp ) 
        // Taking elements from temp set to an_element one by one
        {
            // Here an_element is a member of temp set
            cout << an_element << " ";
        } 
        cout << endl;
    }
    
    int main(){
    
        set < int > setA, setB; // Declaring two sets
        
        setA.insert(1); // Inserting 1
        setA.insert(2); // Inserting 2
        setA.insert(3); // Inserting 3
        // So, Now the setB should be : 1 , 2 , 3
    
        setB.insert(10); // Inserting 10
        setB.insert(20); // Inserting 20
        setB.insert(30); // Inserting 30 
        setB.insert(40); // Inserting 40 
        // So, Now the setB should be : 10 , 20 , 30 , 40
    
        cout << "Before swapping --> \n";
        cout << "setA :: ";
        print_set(setA); // Printing setA
        
        cout << "setB :: ";
        print_set(setB); // Printing setB
    
        setA.swap(setB); // SWAPING between setA and setB
    
        cout << "\nAfter swapping --> \n";
        cout << "setA :: ";
        print_set(setA); // Printing setA
        
        cout << "setB :: ";
        print_set(setB); // Printing setB
    
        return 0;
    }
    ```
    
    **OUTPUT :**
    
    ```cpp
    Before swapping --> 
    setA :: 1 2 3 
    setB :: 10 20 30 40 
    
    After swapping --> 
    setA :: 10 20 30 40 
    setB :: 1 2 3 
    ```

8. **UPPER AND LOWER BOUND:** 
Upper and lower_bound is very important function for certain cases. Using find function you can search for an element if that element is not present in the set then std::find won't be able to find that element. But using Upper and lower bound you can find element which is strictly bigger (smallest number such that this number is bigger than a certain number ~ see the code for better understanding) than a certain number. Lets see the difference between **Upper_bound** and **lower_bound** :
    - **UPPER BOUND :** Suppose you are given a set of integers, `S = { 12, 17, 27, 35, 47, 58, 93 }` Here if you want to know the **upper bound of 24**, it will be **27** which means _**`upper_bound(x) will return an iterator to the first element which is greater than x`**_. But in case of upper bound in the example mentioned above the **uppper_bound(35)** will be **47** because 47 is the first integer in the set which is greater than 35 (_not 35 as it is equal_). So, lets see the code for implementation :
    
    ```cpp
    void print_set (set < int > temp){
    for( auto an_element : temp ) 
    // Taking elements from temp set to an_element one by one
    {
        // Here an_element is a member of temp set
        cout << an_element << " ";
    } 
    cout << endl;
    }
    
    int main(){
    
        set < int > MySet; // Declaring MySet
        set < int >::iterator it; // Declaring an iterator of integer set
    
        MySet.insert(12); 
        MySet.insert(17); 
        MySet.insert(27); 
        MySet.insert(35); 
        MySet.insert(47); 
        MySet.insert(58); 
        MySet.insert(93); 
        // So, Now the set should be : 12 , 17 , 27 , 35, 47, 58, 93
        
        cout << "The Elements of the set are : " << endl;
        print_set(MySet); // Printing MySet
        cout << endl;
    
        it = MySet.upper_bound(24);
        cout << "value of MySet.upper_bound(24) is : " << *it << endl;
        // *it will be 27 because 27 is the first number greater than 24
    
        it = MySet.upper_bound(35);
        cout << "value of MySet.upper_bound(35) is : " << *it << endl;    
        // *it will be 47 because 47 is the first number greater than 35
        // *it is not 35 because they are equal... 
    
        return 0;
    }
    ```
    
    **output :**
    
    ```cpp
    The Elements of the set are : 
    12 17 27 35 47 58 93 
    
    value of MySet.upper_bound(24) is : 27
    value of MySet.upper_bound(35) is : 47
    ```
    - **LOWER BOUND :** Suppose you are given a set of integers as like before, `S = { 12, 17, 27, 35, 47, 58, 93 }` Here if you want to know the **lower bound of 24**, it will be **27** which means _**`lower_bound(x) will return an iterator to the first element which is greater or equal to x`**_. But in case of lower bound in the example mentioned above the **lower_bound(35)** will be **35** because 35 is equal ot the argumant (_as it is equal_). So, lets see the code for implementation :
    
    ```cpp
    void print_set (set < int > temp){
    for( auto an_element : temp ) 
    // Taking elements from temp set to an_element one by one
    {
        // Here an_element is a member of temp set
        cout << an_element << " ";
    } 
    cout << endl;
    }

    int main(){

        set < int > MySet; // Declaring MySet
        set < int >::iterator it; // Declaring an iterator of integer set

        MySet.insert(12); 
        MySet.insert(17); 
        MySet.insert(27); 
        MySet.insert(35); 
        MySet.insert(47); 
        MySet.insert(58); 
        MySet.insert(93); 
        // So, Now the set should be : 12 , 17 , 27 , 35, 47, 58, 93
        
        cout << "The Elements of the set are : " << endl;
        print_set(MySet); // Printing MySet
        cout << endl;

        it = MySet.lower_bound(24);
        cout << "value of MySet.lower_bound(24) is : " << *it << endl;
        // *it will be 27 because 27 is the first number greater or equal to 24

        it = MySet.lower_bound(35);
        cout << "value of MySet.lower_bound(35) is : " << *it << endl;    
        // *it will be 35 because 35 is equal to the argumant
        // *it is will be 47 in case of upper bound

        return 0;
    }
    ```
    
    **output :**
    
    ```cpp
    The Elements of the set are : 
    12 17 27 35 47 58 93 

    value of MySet.lower_bound(24) is : 27
    value of MySet.lower_bound(35) is : 35
    ```
    Hope that you are clear with the basic functons of a set.
