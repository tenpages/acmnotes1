### array

watch out when calling `a[k-1]` for `k-1` might go minus

### scanf/printf

use `%i64d` for long long integers

### typedef for stl contianers

for reducing typing. and assigning value to vars becomes more covenient.

```cpp
typedef vector<int> i;
typedef vector<i> ii;
typedef pair<int, double> pp;

pp a=pp(10,1.0);
```

### cmath

#### rounding

| function | usage | note |
| :--- | :--- | :--- |
| `ceil( num )` | round up |  |
| `floor( num )` | round down |  |
| `round( num )` | round to the nearest, .5 to 1.0 | only supported by C++11 and later |
| `trunc( num )` | round toward zero | only supported by C++11 and later |

#### mod

cannot use `%` with floating numbers. use `fmod( num, denominator )` instead

### iomanip

`std::fixed` output numbers with floating-point notation  
`std::scientific` output numbers with scientific notation

#### iomanip

include: `iomanip.h`

`std::setprecision( num )` set decimal precision



