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
- stands for enumeration
- define a collection of constants
- the constants defined are objects
- the constants have properties
```
enum class Color(
    RED,
    GREEN,
    BLUE
)

fun decide(color: Color) {
    when(color){
        Color.RED -> { println("You chose red")}
        Color.GREEN -> { println("You chose green")}
        Color.BLUE -> { println("You chose blue")}
    }
}
```
- enum constants can be initialized
- constants have properties like name and ordinal
```
enum class Color(val timesUsed: Int){
    RED(34),
    GREEN(12),
    BLUE(64)
}

Color.GREEN.timesUsed // 12
Color.RED.name  // RED
Color.BLUE.ordinal //2
```

### Sealed Classes
- define a restricted hierarchy
- abstract by default so cannot be instantiated
- useful in when expressions
```
abstract class Plant
sealed class Fruit: Plant()
class Apple: Fruit()
sealed class Vegetable: Plant()
class Potato: Vegetable()
fun getPlant(): Plant = Apple()

val somePlant = getPlant()
when(somePlant){
    is Fruit -> println("Sweet")
    is Vegetable -> println("Tasty")
}
```

### Nested Classes
- a class created inside another class
- uses the inner keyword
- the inner class can access variable and methods of the outer class through the this keyword
- to access inner variables from the outer class, create an instance of the nested class
```
class Carr{
    val engine = Engine
    var speed = 100
    fun drive(){
        engine.run()
        println("Driving at $speed")
    }

    inner class Engine{
        val rpm = 300
        fun run(){
            this@Car.speed = 150
            this@Car.drive()
            println("Engine running")
        }
    }
}
```
