A _list_ or _chain_ holds data of the _same type_ in a **sequential order**.

A _linear list_ is a finite sequence of `n` elements of the _same type_, named **nodes**.

In a list, the following nodes are _important_:
- the **first**
- the **last**
- a **successor** (_every_ node has a successor except the _last_ one)
- a **predecessor** (_every_ node has a predecessor except the _first_ one)
### Operations
#### Inserting
**Inserting** (adding) a element at a _specific_ index means moving the _right_ elements of `index`, **one to the right**.

Example
$L=\{1, 2, 4, 5\}$

If we want to _insert_ $3$ _after_ $2$ (index 1) but _before_ $4$ (index 2), we have to move $4$ to index _3_ and move $5$ to index _4_, to make room so $3$ can be inserted at index _2_.

Result
$R=\{1, 2, 3, 4, 5\}$

**Moving** the elements is done using a `for` loop, starting from the _last_ index **minus one**, until the _new_ index (**including**), **decreasing** `i` each time.

Suppose we want to _move_ $4$ and $5$ in $L$ _above_ one to the right.
```c++
// Last index is 4 but 4 - 1 = 3
for (int i = 3; i >= 2; i--)
	L[i + 1] = L[i];
```

Step by step
$i=3$
  `L[3 + 1] = L[3]`
  $\{1, 2, 4, 5, \_\} \rightarrow \{1, 2, 4, 5, 5\}$
  
$i = 2$
  `L[2 + 1] = L[2]`
  $\{1, 2, 4, 5, 5\} \rightarrow \{1, 2, 4, 4, 5\}$

And now, the element at index _2_ can be replaced with $3$ because the rest of the elements have been _moved_.

`L[2] = 3` resulting in $\{1, 2, 3, 4, 5\}$.
#### Deleting
**Deleting** (removing) a element at a _specific_ index means moving the _right_ elements of `index`, **one to the left**.

Example
$L=\{1, 2, 3, 7, 4, 5\}$

If we want to _delete_ $7$ (index _3_), we have to move $4$ to index _3_ and move $5$ to index _4_, to fill up the space $7$ left behind.

Result
$R=\{1, 2, 3, 4, 5\}$

**Moving** the elements is done using a `for` loop, starting from the deleting item's _index_, until the _last_ index **minus one** (**including**), **increasing** `i` each time.

Suppose we want to _move_ $4$ and $5$ in $L$ _above_ one to the left.
```c++
// Last index is 5 but 5 - 1 = 4
for (int i = 3; i <= 4; i++)
	L[i] = L[i + 1];
```

Step by step
$i=3$
  `L[3] = L[3 + 1]`
  $\{1, 2, 3, 7, 4, 5\} \rightarrow \{1, 2, 3, 4, 4, 5\}$
  
$i = 4$
  `L[4] = L[4 + 1]`
  $\{1, 2, 3, 4, 4, 5\} \rightarrow \{1, 2, 3, 4, 5, 5\}$

And now, the list's _length_ can be _decremented_ since there's an element missing.

Result
$\{1, 2, 3, 4, 5\}$
### Special lists

By _special_ we mean a **list** which has restrictions on its _operations_.

Their implementation is _no different_ than that of an array.
```c++
TYPE VAR[SIZE];
```

#### Stack
A _stack_ is a _linear list_ whose _inserting_ and _deleting_ operations target one end of the list, called its _head_ (vârf).

We can think of stack as a pile of _plates_, you can't take the bottom one unless u take every plate at the top and _remove_ it first, and u cant _add_ a new plate at the bottom.

![[Stack.svg]]

A stack's operations are:
- **push**, insert an element at the _top_ of the stack
- **pop**, remove an element from the _top_ of the stack

#### Queue
A _queue_ is a _linear list_ whose _inserting_ operation target one end of the list (the _back_), while the _deleting_ operation target the _other end_ (the _front_).

![[Queue.svg]]