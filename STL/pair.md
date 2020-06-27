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
Now, lets see some ways to take input of pairs:
