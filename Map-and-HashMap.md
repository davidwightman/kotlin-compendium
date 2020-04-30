## Map and HashMap

### Map
- key-value pairs
- keys are unique
- Immutable
- example: dictionary

```
var count = mapOf(Pair(1, "one"), Pair(2, "two"))
// create an empty map you must specify key and value type
var count = mapOf<Int, String>()
count.get(2) // "two"
count[2] // "two"
count.keys // [1,2]
count.values // [one, two, three]
```

### HashMap
- Mutable map
```
var count = hashMapOf(Pair(1, "one", Pair(2, "two"), Pair(3, "three")))
count.put( 4, "four")
// combine two objects
countMore = hashMapOf(Pair(20, "twenty))
count.putAll(countMore)
```