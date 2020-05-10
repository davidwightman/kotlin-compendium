##Interfaces
- an interface is a definition of a part of a class
- defines what a class/object can do
- objects can access other objects through their interfaces
- very similart to abstract class
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

### Methods and variables

### inheritance