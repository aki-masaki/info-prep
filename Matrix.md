A **matrix** is a two-dimensional array, or an array _of arrays_ where array at each index has the _same size_.

A matrix $A$ with $n$ rows and $m$ columns
$$
A_{n\times m} =

{\begin{bmatrix}

a_{11} & a_{12} & \cdots & a_{1m}\\

a_{21} & a_{22} & \cdots & a_{2m}\\

\vdots & \vdots & \ddots & \vdots\\

a_{n1} & a_{n2} & \cdots & a_{nm}\\

\end{bmatrix} }
$$

### Declaration

**Notice**: The _max_ number of rows and columns must be specified at compile-time and be constant, which means most of the time some _memory gets wasted_.

```c++
TYPE NAME[MAX_ROWS][MAX_COLUMNS]
```

Example
```c++
int matrix[10][10]
```

### Operations

**Accessing**, where $i$ denotes the _row_ and $j$ denotes the _column_ 
```c++
matrix[i][j]
```

**Traversing** it's done using _two_ loops, where $n$ denotes the number of _rows_ and $m$ denotes the number of _columns_
```c++
for (int i = 0; i < n; i++) {
  for (int j = 0; j < m; j++) {
    std::cout << matrix[i][j];
  }
}
```

**Transposing** it's done by _replacing_ `mat[i][j]` with `mat[j][i]`


### Initialization

```c++
int mat[2][3] = {
  {1, 2, 3},
  {4, 5, 6}
};
```

**Notice**: When initializing, `MAX_ROWS` can be omitted
```c++
int mat[][3] = {
  {1, 2, 3},
  {4, 5, 6}
};
```

If, when initializing, some arrays are _smaller_ than `MAX_ROWS` then the **rest of the array is left uninitialized**.

```c++
int mat[][3] = {
  {1, 2},
  {4, 5, 6}
}
```

The resulting matrix would be
$$
{\begin{bmatrix}

1 & 2 & \_\\

4 & 5 & 6\\
\end{bmatrix} }
$$
If the matrix is `global`, then `mat[0][2]` would be equal to $0$, otherwise `undefined`.

