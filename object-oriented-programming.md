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
- the "this" keyword refers to parameters of the class
```
class PostItNote(){
    var message: String = "No message"

    fun updateMessage(message: String) {
        this.message = message
    }
}

val postIt = PostItNote()
println(postIt.messge)
postIt.updateMessage("Meeting at 5")
println(postIt.message)
```

### the init block
- the "init" block is run before any other code in the class
```
class Car {
    var model: String? = "no model"
    var topSpeed = 100

    init {
        println("Model $model top speed $topSpeed")
    }
}
```

### the companion object
- static code
- makes class code available without the need for an object
```
class Car{
    companion object{
        fun getDrivingInstructions(): String {
            return "Drive safe"
        }
    }
}
println(Car.getDrivingInstrictions())
```

### The four principles of OOP
- a set of guidelines that make a language object-oriented
- help developers write clean, maintainable code
- help guide how a program is divided into components

### Inheritance
- Classes can inherit methods and parameters from other classes
- same functionality but in one place
- to make a class inheritable, use the open keyword
```
open class Mom(nativeTongue: String) {
    open val hairColor = "brown"
    val eyeColor = "blue"

    open fun say(message: String) {
        println("mom says $message")
    }
}

class Daughter(nativeTongue: String): Mom(nativeTongue){
    override val hairColor = "blonde"
    override fun say(message: String){ 
        println("daughter says $message")
    }
}

val carol = Daughter("french")
println(carol.hairColor) // blonde
carol.say("Hi") // daughter says Hi
```
- if the class has multiple constructors, at least one must be initialized
- "Daughter" classes can override methods in "mother" classes using the override keyword if they are marked as open
- "Daughter" classes can access "mother" class methods and variables using the super keyword


### Encapsulation
- hiding data and inner workings of a class from other classes that don't need to know how something is done
- variables and functions are available only in the block of code they are declared in
- Classes can change the scope of their variables / functions
- Modifiers
```
-- private - visible inside the class only
-- protected - visible inside class and inheriting classes
-- internal - visible inside the package
-- public - visible to anyone accessing the class
```
- the default is set to public

### Abstraction
- a common feature of 2 classes should be abstracted in a third class
- a functionality that is not associated with an instance (object) should be abstracted away
- if 2 classes share common  features, create a super class that contains the common features and inherit from it

### Polymorphism
- same name many forms