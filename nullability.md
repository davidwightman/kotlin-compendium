## Nullability

### Null value

- no value present, variable does not exist
- if you use a variable with a null value, your program will crash with a NullPointerException (NPE)
- kotlin guards against null values
- kotlin differentiates between variable that can be null and those that cannot using the ? operator
```
val herName: String = "Lilly"
val hisName: String? = null
```
- if the variable can be null, you must provide a value IF you wan to use 

### Null Arithmetic operators
- cannot use the classic operators for null variables
- replacement methods
```
?.plus()
?.minus()
?.times()
?.div()
?.rem()
```
So that would look like the following...
```
val a: Int? = 10
a?.plus(3) // 10
```

### elvis operator
- Guarantees a result returned
- either the actual result for a non-null variable, or a default value
```
val catName: String? = null
println(catName?:"This cat has no name")
catName.length
```
- no need for null safety after elvis operator

### non-null assertions
```
!!.
```
- a developer guarantee that the variable is not null
- bypasses all the language chekcs for null safety 
- can trigger a program crash