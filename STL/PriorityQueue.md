# Priority Queue
## Introduction
Priority queue is a special variant of the queue which works like a **heap data structure**. This is very important sometimes in some situation to use this heap. As it uses heap it can store data in increasing or decreasing order.  This can pull out maximum or minimum element of a list in _**`logN`**_ time where **N** is the size of the list. So You can get all the elements of the array in _**`NlogN`**_ time.

> [**To know about HEAP click here**](https://en.wikipedia.org/wiki/Heap_(data_structure))

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
