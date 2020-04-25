## handling exceptions

### Exeptions
- unexpected event in a program
- the system cannot recover from an exception
- when stopped, data is lost and ux is bad
- exceptions have: message, stacktrace, optionaly a cause

### Try catch and finally
```
try{
    println("works")
} catch (e: Exception) {
    e.printStackTrace()
    println("Error")
} finally {
    println("the execution is complete")
}
```

### throw
- generate your own exceptions
```
throw IllegalStateException("Error message here")
```

