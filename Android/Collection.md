## *About the Collection*

<br>

```kotlin
package Kotiln

// 14. Collection
// -> list, set, map


fun main (args : Array<String>) {
    // Immutable Collection (값을 변경 못함)
    // List
    var numberList = listOf<Int>(1,2,3,3)
    println(numberList)
    println(numberList.get(0))
    println(numberList[1])

    // Set (집합)
    // - (중복은 허용하지 않는다.)
    // - 순서가 정해지지 않음!!
    var numberSet = setOf<Int>(1,2,3,3,3)
    println(numberSet)
    numberSet.forEach {
        println(it)
    }

    // Map - Key, Value 방식으로 관리한다
    var numberMap = mapOf<String, Int>("one" to 1, "two" to 2)
    println()
    println(numberMap.get("one"))

    // Mutable Collection (값 변경 가능)
    val mNumberList = mutableListOf<Int>(1,2,3)
    mNumberList.add(3,4)
    println(mNumberList)

    val mNumberSet = mutableSetOf<Int>(1,2,3,3,3)
    mNumberSet.add(10)
    println(mNumberSet)

    val mNumberMap = mutableMapOf<String, Int>("one" to 1)
    mNumberMap.put("two", 2)    // map은 값을 추가할때 put 키워드 사용, + to 대신 , 사용
    println(mNumberMap)
}
```