# Priority Queue
## Introduction
Priority queue is a special variant of the queue which works like a **heap data structure**. This is very important sometimes in some situation to use this heap. As it uses heap it can store data in increasing or decreasing order.  This can pull out maximum or minimum element of a list in _**`logN`**_ time where **N** is the size of the list. So You can get all the elements of the array in _**`NlogN`**_ time.

> [_**To know about HEAP click here**_](https://en.wikipedia.org/wiki/Heap_(data_structure))

## Header File
To use priority queue you need to first add its header by typing the following :
```cpp
 #include <queue> 
```
By default priority queue stores data in **decreasing order** which allows you to _pop the maximum value_ of the list in each operation of _**logN**_ time. 

## Declaration
You can declare a priority queue using following code :
```cpp
priority_queue < data_type > MyPriorityQueue;
```
This creates a priority queue nammed MyPriorityQueue of a cerrain data type.

## Operations
You can do the following operation in a priority queue :
- push
- pop
- top
***
+ _**PUSH :**_  This operation takes an input of certain data type and pushes it into your priority queue or heap. It works same as pushing something in a heap. It take logN time    to do this operation. Suppose you want to push 12,  18,  8 into your priority queue.  You can do that using the following code:
  ```cpp
  priority_queue < int > MyPQ;
  MyPQ.push(12);
  MyPQ.push(18);
  MyPQ.push(8);
  ```
  This code makes a priority queue of integers named MyPQ and pushes 12, 18 and 8 into that. Then it works like a heap and so you can pop out  the maximum number from the heap list in just logN time which means this 3 numbers will be stored in this sequence { 18, 12, 8 }.
+ _**POP :**_  You can retrieve the maximum number from the numbers you pushed earlier using this operation. You can see the following code to see the implementation of this operation :
  ```cpp
  priority_queue < int > MyPQ;
  MyPQ.push(12);
  MyPQ.push(18);
  MyPQ.push(8);
  // After Pushing the queue will be 18, 12, 8
  MyPQ.pop(); // popping 18
  MyPQ.pop(); // popping 12
  MyPQ.pop(); // popping 8
  // Now the queue will be empty
  ```
  This pop functionality works like popping from a heap. And after popping it automatically adjusts the queue in logN time.
+ _**TOP :**_ This function gives us the access to the topmost element of the priority queue. If the queue is in default mode it will return the maximum element and if it is declared as the smaller  version of the heap it will return the smallest number of the list. See the following code for better understanding :
  ```cpp
  priority_queue < int > MyPQ;
  MyPQ.push(12);
  MyPQ.push(18);
  MyPQ.push(8);
  cout << MyPQ.top() << endl;
  // prints 18 as it is the largest among the heap
  ```
***
## Printing a Priority Queue using a custom function : 
There are no library function to print a queue without popping. So, we will  write a custom function of oue own to print a priority queue. We will send a copy of our priority queue in order to print it. We can pop that copy because it will not change the main Priority_queue which is inside the main function. So, Lets see the code :
```cpp
#include <iostream> 
#include <queue> 
  
using namespace std; 

void print_priority_queue(priority_queue < int > temp) 
{ 
    cout << "Elements of the priority_queue are :: \n" ;
    while ( !temp.empty() ) 
    { 
        cout << temp.top() << " "; 
        temp.pop(); 
    } 
    cout << '\n'; 
} 

int main(){
   	priority_queue < int > MyPQ;
  	MyPQ.push(12);
    MyPQ.push(18);
  	MyPQ.push(8);
  	// After Pushing the queue will be 18, 12, 8
  	print_priority_queue(MyPQ);
  	// printing the priority queue using custom function
  	// Here we are sending a copy of the queue
  	MyPQ.pop(); // popping 18
  	MyPQ.pop(); // popping 12
  	MyPQ.pop(); // popping 8
  	// Now the queue will be empty
  return 0;
}
```
### OUTPUT :
```
Elements of the priority_queue are :: 
18 12 8 
```

## Set the Minimum Number as priority ( Minimum Number Heap ) 
Sometimes your priority can be to pop the smallest number first. Which means if you want to keep your data in ascending order you need to declare the priority queue using the following code :
```cpp
#include <iostream> 
#include <queue> 
  
using namespace std; 

// Function to print minimum heap priority queue
void print_spcl_priority_queue(priority_queue < int , vector < int > , greater < int > > temp) 
{ 
    cout << "Elements of the priority_queue are :: \n" ;
    while ( !temp.empty() ) 
    { 
        cout << temp.top() << " "; 
        temp.pop(); 
    } 
    cout << '\n'; 
} 

int main(){
  priority_queue < int , vector < int > , greater < int > > MySpclPQ; 
  MySpclPQ.push(12);
  MySpclPQ.push(18);
  MySpclPQ.push(8);
  // After Pushing the queue will be 8 , 12 , 18
  print_spcl_priority_queue(MySpclPQ);
  // printing the priority queue
  MySpclPQ.pop(); // popping 8
  MySpclPQ.pop(); // popping 12
  MySpclPQ.pop(); // popping 18
  // Now the queue will be empty
  return 0;
}
```
### OUTPUT :
```
Elements of the minimum_heap_priority_queue are :: 
8 12 18 
```
Here we changed the argument of the queue printing function to _**`priority_queue < int , vector < int > , greater < int > > temp`**_ To let the function know that it is a minimum heap.
