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
