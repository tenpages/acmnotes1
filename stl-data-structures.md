# STL

## vector

include:

```cpp
#include<vector>
```

define:

```cpp
vector< type > name[(size[, init-value])];
```

initialization:

```cpp
vector<int> v1 = {1,2,3,4,5,6};
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
insert( iterator, value ) // insert the value at iterator
insert( iterator, range_begin_pointer, range_end_pointer ) // insert a part of a vector at iterator

vector<int> v;  v={1,2,3};
vector<int> v2;  v2={4,5,6};
vector<int>::iterator it = v.begin();
v.insert(it+1, 42);  // v=[1,42,2,3]
it = v.begin();   // after insert/erase, old iterator no longer valid
v.insert(it, v2.begin(), v2.end()) // v=[4,5,6,1,42,2,3]
```

* erase:

```cpp
erase( iterator )
erase( begin_pointer, end_pointer )

v.erase(it); // remove the ele at it
v.erase(v.begin(),v.begin()+2); // remove first 2 eles (not removing the third one, which is (v.begin()+2) pointing at)
```

* assign:

```cpp
assign( begin_pointer, end_pointer) // put something else into the vector

set<int> s;
v.assign(s.begin(),s.end())
```

* reserve:

```cpp
reserve( x ) // help keeping the vector not allocating too much memory (lesser than x till it actually reaches x)
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

* unique\(\)

```cpp
unique( begin_pointer, end_pointer, compare_fucntion )

bool cmp(int a, ant b){  //for comparing function
    return (a==b);
}
it = unique(v.begin(), v.end()) //returns the iterator pointing at the lasat element
```

note that you have to resize after using unique.

iterator functions:

```cpp
#include<iterator>
```

* begin\(\), end\(\):

```cpp
begin(v); // == v.begin()
end(v); // == v.end()
```

* inserter\(\), front\_inserter\(\), back\_inserter\(\):

```cpp
inserter( container, iterator_0 ) // create a iterator using insert() that always insert before the iterator_0
front_inserter( container ) // create a iterator using push_front() (if appliable)
back_inserter( container ) // create a iterator using push_back() (if appliable)
```

inserters can be used in `copy()`  as the third parameter.

## string

include

```cpp
#include<string>
```

define

```cpp
string name;
```

member functions:

basically the same as vectors

* length:

```cpp
s.length() // it's unsigned so don't do s.length()-1 arbitrarily just in case it is 0 already
```

* substring:

```cpp
substr( begin_index, end_index )

string s = "hello";
string s1=substr(0,3); //s1="hel"
```

* remove:

```cpp
erase( index, length )
erase( iterator )
erase( iterator_first, iterator_last )

str ("This is an example sentence.");
                                         // "This is an example sentence."
str.erase (10,8);                        //            ^^^^^^^^
                                         // "This is an sentence."
str.erase (str.begin()+9);               //           ^
                                         // "This is a sentence."
str.erase (str.begin()+5, str.end()-9);  //       ^^^^^
                                         // "This sentence."
```

* insert:

```cpp
.insert( pos, str )
```

* replace:

```cpp
.replace( starting_pos, replacing_length, new_str )
```



## set

include

```cpp
#include<set>
```

define

```cpp
set<int> s;
```

initialization

```cpp
set<int> s={1,2,3,4}

int data[5]={5,1,3,4,2}
vector<int> v1; v1={1,2,3,2,3,4}
set<int> s1(data, data+5); // s={1,2,3,4,5}
set<int> s2(v1.begin(), v1.end()); // s2={1,2,3,4}
vector<int> v2(s.begin(), s.end()); // v2={1,2,3,4} (sorted and distinct)
```

member functions:

* insert
* erase

```cpp
erase( x ) // remove some value from the set
erase( it1, it2 ) // remove all value between it1 and it2 (include *it1, not include *it2)
```

* size
* find  //different from the global function find\(\)

```cpp
s.find(x)  // return an iterator point to the result or end() if not found
```

* count //useless

```cpp
s.count(x) // return the number
```

use iterator \(in this case, normal iterator\) to traverse

## map

include

```cpp
#include<map>
```

define

```cpp
map< type1, type2 > m;  // type1 for keys, type2 for values
```

operator

* \[ \]

```cpp
m['abc'] // returns the value of m['abc'], or create a new item in m with key 'abc' if it does not exist
```

member functions:

* insert
* erase
* size
* find // **do not use **`[ ]`** **in if's, use find\(\) instead

## sstream

include

```cpp
#include<sstream>
```

define

```cpp
istringstream is(s);  // s is a string
// use 'is' in the same way as using 'cin'

ostringstream os;
// use 'os' in the same way as using 'cout'
s = os.str(); // s get the whole output stuff
```

### stack

```cpp
.empty()
.size()
.top()
.push( ele )
```

### queue

```cpp
.empty()
.size()
.front()
.back()
.push( ele )
.pop()
```

### dequeue/list

```cpp
//Capacity
.size()
.resize( new_size )
.empty()

//Elements
operator []
.at( pos )
.front()
.back()

//Modifiers
.push_back( ele )
.push_forward( ele )
.pop_back()
.pop_forward()
.insert()
.erase()
```

### priority queue

```cpp
.empty()
.size()
.top()
.push( ele )
.pop()
```

### multiset

set that allow multiple elements with same key

delete will remove all elements with same key

### bitset

```cpp
bitset< size > bitset_name;

.any() // return true if 1 exists
.none() // return true if no 1 exists
.count() // return # of 1's
.size() // return size
operator [] // access the bit
.set( ele ) // set bit to 1
.reset( ele ) // set bit to 0
.flip( ele ) // reverse the bit
.to_ulong() // return an unsigned long number
```



