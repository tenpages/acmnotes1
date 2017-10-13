# STL

## Vector

include:

```cpp
#include<vector>
```

define:

```cpp
vector< type > name[(size[, init-value])];
```

member functions:

* check empty: 

```cpp
v.empty()
```

* check size: 

```cpp
v.size() //don't use this for empty checking like ".size()==0"
```

* add one ele x to the end: 

```cpp
v.push_back(x)
```

* change size: 

```cpp
v.resize(k) //new eles filled with zeros
```

* clear \(resize to 0\): 

```cpp
v.clear()
```

* insert:

```cpp
v.insert( iterator, value ) // insert the value at iterator
v.insert( iterator, range_begin_pointer, range_end_pointer ) // insert a part of a vector at iterator

vector<int> v;  v={1,2,3};
vector<int> v2;  v2={4,5,6};
vector<int>::iterator it = v.begin();
v.insert(it+1, 42);  // v=[1,42,2,3]
it = v.begin();   // after insert/erase, old iterator no longer valid
v.insert(it, v2.begin(), v2.end()) // v=[4,5,6,1,42,2,3]
```

functions:

* erase:

```cpp
erase( iterator )
erase( begin_pointer, end_pointer )
```

initialization:

```cpp
vector<int> v2 = v1;
vector<int> v3(v1);  // v2 and v3 are the same
vector<int> v4(1000);  // with specific size
vector<int> v5(20, -1);  // with initial value -1
```

multidimensional:

```cpp
vector<vector<int> > matrix;
vector<vector<int> > matrix2(N, vector<int>(M, -1)) //with size NxM and init-value -1
```

## pairs

define:

```cpp
pair< type1, type2 > name;
```

extract:

```cpp
type1 a = p.first;
type2 b = p.second;
```

note:

pairs can be compaired first-to-second element directly using '&lt;', '==', and '&gt;' etc.

## iterators

define:

```cpp
vector<int>::iterator it1;
vector<int>::const_iterator it2;
vector<int>::reverse_iterator it3;
vector<int>::const_reverse_iterator it4;
```

most common iterators are `.begin()` and `.end()`.

function `reverse()` can reverse elements between two iterators \(or pointers\):

```cpp
int a[10]={1,2,3,4,5,6,7,8,9,10};
vector<int> v=a;
reverse(a+2, a+5);  // {3,4,5} -> {5,4,3}
reverse(v.begin(), v.end()); // totally reverse
```

reverse iterators `.rbegin()` and `.rend()` are used for tracking elements backward \(for which `++` means go backward and `--` means go forward\)

random iterators support the following operations: \(pointer-like\)

```cpp
int x = *it; // * for getting value
it++; it--;  // ++, -- for increment and decrement
cout << (it1 != it2) << (it1 < it2); // comparison between iterators
it += 20; // plus or minus some number meaning shift for/backward more than one position
it = it2 - it1; // getting
```

normal iterators only support some comparison methods and in/decrease. they don't support subtraction.

```cpp
int x = *it; // * for getting value
it++; it--;  // ++, -- for increment and decrement
cout << (it1 != it2) << (it1 == it2); // comparison between iterators (only == and !=)
```

functions:

* find\(\)

```cpp
find( begin_pointer, end_pointer, target_ele )
it = find(v.begin(), v.end(), 10) // returns the pointer of the result, if not found, return .end()
index = it - v.begin() // to get the index of the result
```

* max\_element\(\), min\_element\(\)

```cpp
max_element( begin_pointer, end_pointer ) // min_ is the same
it = max_element(v.begin(),v.end()) // returns pointer
n = *max_element(v.begin(),v.end()) // returns value
```

* sort\(\)

```cpp
sort( begin_pointer, end_pointer[, compare_function] )
sort(x.begin(), x.end()) // sort in ascending order
sort(x.rbegin(), x.rend()) // sort in descending order
```



