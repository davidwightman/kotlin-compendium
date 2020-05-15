## Extensions
- allow us to extend a class that we don't own or cannot modify
- without the need to inherit from that class
- add functionality that is available int the context of our program only
- added code can be called the usual way by declaring objects of that class and invoking methods
- can extend functions, properties, companion object

### Extension functions
- can add functions to classes that we don't own or cannot modify
- can acdces the object using the 'this' reference
```
fun String.slim() = this.substring(1, length-1)

val name = "Michael"
println(name.slim())
```
- the original class is not actually modified
- rather it is a shortcut to make the functions available using the usual object.function notation

### Extension Properties
- can add properties to classes, in a similar way to functions
```
val String.betterLength: Int
    get() = 200

println("Michael".betterLength)
```
- they cannot be local, i.e. declared inside a function or class
- cannot updat an extension property can only use values (val), not variables (var)
- the property is not actually inserted into the class
- the extension properties are a shortcut for the . notation
- therefore initializers are not allowed
```
val String.betterLength = 7 // Error
```

### Companion object extensions
- if a class has a companion object defined, we can extend it with functions and properties
- if not, we cannot add a companion object
```
class Book {
    companion object {}
}

fun Book.Companion.printMe(){
    println("Car companion object")
}

fun main(args: Array<String>) {
    Book.printMe()
}
```