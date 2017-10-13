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

```
set_union(), set_intersection(), set_difference() and set_symmetric_difference()

it = set_union(begin1, end1, begin2, end2, begin_result);
// remind: the size of result must be enough
result.resize( it - v.begin );
```



