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
v.resize(s) //new eles filled with zeros
```

* clear \(resize to 0\): 

```cpp
v.clear()
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



