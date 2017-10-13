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

```
v.empty()
```

* check size: 

```
v.size() //don't use this for empty checking like ".size()==0"
```

* add one ele x to the end: 

```
v.push_back(x)
```

* change size: 

```
v.resize(s) //new eles filled with zeros
```

* clear \(resize to 0\): 

```
v.clear()
```

* 
initialization:

```
vector<int> v2 = v1;
vector<int> v3(v1);  // v2 and v3 are the same
```













