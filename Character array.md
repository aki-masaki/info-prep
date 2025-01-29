A **character array** is an array of `char` type whose _last element_ is the _null terminator_, `'\0'` 

### Declaration

```c++
char NAME[MAX_SIZE];
```

### Operations

**Accessing** a specific `char` by index can be done by `arr[index]`

**Pointer arithmetic** can be used to _start_ the `array` from a specific _byte_, `arr + index`

Example
```c++
char arr[] = "albas";

std::cout << arr + 0; // Prints albas
std::cout << arr + 1; // Prints lbas
std::cout << arr + 3; // Prints as
```

### Initialization

**Notice**: the _first one_ is legal, but incorrect. There's not enough memory for the _null terminator_, which will give problems later on.

If you omit the _null terminator_, the compiler automatically adds it, but you need to make sure you have enough memory for it.

If you omit the `MAX_SIZE`, the compiler assigns it to `LENGTH + 1` to make room for `'\0'`

```c++
char array[3] = {'a', 'b', 'c'};       // incorrect
char array[4] = {'a', 'b', 'c', '\0'}; // correct
char array[] = {'a', 'b', 'c'};        // correct
char array[] = "abc";                  // correct
char array[4] = "abc\0";               // correct
char array[3] = "abc";                 // incorrect
```

### Reading

`std::cin.get(ARRAY, COUNT, STOP_CHAR = '\n')`

Read into `ARRAY`, `COUNT - 1` characters _unless_ the `STOP_CHAR` was met.

**Notice**: `STOP_CHAR` will not be included in `ARRAY`

Example
```c++
// Create a char array of max size 10
char a[10];
char b[10];

// Read maximum 4 (5 - 1) characters into a
std::cin.get(a, 5);

// Read maximum 2 (3 - 1) characters into b, stopping at '0' if met
std::cin.get(b, 3, '0');

std::cout << a;
std::cout << b;
```

### Standard functions

The standard functions for manipulating char arrays are under the _header_ `string.h`

```c++
#include <string.h>
```

- `strlen(arr)`, returns the _length_ of the array, **without** the _null terminator_
#### Copying
- `strcpy(dest, src)`, copies `src` into `dest` **including** the _null terminator_, returns a pointer to `dest`
- `stpcpy(dest, src)` does the same as `strcpy` but returns a pointer to the _end_ of `dest`
- `strncpy(dest, src, count)` copies _maximum_ `count` characters from `src` to `dest`

**Notice**: The length of `dest` must be _greater than or equal to_ the length of `src`
#### Concatenation
- `strcat(dest, src)` adds `src` to `dest` 