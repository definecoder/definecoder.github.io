# STACK

## Introduction:
Stack is a type of container adaptor. It is just like a pile of plates kept on top of each other. we can do 2 things with a pile of plates: 
- put a new plate on top  
- remove the top plate
Such an arrangement is called Last In First Out(LIFO) which is not possible with Linked list and array. Stack is specifically designed to operate in a LIFO context, where elements are inserted and extracted only from one end of the container. 

## Header File:
we can use `#include <stack>` to access all the library functions of stack.

## Declaration:
Genaral syntax to declare a stack is : `stack < datatype > MyStack;`.  
we can use any kind of datatype, stracture, container in a stack. Example :
```cpp
stack < int > MyStack; 
stack < char > MyStack;   
stack < vector < string > > MyStack; 
```

