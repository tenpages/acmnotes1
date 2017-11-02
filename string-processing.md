### special characters

`NULL` means `0` or `'\000'`

`EOF == -1`

### char\* and string

```cpp
char *sch = str.c_str(); // string -> char*
```

### tokenizer

```
#include<cstring>

strtok( str, delimiter ) // str = target string for the first time, NULL for the rest
                         // delimiter : a string contains all possible delimiters
                         // returns current next token from target string
                         // or return the rest of target itself if there's no token left
                         // or return NULL if it comes to the end of the target string
```



