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



