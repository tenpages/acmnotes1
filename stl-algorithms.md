include

```cpp
#include<algorithm>
```

## basics

```cpp
min(a,b);
max(a,b);   // returns minimum or maximum ele
swap(a,b);  // swaps

sort(begin, end);   // sort ascendingly
sort(begin, end, cmp);

find(begin, end, ele); // find in O(N) time

next_permutation(begin, end)
prev_permutation(begin, end) // find and change it to the alphabetically next or previous permutation of the interval
```

## copy

```cpp
copy( from_begin, from_end, to_begin )

v2.resize(v1.size()+v2.size());                  // make sure there's enough space
copy(v1.begin(), v1.end(), v2.end()-v1.size());  // copying v1 to after elements of v2
```

## set\_

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

```
accumulate( begin, end, start[, method]) // returns answer
```



