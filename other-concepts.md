## Other Concepts

### Type casting - is, as

#### is
- checks whether an object is of a certain type
```
if (value is String){
    println("${value.length} characters")
}
```
- the opposite operator is !is
```
open class Car {}
class BMW: Car(){}

val myCar: Car = getCar()

if(myCar !is BMW)
  println("This is not my favorite brand")
```

#### as
- converts an object into a different type
```
open class Car{}
class BMW: Car {
    fun drive(){
        println("Driving my BMW")
    }
}

val myCar: Car = getCar()

if (myCar is BMW)
    (myCar as BMW).drive()
```

#### as?
- Null safe operator as?
```
val bmwCar = myCar as? BMW
bmwCar?.drive()
```

### lateinit
- allow us to create non null, non initialized variables
- need to initialize the variable before using it
- accessing it before initializing it throws an exception
- can be used only on var variables
- Use .isInitialized to check initialization
```
lateinit var networkService: String
networkService = getNetworkService()
println(networkService)

fun getNetworkService() = "Network service"
```
- Common use cases: dependency injection, unit testing

### lazy
- lazy variables are variables that are initialized when needed
- useful to save memory in case the variable is never accessed
```
val someLargeVariable: String by lazy {"a large value"}
val rand = Random.nextInt()
if(rand % 2 == 0){
    println(someLargeVariable)
}
```
