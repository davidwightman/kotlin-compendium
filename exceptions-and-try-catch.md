## exceptions

not required to handle exceptions (unlike in java)

```
try {
    println(7/0)
}
catch (e: ArithmeticExceptions) {
    println("caught")
}
Thread.sleep(1000)
```

### Throwing exceptions

```
@Throws (InterruptedException::class)
```

### try as an expression
like if statement, try catch is an expression and can return a value

```
var result = try {
    divide (5, 23)
}
catch (e: Exception) {
    0
}
```

### try with rescources

```
fun printFil() {
    val input = FileInputStream("file.txt)
    input.use (
        // an exception could be thrown here
    )
}
```