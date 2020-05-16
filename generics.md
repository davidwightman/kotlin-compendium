## Generics
- a class can have type parameters
- the type can be used by variables and methods
- useful when a class can handle multiple types of parameters
```
val animals: ArrayList<String> = arrayListOf("cat", "dog", "mouse")
```
```
class Box<T>{
    fun display(item: T){
        println(item)
    }
}

class NewBox<T, U> {
    fun display(item1: T, item2: U) {
        println(item1)
        println(item2)
    }
}

val myBox = Box<String>()
myBox.display("Contents")

val newBox = NewBox<Int, Float>
newBox.display(34, 57.4F)
```
- we can have multiple generics, separated by commas
```
val dictionary = hashMapOf<String, String>()
```

### Type Constraints
- we can restrict the type of generic parameters
```
fun main(args: Array<String>){
    val chef = Chef<Apple>()
    chef.cook(Apple())
}

abstract class Fruit {
    abstract fun peel()
}

class Apple: Fruit() {
    override fun peel(){
        println("Peeling the apple")
    }
}

class Banana: Fruit() {
    override fun peel(){
        println("Peeling the banana")
    }
}

class Chef<T: Fruit> {
    fun cook(item: T) {
        item.peel()
    }
}
```

