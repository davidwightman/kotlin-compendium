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


### Creating classes and objects

### Inheritance