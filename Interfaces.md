##Interfaces
- an interface is a definition of a part of a class
- defines what a class/object can do
- objects can access other objects through their interfaces
- very similar to abstract class
- can be used as variable types
```
inteface Oven {
    val temperature: Int
    fun turnOn()
    fun turnOff()
    // implementations ussually do not contain complete function
    fun cook(temp: Int){
        println("Cooking at $temp degrees")
    }
}
```
### Implementation
```
val myOven: Oven = Bosch()
myOven.turnOn()
myOven.turnOff()

class Bosch: Oven {
    override val temperature: Int

    override fun turnOn(){
        println("Turning on")
    }

    override fun turnOff(){
        println("Turning off")
    }
}
```

- a class can implement multiple interfaces
```
interface PlaceToSit{

}

interface PlaceToSleep{

}

class Couch: PlaceToSit, PlaceToSleep {}
```
- an interface has no constructor
- an interface can implement methods but does not need to
- an interface cannot initialize values but can update them through methods
- an interface can inherit from another interface

```
fun main (args: Array<string>){
    val fancy = FrenchRest() 
    val frenchBread: Food = fancy.orderFood()
}

interface Food {
    fun feed()
}

class French: Food {
   fun delight() {
        println("delighted by french food")
    }

    override fun fun feed(){
        println("french will feed you")
    }
}

class Fast: Food {
    override fun feed(){
        println("fast food will feed you")
    }
}

class FrenchRest {
    fun orderfood(): Food{
        val fancyFrenchFood = French()
        return fancyFrenchFood
    }
}

class FastRest {

}
```
