include

```cpp
#include<algorithm>
```

## basics

```cpp
min(a,b);
max(a,b);   // returns minimum or maximum ele
swap(a,b);  // swaps

fill(begin, end, value);  //reinitialize

sort(begin, end);   // sort ascendingly
sort(begin, end, cmp());
// remind: cmp() should be based on '<' operator
// and always return 'false' for same (equal) stuffs

find(begin, end, ele); // find in O(N) time

next_permutation(begin, end)
prev_permutation(begin, end) // find and change it to the alphabetically next or previous permutation of the interval
```

* implement `<` for self-created structure:

```cpp
struct point {
    double x,y;
    //...
    bool operator < (const point& p) const {
        if(x < p.x - epsilon) return true; 
        if(x > p.x + epsilon) return false; 
        if(y < p.y - epsilon) return true; 
        if(y > p.y + epsilon) return false; 
        return false; 
    }
} // operator '<' is reloaded so that 'point's can be sorted firstly by x and secondly by y
```

## copy

```cpp
copy( from_begin, from_end, to_begin )

v2.resize(v1.size()+v2.size());                  // make sure there's enough space
copy(v1.begin(), v1.end(), v2.end()-v1.size());  // copying v1 to after elements of v2
```

## set operations

```cpp
set_union(), set_intersection(), set_difference() and set_symmetric_difference()

set_union(begin1, end1, begin2, end2, begin_result) // returns iterator point to the last ele in result
// remind: the size of result must be enough

vector<int> v1 = {1,2,3,4,5};
vector<int> v2 = {3,4,5,6,7};
vector<int> v3(v1.size()+v2.size());
vector<int>::iterator it;
it = set_union(v1.begin(),v1.end(),v2.begin(),v2.end(),v3.begin()); // v3={1,2,3,4,5,6,7,?,?,?}
v3.resize(it - v3.begin()); // v3={1,2,3,4,5,6,7}
```

## mathematics

* accumulate\(\):

```cpp
accumulate( begin, end, start[, method]) // returns answer
```

use a method function or operator that takes two input arguments and returns a number, e.g.

```cpp
int myMethod(int x, int y) {return x+2*y;}
```

or these

```cpp
 plus<type>(), minus<type>(), multiplies<type>(), divide<type>(), and modulus<type>()
```

* inner\_product\(\):

```cpp
inner_product( begin1, end1, begin2, shift)
```





