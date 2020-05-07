## Lambda Functions

### Lambda Functions
- a lambda function is an anonymous function (has no name)
```
{ name: String -> println("Hello $name")}
```

### Higher order functions
- a HOF is a function that takes another function as a parameter
```
fun sayHello(names: ArrayList<String>, doSomething: (String) -> Unit) {
    for (name in names) {
        doSomething(name)
    }
}

// Lambda can be outside of parenthesis or even below on a new line
sayHello(names) {name: String -> println("Hello there $name")}
```

### Common Higher Order Functions
- forEach
```
val clients = listOf("Anna", "Carol")
clients.forEach { println("Hello $it")}
```

- filter
return collection that passed boolean expression
```
clients.filter {it.length < 5}
 .forEach { println("Hello $it")}
```

- map
creates a new collection based on value of lambda
```
val sizes = clients.map { it.length } 
```

- sortedBy
sort list
```
val clients = listOf("Anna", "Carol")
val sorted = clients.sortedBy {it.length}
```

- maxBy
get maximum value of element based on info in curly brackets
```
val max = clients.maxBy {it.length}
println(max)
```

- minBy
opposite of maxBy. if two have equal size it will get the first one
```
val min = clients.minBy {it.length}
println(min)
```