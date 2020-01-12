### Interfaces

```
interface BookingManager {
    // variables in interface
    val version: String

    fun isSeatFree(seat: Seat) : Boolean
    fun reserveSeat(seat: Seat, customerID: Long) :Boolean

    fun systemStatus() = "All Operations are Functional"
}

open class BasicBookingManager(authorizationKey: String) : BookingManager {
    override val version = "1.0"

    override fun isSeatFree(seat: Seat) = true
    override fun reserveSeat(seat: Seat, customerID: Long) = false
}
```

### extends a class

all classes in Kotlin are final, you cannot extend. you must make class open to extend

when extending a class, must call constructor passing in paramaters

```
class AdvancedBookingManager: BasicBookingManager ("1234"), java.io.Closeable {
    override val version = "2.0"
    fun howManyBookings() = 10
    override fun close() {}
}
```

you can only extend from a single class like java. but you can have multiple interfaces. see above with Closeable

### add functions to existing classes

below adds addition functions to all strings in file

```
fun String.toSentenceCase() : String {
    return this[0].toUpperCase + this.substring(1)
}
val my list = mutableListOf<Int>()
```