# Map in C++

## Introduction

Map is one of the most powerful tools in STL. There are countless uses of maps and all of them are very useful. According to [cplusplus.com](http://www.cplusplus.com/reference/map/map/), Maps are associative containers that store elements formed by a combination of a key value and a mapped value, following a specific order. There are many things common between Set and Map. Infact some argues that **Map** is nothing but a 2D **Set**. So, without further due, lets jump into it!

## Declaration
For using map you need to add the following header file:
```cpp 
#include <map>
```
And the general structure of map is:
```
map <key_value, mapped_value> M;
```
So, in a map, There are some elements which has a key value and a mapped value. ```No two mapped values can have same key values. key values are unique & and Key values are also sorted like set. but mapped values can be duplicate.``` For example lets declare a map of 'string as key' and 'integers as mapped value':
```cpp
map <string, int> M;
```
## Basic Operations

Map is in a way vector of pairs where first element is a key value, which has to be unique(different for multimap we'll come to that later) and second element is mapped value. Now to be clear let's write a code:
```cpp
#include <map>
int main()
{
    map <string, int> M;
    M["Shanto"] = 29;
    M["Mehraj"] = 42;
    M["Mugdha"] = 1;
    cout << M["shanto"] << endl;
}
```
```
output: 29 
```
There are several ways to initialize a map, we could also use:
```cpp
M.insert(make_pair("Shanto", 29));
```
Now if we want to print the whole map we can do it by iterators:
```cpp
for(auto it = M.begin(); it != M.end(); it++){
    cout << it->first << ' ' << it -> second << endl;
}
```
```
output: 
Mehraj 42
Mugdha 1
Shanto 29
```
Now if we analyze the output we would notice that `our map is not printed in the input order rather it was printed in lexicographical order of key values`. Here, *Mehraj* is lexicographically less then *Mugdha*. That's why *Mehraj* was printed first.
|Key Value| mapped value|
|----------|------------|
|Mehraj|42|
|Mugdha|1|
|Shanto|29|

Now what will happen if we add same key value? Lets code:


