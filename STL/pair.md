# Let's Make some Pairs!

##  __introduction__
std::pair is an another container which contains two data elements or objects. It can contain two same type of objects (i.e int, int) or different type of objects (i.e string, int). Pair provides a way to store two heterogeneous objects as a single unit. Pairs are widely used in STL. So, lets jump into it right now!

## Header File
we use `#include <utility>` for using pairs and related functions.
## Syntax and declaration
genaral syntax is : `pair <datatype1, datatype2> pair name` 
Now lets declare the simplest form, pair of 2 integers:
<br>
<br>
`pair < int, int > p;`
<br>
<br>
now this single unit **p** denotes a pair of two integers. **p** has 2 forms: **p.first** and **p.second** which consecutively means the first and the second element of pair **p**. In this case both are integers. 
We could also use `pair <int, string> p` , `pair <char, string> p`, `pair <int,  vector <int> > p` and so on.
## Taking input and output
Enough of talking now it's time to code! Let's jump into it:
```cpp
#include <iostream>
#include <utility>
using namespace std;
int main()
{
    pair <int, int> p;
    p.first = 23;
    p.second = 12;
    cout << p.first << ' ' << p.second << endl;
    return 0;
}
```
We could also take input from user:
```cpp
cin >> p.first >> p.second;
```
There is another way to take input of pair let's see this:
```cpp
p.make_pair(x, y);
```
In this case **x** and **y** are any two variable.

## Use of pairs

There are many usage of pair. For instance, using vector of pairs can be very convenient sometime. To understand this, lets consider a scenario:

`You have to take input n people's names and their IDs. Then you have to store all the data in a vector of pairs. Then print it in reverse order.`
```
input:
3
Shawon 1013
Mehraj 1074
Shanto 1029
output:
Shanto 1029
Mehraj 1074
Shawon 1013
```
**You must Try to code this by yourself first and then proceed to the next portion!**
<br>
Now lets see how we can code with the help of pairs!
```cpp
#include <iostream>
#include <utility>
#include <vector>
using namespace std;

int main()
{
    int n;
    cin >> n;
    vector < pair <string, int > > vp(n);
    
    for(int i = 0; i < n; i++){
        cin >> vp[i].first >> vp[i].second;  
    }
    
    for(int i = n-1; i >= 0; i--){
        cout << vp[i].first << ' ' << vp[i].second << endl;
    }
    return 0;
}
```
**We could also sort the vectors of pairs in the increasing order of id or or name by using customized sort functions, which will be shown in the sorting part of STL**

Now that you can make pairs so start solving some problems using pairs!


