# type_to_string
Takes a C++ type and outputs a string describing its type in English

The main function is _describe_, taking a single type as a template parameter,
and it returns a std::string describing it:

Example:

```cpp
#include "describe.hpp"

struct X {
    using T = int *((*)[10]);
    T f(T, const unsigned long long * volatile * );
};

int main() {
    std::cout << describe<decltype(&X::f)>() << '\n';
}
```

Output is:

```
pointer to member function of class 1X taking (pointer to array[10] of pointer
to int, pointer to volatile pointer to const unsigned long long), and returning
pointer to array[10] of pointer to int
```
(newlines added)

NOTE: it is also useful to include this directly via url on Compiler Explorer:

`#include "https://raw.githubusercontent.com/cuzdav/type_to_string/main/describe.hpp"`
