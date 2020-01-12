### Unit Testing

```
class AgeCalculation() {
    fun getAge(dob: Calendar) : Int {
        return 0
    }
 }

class AgeCalculationTest() {
    @Test  
    fun checkAgeWhenBornToday() {
        assertEquals(0, AgeCalculation().getAge(Calendar.getInstatnce()))
    }
}
```