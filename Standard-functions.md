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