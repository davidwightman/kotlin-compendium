## Standard Functions

- also called scope functions
- execute code in the context of an object
- creates a temporary scope while the code is executed
- in the scope you can access the original object
```
Person("Alice",20,"Amsterdam").let{
    println(it)
    it.moveTo("London")
}
```
- if object is null then block of code is not executed
- you can access the object on which we apply the function through the keyword it

There are 5 scope functions, and 2 additional check functions
- let
- with
- run
- apply
- also
- takelf and takeUnless

### Let
- allows us to run code on an object or on the result on a function on a chain of calls (like filter)
- we can access the result as a lambda argument it by default
```
val animals = listOf("cat", "dog", "mouse", "bear", "zebra")
animals.map { it.length }
    .filter { it > 3 }
    .let {
        print(it)
        println("size of list is ${it.size}")
    }
```
- if the block of code contains a single function call, we can use the method reference::
```
animals.map{it.length}
    .filter{it>3}
    .let(::println)
``` 
- a common use case is to use let to filter for non-null variables
```
val name = readLine()
name?.let{
    println(name)
}
```

### with Function
- perform a block of code on an object
- the context is available as 'this' (the 'this' keyword can be ommitted)
- can access object variables and methods
- typical use case: perform some initialization on an object, perform a sequence of actions on an object
```
fun main(args: Array<String>){
    with(Car()) {
        speed = 80
        drive()
        println("Car is driving")
    }
}

class Car {
    var speed = 50
    fun drive(){
        println("Driving at $speed")
    }
}
```
- like let but in with you pass the object into the with context and you use the object to call methods or set variables

### run function
- same as with but invokes as an extension function
- useful when you need a lambda that returns a result
- can be used to limit the scope of variables
- two ways to use the function
```
Car().run {
    speed = 80
    drive()
    println("Car is driving")
    this
}

// in this case car is only available in this scope 
run {
    val car = Car()
    car.speed = 80
    car.drive()
    println("Car is driving")
}
```

### apply function
- can be used to apply some functionality and return a result
- returns the initial object
- common use case in applying configuration to an object creation
```
val myCar = Car().apply {
    speed = 80
    color = "red"
    startCar()
}
println(myCar::class.java)
```

### also function
- used for performing some additional actions on an object
- commmon use case is adding some actions that don't affect the object such as logging or debugging information
- removing an also block should not affect the execution of a program
```
Car().apply{
    speed = 80
    run()
    println("car is running")
}
.also {
    println("the car has been started $speed")
}
```

### takeIf and takeUnless

#### takeIf
- returns the object if the predicate values to true
- otherwise returns null
```
val number - Random.nextInt(100)
val evenOrNull = number.takeIf{it % 2 == 0}
```

#### takeUnless
- returns the object if the predicate values to false
- otherwise returns null
```
val number - Random.nextInt(100)
val evenOrNull = number.takeUnless{it % 2 == 0}
```