## Functions
- a way to group code to be executed
- main is entry function 
- can accept input and return output
```
fun doSomething(){
    // do something
}
```

### Paramaters
- a function can accept parameters
```
fun double(number: Int) {
    println("Double is ${number *2}")
}
```
- parameters can have default values
```
fun double(number: Int, message: String = "Double is") {
    println("$message $number")
}

double(5, "5*5=")
double(5)
```

### Returns
- a function can return a result
- must declare type of return
```
fun calculateCircleArea(radius: Int): Double{
    val pi = 3.1415
    return pi * radius * radius
}
```
- return shorthand
```
fun caculateCirclArea(radius: Int) = 3.1415 * radius * radius
```

### Function overloading
- two functions can have the same name if they have different numbers or types of parameters
```
fun multiply(number: Int) = number * 2
fun multiply(number: Int, multiplier: Int) = number * multiplier

multiply(3)
multiply(3, 5)


fun feedAnimal(animal: String) {
    println("Feeding the $animal")
}

fun feedAnimal(animals: Collection<String>){
    for (animal in animals) {
        feedAnimal(animal)
    }
}

feedAnimal("cat")
feedAnimal(setOf("dog", "bear", "cat"))
```

### Scope
- a variable defined inside a function only exists in that function

### Varag
- variable number of parameters (arguments)
```
fun sayHello(vararg names:String){
    for (name in names){
        println("Hello $name")
    }
}
sayHello("Mary", "John", "Alex")
```

### Local Functions
- a local function is function inside a function
```
fun listAnimals(){
    fun listOneAnimal(animal: String) {
        println("I have a $animal)
    }
    var myAnimals = arrayListOf("cat", "dog", "horse")
    for(animal in myAnimals){
        listOneAnimal(animal)
    }
}
```