## Set and HashSet
- Set
- HashSet
- Set Functions
- HashSet Functions

### Set
- Collections that store UNIQUE elements in an undefined order
- example: deck of cards
```
val numbers = setOf(6, 34, 42)
```
- if you add twice it will be only shown once
- empty sets must be created with a specified type
- a set can containe a null element, but only one

### HashSet
- mutable Set
- Set that you can change
- update data
- again, if empty you must provide a type
```
val numbers = hashSetOf(3, 4, 5)
numbers.add(44)
val newNumbers = setOf(56, 7)
numbers.addAll(newNumbers)
numbers.remove(53)
```

### Set Functions
```
val numbers = setOf(3,4,null,83)
numbers.size // 4
numbers.contains(84) // false
val newNumbers = setOf(8456, 3)
numbers.containsAll(newNumbers) // false
numbers.isEmpty() //false
```

### HashSet Functions
- all set functions apply to HashSets
```
val numbers = setOf(3,4,null,83,56)
val newNumbers = setOf(83,345,56)
// retains all elements that are common between two sets
numbers.retainAll(newNumbers) // true
println(numbers) // [56, 83]
numbers.clear() // []

```

