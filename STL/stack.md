# **STACK**

## **Introduction:**
Stack is a type of container adaptor. It is just like a pile of plates kept on top of each other. we can do 2 things with a pile of plates: 
 - put a new plate on top  
 - remove the top plate
 
Such an arrangement is called Last In First Out(LIFO) which is not possible with Linked list and array. Stack is specifically designed to operate in a LIFO context, where a new element is added at one end called the 'top' of the stack and an element is removed from the same end only.

## **Header File:**
we can use `#include <stack>` to access all the library functions of stack.

## **Declaration:**
Genaral syntax to declare a stack is : `stack < datatype > MyStack;`.  
we can use any kind of datatype, stracture, container in a stack. Example :
```cpp
    stack < int > MyStack; 
    stack < char > MyStack;   
    stack < vector < string > > MyStack; 
```

## **functions:**
There are mainly four functions  which are hugely used in stack. They are:  
 - push()
 - pop()
 - top()
 - empty()
##### push():
push() function is used to input a data in the stack. This function always adds a new data on the top of the container and increases the size of the stack by one. Example:
```cpp
    stack < int > MyStack;
    MyStack.push(5);
    MyStack.push(15);
    MyStack.push(63);
```
In this code, we have inputed some data in "MyStack". After pushing some datas the stack will be {5, 15, 63}. As '63' is the last data we have inserted, so it is on the top of the stack. 

##### pop():
pop() is the opposite of the push() function. It removes the last data inserted in the stack. It decreases the size of the stack by one.The items are popped in the reversed order in which they are pushed.
```cpp
    stack < int > MyStack;
    MyStack.push(5);
    MyStack.push(15);
    MyStack.push(63);
                                //we have pushed 5, 15, 63 in the stack, the stack is{5, 15, 63} now
    MyStack.pop();              //popping 63 from the stack, the stack is {5, 15} now
    MyStack.pop();              //popping 15 from the stack, the stack is {5} now
    MyStack.pop();              //popping 5 from the stack, the stack is empty now
```
pop() function always deletes the data in the reversed order it was pushed. As we pushed 63 at the last it was popped at first.

#### top():
top() function always returns a reference to the top element(the newest) of the stack. Let's see the code:
```cpp
    stack < int > MyStack;
    MyStack.push(5);
    MyStack.push(15);
    MyStack.push(63);
    cout << MyStack.top() << "\n";
```
`OUTPUT : 63`  

In this code '63' is on the top of the stack, so top() function will return '63'. 

#### empty():
empty() function is used to check if the stack container is empty or not. If the stack is **empty** it returns **TRUE**. Otherwise, if the container has **at least one element** it returns **FALSE**. Let's see the example:
```cpp
    stack < int > MyStack;
    MyStack.push(5);                //pushing an element in the stack
    if(MyStack.empty() != 1)
        cout << "EMPTY\n";          //if empty() funtion returns false it'll print "EMPTY"
    else
        cout << "FILLED\d"          //if empty() funtion returns true it'll print "FILLED"
```
`OUTPUT : FILLED`

In this code we gave a input in MyStack, so the empty() function returned 1. As a result we got "FILLED" as an output.

Let's see another code:
```cpp
    stack < int > MyStack;
    MyStack.push(5);
    MyStack.push(15);
    MyStack.push(63);
                                        //the stack is {5, 15, 63} now
    while(MyStack.empty() != 1){        //the loop runs untill empty() function returns 1
        cout << MyStack.top() <<" ";    //prints the last element of the stack
        MyStack.pop();                  //decreasing the size of the stack by removing the last element
    }
```
`OUTPUT : 5     15    63`

In this code we have firstly inputed 5, 15, 63. Then we have run a while loop. If empty() function returns 0, the loop will break. In the loop we have printed the top element everytime and also removed it from the stack. As a result the loop will run for 3 times. On the third time the last element 5 will be removed ans our stack will become empty. We know that when a stack becomes empty the empty() function will return FALSE. So the loop breaks.

Let's see all the functions used in stack at a glance:

|function         |description|
|:--              |:--        |
|push             |Insert element|
|pop              |Remove top element|
|top              |Access next element|
|empty            |Test whether container is empty|
|size             |Access next element|
|swap             |Swap contents|


Time complexity of all above functions is O(1).

So these were the basic concepts of stack. We must need to solve stack related problems. **Some problem links are given below:**

- [*UVA 514*](https://onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&category=24&page=show_problem&problem=455)
- [*UVA 1062*](https://onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&category=24&page=show_problem&problem=3503)
- [*Codeforces 5C*](https://codeforces.com/contest/5/status)

Happy coding<3
