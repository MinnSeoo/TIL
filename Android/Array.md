## **배열**

<br>

```kotlin
package Kotiln

// 12 배열

// 배열이 필요한 이유
//

fun main(args : Array<String>) {
    // 배열을 생성하는 방법(1)
    var group1 = arrayOf<Int>(1,2,3,4,5)
    var group2 = arrayOf<String>("apple", "banana", "pineapple")

    println(group1 is Array)
    println(group2 is Array)

    // 배열을 생성하는 방법(2)
    var array = arrayOf(1,2,3.5,"hello")

    // 배열의 값을 꺼내는 방법1
    val print = array.get(3)
    println(print)

    // 배열의 값을 꺼내는 방법2
    val print2 = array[0]
    println(print2)

    // 배열의 값을 바꾸는 방법1
    group1.set(0,100)
    println(group1[0])

    // 배열의 값을 바꾸는 방법2
    group2[0] = "peach"
    println(group2[0])
}
```