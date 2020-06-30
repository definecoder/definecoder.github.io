# Vector

## Introduction

Vector is one of the most powerful Data Type in ***C++ programming language*** and very much helpful for competitive programmers. The concept of vector is almost same as C programming language’s ***Array***. However, in C++, we call the vector ***“A Container”***. As a container, a vector can contain everything such as *<ins>`integers, doubles, characters, bools, strings, structures`</inS>* and a vector can contain *<ins>`some vectors`</ins>* too. But the most important feature of vector is –***“Its memory is allocated dynamically.”***  We can change its length at any time and you can perform many operations that is not possible for C language’s array. We will see and learn all of these things gradually in a proper way.

***

### Why should we learn vector?
- We can change the size of a vector at any time
- We can delete any element at any time
- We can insert new elements at any place
- We can set all the value of all elements to an specific value without using loops
- We can copy one vector to another without using loops
- And so many things we can perform using vector which is not possible using traditional array

***

## Header File

We have to include an extra header file to use this data type. That is- `#include <vector>`. Under this header file, we can access all the library functions that can be used for vector data type.

## Declaration and initialization of a vector

We can declare a vector in several ways. Let us see some of them at a glance and then move forward.

- Type-01 - ***Creating an empty Vector***

    ```c++
        vector < int > v;
    ```
        
- Type-02 - ***Specifying size and initializing all values***
    - there are two criterias
        - 1
            ```cpp
                int n = 7;
                vector < int > v(n);
                
                // This sets all elements to 0 automatically
                // Print the vector just to be made sure
                cout << "v = ";
                for(int x : v) {
                    cout << x << " ";
                }
                cout << endl;
            ```
            
                Output:
                0 0 0 0 0 0 0
    
            - This sets all elements to 0 automatically.
            
        - 2
        
            ```cpp
                int n = 7;
                vector < int > v(n, 10);   //The 7 elements of the vector is now 10
        
                // Print the vector just to be made sure
                cout << "v = ";
                for(int x : v)
                    cout << x << " ";
                cout << endl;
            ```
            
                Output:
                10 10 10 10 10 10 10


- Type-03 - ***Initializing like arrays***
    - We can do it in 2 different styles
        - Style-A
            
            ```cpp
                vector < char > v {'d', 'e', 'f', 'i', 'n', 'e', 'c', 'o', 'd', 'e', 'r'};
        
                // Print the vector just to be made sure
                cout << "v = ";
                for(char x : v) {
                    cout << x;
                }
                cout << endl;
            ```
            
                Output:
                definecoder


        - Style-B - We can use an equal sign too
            
            ```cpp
                vector < double > v = {'d', 'e', 'f', 'i', 'n', 'e', 'c', 'o', 'd', 'e', 'r'};
        
                // Print the vector just to be made sure
                cout << "v = ";
                for(char x : v)
                    cout << x;
                cout << endl;
            ```
            
                Output:
                definecoder


- Type-04 - ***Initializing from an array***
    ```cpp
        int arr[] = {10, 20, 30};
        int n = sizeof(arr) / sizeof(arr[0]);
        vector < int > v(arr, arr + n);
        
        // Print the vector just to be made sure
        cout << "v = ";
        for(int x : v)
            cout << x << " ";
        cout << endl;
    ```
    
        Output:
        10 20 30


- Type-05 - ***Initializing from another vector***
    ```cpp
        vector < int > motherVector {8, 4, 2, 0, 1};
        vector < int > v(motherVector.begin(), motherVector.end());
        
        // Print the vector just to be made sure
        cout << "v = ";
        for(int x : v)
            cout << x << " ";
        cout << endl;
    ```
    
        Output:
        8 4 2 0 1


***

### What operations can we make with an empty vector?

- We can push elements into it using `push_back()` function. The syntax is like `VariableName.push_back(value)`. We can push as much elements as we need (but within the range).

    ```cpp
        vector < char > v;
        v.push_back('d'), v.push_back('e'), v.push_back('f');
        v.push_back('i'), v.push_back('n'), v.push_back('e');
        //And so on...
    
        // Print the vector just to be made sure
        cout << "v = ";
        for(char x : v) {
            cout << x;
        }
        cout << endl;
    ```
    
        Output:
        define


- The most important thing, when we declare an empty vector, is to have in mind that after declaration, the size of the vector is 0. Then when we push elements one by one, the size of the vector gradually increases. For example, in the previous code - **`"after initialization, the size was 0. Then we pushed 6 elements into the vector. Now The size of the vector is 6."`**

- We can check the size of the vector at any time using `size()` function. The syntax is `VariableName.size()`. Compile and run the following code to make it clear.

    ```cpp
        vector < double > v;
        cout << "After declaration, size = " << v.size() << endl;
        v.push_back(10.5);
        cout << "After adding first element, size = " << v.size() << endl;
        v.push_back(13.684);
        cout << "After adding one more element, size = " << v.size() << endl;
        v.push_back(18.12345);
        cout << "After adding one more element, size = " << v.size() << endl;
    ```

        Output:
        After declaration, size = 0
        After adding first element, size = 1
        After adding one more element, size = 2
        After adding one more element, size = 3

- We can also assign values to the vector after declaration as shown below.

    ```cpp
        vector < int > v;
        v = {10, 20, 30, 40};
    ```

***

### Which things should we be aware of after declaring an emtpy vector?

- We cannot add elements without using `push_back()` function.
- We cannot just make the following operations:

    ```cpp
        vector < int > v;
        v[0] = 10;
        v[1] = 20;
        v[2] = 30;
    ```

    or,

    ```cpp
        vector < int > v;
        for(int i = 0; i < 10; i++) {
            cin >> v[i];
        }
    ```

- We will get a **runtime error** as we are accessing a memory that we do not have. The question is why? The answer is quite simple - **"An empty vector does not provide any memory for its elements. When we use `push_back()` function to add new elements, it provides memory for the elements."** But if we want to add memories for some elements to our vector, we have to use `resize()` function. The syntax is `VariableName.resize(NewSize)`. **Then we can access indexs form 0 to NewSize - 1.**
- So we have to use `v.Push_back(10), v.push_back(20), v.push_back(30)` in the first one. We can handle the second one like this:

    ```cpp
        vector < int > v;
        for(int i = 0; i < 10; i++) {
            int x;
            cin >> x;
            v.push_back(x);
        }
    ```

- Or we can use resize the vector and access indexs from 0 to NewSize - 1.

    ```cpp
        vector < int > v;
        v.resize(10);
        for(int i = 0; i < 10; i++) {
            cin >> v[i];
        }
    ```

- Suppose, we have declared an empty vector and then pushed 5 elements into it. After those pushing, we can change any of those value using `VariableName[index] = value`. See the following code:

    ```cpp
        vector < int > v;
        v.push_back(10), v.push_back(11), v.push_back(12), v.push_back(13), v.push_back(14);
        v[0] = 100;
        v[1] = 200;
        v[2] = 300, v[3] = 400, v[4] = 500;
    ```

- So, the lesson is **"We cannot access an index that has no allocation in the memory."**

***

### What happens when we use `resize()` function?

- Suppose we have a vector of size 5. Now we use `resize()` function to change the size of the vector to 10. After this operation, the first elements of our vector remains the same as it was before. Besides, we get (10 - 5 =) 5 extra indexes to access. Initially these new 5 indexes will contain 0 for an integer vector! Run the code:

    ```cpp
        vector < int > v{1, 2, 3, 4, 5};
        v.resize(10);
        for(int x : v){
            cout << x << " ";
        }
        cout << endl;
    ```

        Output:
        1 2 3 4 5 0 0 0 0 0

- The big question in our mind is **What happens after resize if the data type is not integer!** The answer is **If the datatype is `int`, `double`, `long int` or number related anything, the value is automatically set to 0. And if the data type is `char` or `string` related something, each index will contain a `NULL` character!**

- Now suppose, we have a vector of length 7. We resize if to length 5. Then these 5 elements remains the same. Just those last elements get deleted.

    ```cpp
        vector < int > v{1, 2, 3, 4, 5, 6, 7};
        v.resize(5);
        for(int x : v){
            cout << x << " ";
        }
        cout << endl;
    ```
        Output:
        1 2 3 4 5

***

### What if we want all of the elements of our vector become 0 (for number types) or NULL (for character types) after resize?

- Use `clear()` function before resize. The syntax of `clear()` function is `VariableName.clear()`.

    ```cpp
        vector < int > v{1, 2, 3, 4, 5, 6, 7};
        v.clear();
        v.resize(10);
        for(int x : v){
            cout << x << " ";
        }
        cout << endl;
    ```

        Output:
        0 0 0 0 0 0 0 0 0 0

- **`clear()` function deletes all the elements of the vector and the vector becomes empty. And when we resize an empty vector, all indexes will contain 0 (or NULL) by default.**

***

## The last 4 questions explains how we are going to insert new elements to our vector under different circumstances. Now we will see a list of some functions along with a short description.

***

### Important Iterator Functions

| Function     |                                                   Work of the function                                                  |
|--------------|-------------------------------------------------------------------------------------------------------------------------|
| **begin()**  | Returns an iterator pointing to the first element of the vector                                                         |
| **end()**    | Returns an iterator pointing to the theoretical element that follows the last element in a vector                       |
| **rbegin()** | Returns a reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first. |
| **rend()**   | Returns a reverse iterator pointing to the first element in the vector (reverse end).                                   |

***

### Important Capacity Functions

|       Function      |                                         Work of the function                                        |
|---------------------|-----------------------------------------------------------------------------------------------------|
| **size()**          | Returns the number of elements in the vector                                                        |
| **max_size()**      | Returns the maximum number of elements that the vetor can hold                                      |
| **capacity()**      | Returns the size of the storage space currently allocated to the vector expressed as number         |
| **resize(n)**       | Resizes the container so that it can contain `'n'` elements                                         |
| **empty()**         | Returns whether the container is empty                                                              |
| **shrink_to_fit()** | Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity |
| **reserve(n)**      | Requests that the vector capacity be at least enough to contain `'n'` elements                      |

***

### Element Access Functions

|          Function          |                                          Work of the function                                          |
|----------------------------|--------------------------------------------------------------------------------------------------------|
| **reference operator [g]** | Returns a reference to the element at position `'g'` in the vector                                     |
| **at()**                   | Returns a reference to the element at position `'g'` in the vector                                     |
| **front()**                | Returns a reference to the first element in the vector                                                 |
| **beck()**                 | Returns a reference to the last element of the vector                                                  |
| **data()**                 | Returns a direct pointer to the memory array used internally by the vector to store its owned elements |

***

### Modifiers

| Function        | Work of the function                                                                           |
|-----------------|------------------------------------------------------------------------------------------------|
| **assign()**    | It assigns new value to the vector elements by replacing old ones                              |
| **push_back()** | It pushes the elements into the vector form the back                                           |
| **pop_back()**  | It removes elements from a vector from the back                                                |
| **insert()**    | It inserts new elements before the element at specified position                               |
| **erase()**     | It removes elements from the specified position or specified range                             |
| **swap()**      | It is used to swap the content of one vector with another vector of same type, size may differ |
| **clear()**     | It is used to remove all the elements of the vector container                                  |

***










