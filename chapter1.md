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

methods:

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

* 
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

```



