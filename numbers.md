## Numbers

types of numbers

Short 16 bits
Int 32 bits
Long 64 bits

Float 32 bits 6-7 decimals
Double 64 bits 15-16

int and double are most common

### implicit numbers are decided by kotlin
```
val cat = 3 // Int
val dog = 14.99 // Double
```

### explicit: provide types

```
val car: Int = 8
```

### type conversions

```
val cats = 3 // Int
val longCats = cats.toLong() // Long

// result of operation is converted but not original var (cats)
```

Don't convert a Long to an Int
```
val people 7500000000000000000
val fewPeople = people.toInt()
```

Other Conversions:
```
toByte()
toShort()
toInt()
toLong()
toFloat()
toDouble()
```
