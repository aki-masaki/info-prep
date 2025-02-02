## Undirected graphs
An _undirected graph_ is a pair of sets $(V, E)$, where $V$ is the set of all the _nodes_, and $E$ is the set of all the _edges_ (pairs of nodes from $V$).
![[Undirected Graph.svg]]
In the example above,
$G=(V, E)$
$V=\{1, 2, 3, 4, 5\}$
$E=\{(1, 2), (1, 3), (1, 4), (2, 3)\}$

**Degree** (ordin) of a graph represents the number of nodes.

Let $e=(u, v), e \in E, u, v \in V$
$u, v$ are called $e$'s _endpoints_
$u, v$ are _adjacent_ to each other
$e$ is _incident_ on $u$ and $v$

Tow _edges_ are called incident if they **share** an _endpoint_.

**Degree** of a node is the number of edges that are _incident_ to it, noted by $d(x)$.

**Neighbor** of a node is a node which is adjacent to it.

A **terminal** node is a node whose _degree_ is equal to $1$.
An **isolated** node is a node whose _degree_ is equal to $0$.

- The total number of _undirected graphs_ with $n$ nodes is $2^{C_n^2}$
- Let $n=|V|$ and $m=|E|$
$$
\sum_{i=1}^{x} d(x_i)=2m
$$
- A _graph_ with $n$ nodes has _at least_ $2$ nodes with the same _degree_
- For every graph, the number of nodes with an _odd_ degree is _even_
- The _minimum_ number of edges a graph needs to have so **no** _isolated_ nodes exist is $[\frac{n+1}{2}]$

## Directed graphs

A _directed graph_ is a graph whose _edges_ have **orientation**.

![[Directed Graph.svg]]

$G=(V, E)$
$V=\{1, 2, 3, 4\}$
$E=\{(1, 2), (2, 4), (4, 3), (3, 2)\}$

**Notice**: in a _directed graph_, the order of the edges **matter**, $(1, 2)$ is **NOT** the same as $(2, 1)$, as _opposed_ to _undirected graphs_.

Let $u=(x, y)$
$x$ is called the _tail_
$y$ is called the _head_

**Successor** of $x$ is a node that's the _head_ of the edge in which $x$ is the _tail_.
The set of all _successors_ of $x$ is denoted by $\Gamma^+(x)$
The set of all _edges_ of whose _tail_ is $x$ is denoted by $\omega^+(x)$

**Predecessor** of $x$ is a node that's the _tail_ of the edge in which $x$ is the _head_.
The set of all _predecessors_ of $x$ is denoted by $\Gamma^-(x)$
The set of all _edges_ of whose _head_ is $x$ is denoted by $\omega^-(x)$

$\Gamma^+(x)=V-\{x\}$ **and** $\Gamma^-(x)=\emptyset$ - **root** node
$\Gamma^-(x)=V-\{x\}$ **and** $\Gamma^+(x)=\emptyset$ - **destination** node

The _internal_ degree of a node $x$ is the number of _edges_ where $x$ is the _head_, and is denoted by $d^-(x)$
The _external_ degree of a node $x$ is the number of _edges_ where $x$ is the _tail_, and is denoted by $d^+(x)$

$d^-(x)+d^+(x)=1$ means $x$ is _terminal_
$d^-(x)+d^+(x)=0$ means $x$ is _isolated_

## Implementation
**TODO**