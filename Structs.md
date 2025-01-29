A _struct_ (Romanian: **inregistrare**) is used to group variables into a _structure_. A variable in a _struct_ is called the _struct_'s **member**.

### Syntax

```c++
struct [NAME] {
	TYPE_A VAR_A;
} [VARS];
```

where,
- `NAME` (**optional**) treats the _struct_ as a **data type**,
- `VARS` (**optional**) is a list of variables to be created whose type is _struct_.

**Accessing** is done with a _dot_ `.`, e.g. `NAME.VAR`
### Example

Create a `User` struct consisting of `id` (**int**) and `age` (**int**) and a `Group` struct consisting of `userIds` (**int [2]**). Create two variables of type `User`, having `age` _21_, `id` _0_ and the other `age` _23_, `id` _1_. Print the oldest `user`.

```c++
// User struct
struct {
	int id;
	int age;
} user1, user2;

// Group struct
struct Group {
	int userIds[2];
};

// Create Group variable
Group group;

// Initialize user1
user1.id = 0;
user1.age = 21;

// Initialize user2
user2.id = 1;
user2.age = 23;

// Initialize group
group.userIds[0] = user1.id;
group.userIds[1] = user2.id;

// Print the oldest user
if (user1.age > user2.age)
	std::cout << user1.age;
else
	std::cout << user2.age;
```