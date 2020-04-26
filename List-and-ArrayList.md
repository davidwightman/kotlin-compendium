## Lists and ArrayList
- List
- ArrayList
- List functions
- ArrayList functions

### List
- ordered collection that can containe duplicate elements
- remember: lists are immutable
- remember: lists can contain duplicate elements
- list can contain nulls because null value is considered any element type
- to create a list:
```
val colors = listOf("blue", "yellow", "red", null)
```
- empty list must specify the element type
```
var colors = listOf<String>()
```
- 2 ways to retrieve the element of the list:
```
colors[1] // "yellow"
colors.get(1) // "yellow"
```
- if you access an index that is out of range you will get an exception
- get the size of list
```
colors.size // 4 
```

### ArrayList
- A mutable (changeable) list
- create like this:
```
var colors = arrayListOf("blue", "red")
var noColors: ArrayList<String> = arrayListOf<String>()
// system can infer type so that is not required
```
- to add elements
```
colors.add("yellow")
```
- add another collection
```
var moreColors = arrayListOf("pink", "teal")
colors.addAll(moreColors) // [blue, red, yellow, pink, teal]
```
- remove an element
- if list contains multiple entries of the same it will remove the first entry
```
colors.remove("red")
colors.removeAll(moreColors)
colors.removeAt(1)
```

### List Functions
- check if it contains, returns boolean
```
colors.contains("red")
```
- check if one list contains all the items of another list, returns boolean
```
colors.containsAll(newColors)
```
- get index of 
```
colors.indexOf("blue")
```
