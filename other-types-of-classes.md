## Other Types of Classes

### Data Classes
- Commonly created classes just for storing data
- "Pojo" in Java
- primary constructor has at least one parameter
- all primary constructor parameters need to be val or var
- Can have a body but not required
```
data class User(
    val name: String,
    val email: String,
    val password: String
)

val user = User("John", "john@gmail.com", "JohnCool123")
```

#### Data Class Methods
- Automatically generated class methods
- Compares data not object references
```
.equals()
==

// a regular class (with no data prefix) will compare object references and produce false
val user1 = RegularUser("John")
val user2 = RegularUser("John")

println(user1 == user2) // false

// Data class allows us to compare data (inside the object) not object references
val user3 = User("John")
val user4 = User("John")

println(user3 == user4) // true

```
- prints out variable names and data, instead of object reference and id
```
.toString()

val user1 = RegularUser("John")
println(user1.toString()) // RegularUser@3cd1a2fq

val user3 = User("John")
println(user3.toString()) // User(name=John)
```
- creates a copy with only some data changed
```
.copy()

val user3 = User("John", "john@gmail.com")
val user4 = user3.copy(email="david@gmail.com")
println(user4.toString()) // User(name=John, email=david@gmail.com)
```

### Enum Classes

### Sealed Classes

### Nested Classes