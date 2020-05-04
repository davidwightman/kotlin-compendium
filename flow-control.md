## Flow Control
- change the directioin of execution of a program
- make decisions
- run part of code multiple times
- stop the execution of a part of code

### if conditional
- you can omit the curly brackets if there is only one expression in the block
```
if (number % 2 === 0)
    isEven = 'is even'
else
    isEven = 'is odd'
```
- shorthand: you can put the expression on a single line if there are no curly brackets
```
if (number % 2 === 0) isEven = 'is even' else isEven = 'is odd'
```
- if conditional can return a result
```
val isEven = if (number % 2 === 0) 'is even' else 'is odd'
```

### expressions

#### arithmetic expressions
- in conditional statements we can use any logical expression
- in keyword checks whether value is in a collection
```
"cat" in listOf("dog", "cat") // true
```

#### ranges
#### in and !in keywords
- in keyword aso allows you to check value in a range
```
5 in 1..10 // true
15 in 1..10 // false
```
- use this in if statements
- the !in keyword checks whether a value is not in a collection
```
"cat" !in listOf("dog", "cat") // false
3 !in setOf(1, 5, 8, 34) // true
5 !in 1..10 // false
15 !in 1..10 // true
if (number !in 1..9) println("number is not a single digit number")
```

#### Boolean returning functions
- a function can be used in a conditional statement if it returns a boolean
```
val animals = arrayListOf<String>()
if(animals.isEmpty()) {
    animals.add("dog")
}
```
- Some functions that you would not expect actually return boolean. For example, add() returns a boolean value true/
- ctrl + space will show you if the function returns a boolean
```
if (animals.add("horse")) { // this conditional returns boolean
    println("horse is added")
}
```

### When conditional
- when conditional 
- when statement (returning a value)
- capturing the subject

#### When
- make decisions base on values of a variable or expression
- if you only have one line then you can omit the curly braces
- you can have nested when statements
```
val animal = "dog"
when(animal){
    "cat"-> {
        // do something
    }
    "dog" ->{
        // do something
    }
    else -> {
        // do something
    }
}
```

#### When as a statement
- when can return a value
```
var action: String = ""
when (animal) {
    "cat" -> action = "pet it"
    else -> action = "google it"
}

var action = when(animal) { 
    "cat" -> "pet it"
    "dog", "bird" -> "pet it"
    else -> "google it"
}
```

#### Capturing the Subject
- it's possible to capture the value in a when statement and use it in the block
```
val name = "Michelle"
when(val length = name.length) {
    in 1..5 -> println("a name with $length is short")
    in 6..10 -> println("a name with $length characters is medium")
    else -> println("a name with $length characters is long)
}
```
- you can use ranges with characters as well
```
when(name[0]) {
    in 'A'..'C' -> println("hello $name")
    in 'D'..'F' -> println("hi $name")
    else -> println("yo")
}
```

### For loops

#### for loops
- executes a block of code for each element in an iterator
```
val collection
for(item: String in collection) {
    // do something
}

val animals = arrayListOf("cat", "dog", "mouse", "bear")
for (animal in animals) {
    println("feed the $animal")
}

// loop through range

for (i in 1..12) {
    val month = when(i) {
        1 -> "January"
        12 -> "December"
        else -> ""
    }
    print("Month number $i is called $month")
}
```

#### ranges in for loops
```
for (i in 1..3) {
    println("Strike $i")
}
```
- ranges can be ascending 1..10
- descending: 10 downTo 0
```
for (i in 10 downTo 0) {
    // do something
}
```
- can skip steps: 10 downTo 0 step 3

#### nested for loops
```
for(i in 1..5) {
    for (j in 1..5) {
        println("$i, $j")
    }
}
```

### while loops
```
var i = 0
while (i < 10){
    // do something
    i++
}
```

#### Do While Loops
- very similar to while loop
- the condition is evaluated at the end
```
var i = 0
do {
    // do something
    i++
} while (i < 10)

var finished = false
do {
    println("enter a number greater than 100")
    val input = readLine()?:""
    var number = input.toInt()
    if(number > 100) {
        println("Thanks")
        finished = true
    } else {
        println("$number is not greater than 100. please try again")
    }
} while (!finished)
```

#### Nested While Loops