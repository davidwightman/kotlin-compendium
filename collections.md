## Collections
- Zero or more elements
- all of the elements have to be the same type in Kotlin
- a collection is iterable
```
// examples
[1,1,2]
[]
["January", "February"]
```

### Types of Collections
- List, MutableList
- Set, MutableSet

### List
- Ordered collections
- elements can be accessed by the position (index)
- can contain duplicate elements

### Set
- group of UNIQUE elements
- the order has no significance
- we can go through elements one by one but the order is not defined
```
[1,2,3]
```
- example: a deck of cards

### Map
- a set of key-value pairs
- keys are unique
- each key maps to exactly one value
- values can be duplicates
```
{1=one,
3=three,
5=five}
```
- example: dictionary, maps words to definitions

### Iterator
- an object that loops through elements of a collection