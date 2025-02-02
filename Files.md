To use files in C++, you need to import the `fstream` **AND** `iostream` header
 
```c++
#include <fstream>
#include <iostream>
```

The `fstream` header includes _three_ classes:
- `ifstream` reads from files
- `ofstream` creates and writes to files
- `fstream`   combination of `ifstream` and `ofstream`

Declaration can be done like `ifstream file(FILE)` or `ifstream file` _then calling_ `file.open(FILE)`

Checking for _end of file (EOF)_ can be done with:
- `ifstream.eof()` which returns whether _EOF_ was reached
- `ifstream >> var` which returns the **opposite** of `ifstream.eof()`

After using a file, it's **good practice** to _close_ it to free up resources, using `file.close()`

## Example

The text file `input` has the _natural_ number `n` on the _first line_, and on the next `n` _lines_, a pair of two _natural_ numbers `a`, `b`. Write a program in c++ that reads the `input` file and writes to `output` file, on `n` _lines_, the **sum** of each pair.

Example `input`
```input
3
1 5
4 2
5 6
```

Code
```c++
std::ifstream fin("input");
std::ofstream fout("output");

int n, a, b;

// Read n (the number of pairs)
fin >> n;

// Iterate over all pairs
for (int i = 0; i < n; i++) {
  // Read a and b
  fin >> a; fin >> b;

  // Write their sum to output file
  fout >> a + b;
}
```

Expected `output`
```output
6 6 11
```