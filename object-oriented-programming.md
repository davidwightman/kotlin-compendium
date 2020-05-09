## Object Oriented Programming

- Object Oriented Programming
- entities in a program that perform certain tasks
- tasks are completely contained in the object (encapsulation)
- the entities can be replaced with similar entities that perform the sam task in a different way

### Classes
- a class is a blueprint for components (objects)
- a class has
-- variables
-- methods (functions)
```
class Car {
    var model: String? = null
    var topSpeed = 100

    fun start() {
        println("starting car now")
    }

    fun drive(speed: Int) {
        println("driving at $speed")
    }
}
```
- name should start with capital letter
- Class creates a type (example: Car)

### Objects
- an instance of a class
```
val myCar = Car()
val yourCar = Car()
```
- an object can change its values without impacting other objects from the same class
```
myCar.model = "BMW"
yourCar.model = "Toyota"
```
- an object can call its methods
```
yourCar.start()
yourCar.drive(75)
```

### The "Object" Construct
- when a class is instantiated the instance is called an object
- an object construct is a static class. all methods and variables can be accesed without an instance
- this is a Singleton - one instance of a class
```
object DatabaseAccess {
    var connected = false
    fun connect(){
        connected = true
        println("connected to database")
    }
    fun disconnect(){
        connected = false
        println("Disconnected from database")
    }
}
```

### Creating classes and objects
- in kotlin, almost everything is an Object
- The following types are all Objects: String, Int, Float, Boolean, ArrayList, HashMap
- Collection, List are interfaces (a type of object)
- Object definitions (classes) can contain references to other objects
```
val myGarage = Garage()
myGarage.car.drive()

class Car {
    fun drive () {
        println("drive")
    }
}

class Garage {
    val car = MyCar()
}
```

### Inheritance
- apply the variable and methods of a class to another class
- a class from another class
```
open class Dog {
    var size: Int = 0
    
    fun bark(){
        println("Bark")
    }

    fun play(){
        println("Playing")
    }
}

// Corgi inherits all variables and methods from dog
class Corgi: Dog(){

}

val myDog = Corgi()
println(myDog.size)
myDog.bark()
myDog.play()
```
- inheritance is transitive
- Corgi class has access to the methods and variables in Dog and Animal

### Constructors
- defines a set of variables that are available at the creation of an object
```
class Car(var model: String, var topSpeed: Int) {
    // other parameters and methods
}
val myCar = Car("BMW", 220)
```
- a class can have multiple ways of being created
- which constructor is used depends on the parameters
```
class Car{
    // three different ways:
    constructor(){
        model = "No model"
        topSpeed = 150
    }

    constructor(newModel: String) {
        model = newModel
        topspeed = 150
    }

    constructor(newModel: String, newSpeed: Int){
        model = newModel
        topSpeed = newSpeed
    }

    var model: String? = null
    var topSpeed = 100
}

val myCar = Car()
val yourCar = Car("BMW")
val hisCar = Car("Fiat", 200)
```
- if there is only one constructor, just put it in parenthesis after the class name
```
class Car(var newModel: String, var newSpeed: Int) {
    // other parameters and methods
}
```

### Getters and Setters
- allow us to change the way variables are assigned and retrieved
```
var customInfo: Int
    get() = // do something
    set(value) {
        // do something
    }
```
- custom getter will be called every time we acces the variable
- same for setter
```
fun main(args: Array<String>){
    val myCar = Car()
    myCar.speed = 100
    println(myCar.name)
    println(myCar.speed)
}

class Car {
    var name = ""
    var speed: Int = 0
        get() = field
        set(value) {
            name = "high speed car $value"
            field = value
        }
}
```

### The this keyword

### the init block

### the companion object