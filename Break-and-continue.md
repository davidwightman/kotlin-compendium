### Break and Continue

#### Break
- terminates a loop
```
var onlyEvenNumbers = arrayListOf(2,8,4,6,7,9)
for (number in onlyEvenNumbers){
    if (number % 2 != 0) break
    println("Half of $number is ${number /2}")
}
```

#### Continue
- proceeds to the next step of a loop, doesn't stop everything but just stops the current iteration
```
var onlyEvenNumbers = arrayListOf(2,8,4,6,7,9)
for (number in onlyEvenNumbers){
    if (number % 2 != 0) continue
    println("Half of $number is ${number /2}")
}
```

#### Labels
- a labe is used to mark a position in code that you can jump to 
- can be used with break and continue
```
loop@ for (i in 1..10){
    for (j in 1..10) {
        if (i%3 == 0)
            break@loop
        println("$i, $j")
    }
}
```