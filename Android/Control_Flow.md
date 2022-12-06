## **Kotlin 제어흐름**

<br>

**(안드로이드 강의 - 제어흐름 정리)**

```kotlin
package Kotiln

// 제어 흐름(2)

fun main(args : Array<String>) {
    val value : Int? = null

    when(value) {
        null -> println("value is null")
        else -> println("value is not null")

    }

    val value2 : Boolean? = null

    // when 구문은 조건으로 갖는 값의 모든 경우에 대응 해 주는 것이 좋다.
    when(value2) {
        true -> println("value2 is true")
        false -> println("value2 is false")
        null -> println("value2 is null")
    }
    // 값을 리턴하는 when 구문은 반드시 값을 리턴 해야 한다.
    val value3 = when(value2) {
        true -> 10
        false -> 20
        null -> 30
    }
    println(value3)

    // when의 다양한 조건식(1)
    val value4 : Int = 10
    when(value4) {
        is Int -> {
            println("value4 is int")
        }
        else -> println("value4 is not int")
    }

    // when의 다양한 조건식(2)
    val value5 : Int = 61
    when(value5) {
        in 50..60 -> println("value5 is in 50 ~ 60")    
        // value5값이 50~60사이일 경우 문장 출력
        in 61.. 70 -> println("value5 is in 61 ~ 70")   
        // 61~70사이일 경우 문장 출력
        in 71 .. 80 -> println("value5 is in 71 ~ 90")  
        // 71 ~ 90 사이일 경우 문장 출력
    }

}
```