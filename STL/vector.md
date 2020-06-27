# Vector
## Introduction
Vector is one of the most powerful Data Type in ***C++ programming language*** and very much helpful for competitive programmers. The concept of vector is almost same as C programming language’s ***Array***. However, in C++, we call the vector ***“A Container”***. A container can contain everything such as *<ins>`integers, doubles, characters, bools, strings, structures`</inS>* and a vector can contain *<ins>`some vectors`</ins>* too. But the most important feature of vector is –***“Its memory is allocated dynamically.”*** We can change its length at any time and you can perform many operations that is not possible for C language’s array. We will see and learn all of these things gradually in a proper way.
<br/>
<br/>
## Header File
We have to include an extra header file to use this data type. That is- <br/>
`#include <vector>`<br/>
Under this header file, we can access all the library functions that can be used for vector data type.
<br/>
<br/>
## Declaration and initialization of a vector
We can declare a vector in several ways. Let us see them one by one and understand their differences gradually.
  - `vector < Datatype > MyVector;`<br/>
Using this format, we can declare a vector. Now we can see that the size of the vector is not mentioned here. That means **“we have not allocated any memory for this vector.”** In this case if we want to add any value (of the datatype mentioned inside), we have to use a library function `push_back()`. For example, if we want to store 55, 72, 89 and 100 into an integer vector, we have to perform these:
```cpp
    vector < int > v;
    v.push_back(55);
    v.push_back(72);
    v.push_back(89);
    v.push_back(100);
```
Alternatively, we can write them also in a single line using commas, like this-
```cpp
    vector < int > v;
    v.push_back(55), v.push_back(72), v.push_back(89), v.push_back(100);
```
The size of vector  `v` will be as much element we insert into the vector using `push_back()` function. 
  - `vector < Datatype > MyVector(n);`     where n = size of the vector.<br/>
Thus we can initially allocate the memory needed for our vector like this. This method will give us two extra benefit:
    - This will set the values of all index to 0 automatically.
    - We can now access any index form 0 to size-1 inclusively by <br/>`“MyVector[i]”`; where i = index.<br/>
But still we can change the size of the vector at any time. Besides, we can also store more than n elements into the vector (if needed). Using `push_back()`, we can add elements from index n to maximum size.

Suppose, we are declaring a vector of length 3 and store 3 values into the vector. we have to do it like-
```cpp
    vector < int > v(3);
    v[0] = 29, v[1] = 37, v[2] = 23;
```

Now if we want to add more elements, we can do it by simply using `push_back()`. <br/>
```cpp
    v.push_back(18), v.push_back(97);
```
**Now the size of the vector is increased from three to five**.
