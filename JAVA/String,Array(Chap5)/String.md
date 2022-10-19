## **String Type (문자열)**

<br>

&nbsp; String 변수는 **참조형** 변수이다.<br><br>
### **String** 생성 방식 
<br>

&nbsp; String 생성 방식에는 **리터럴** 방식과 **new** 연산자를 사용하여 생성방식이 있다.<br><br>

&nbsp; **리터럴 방식**

  -  new 연산자 없이 생성 가능하다 (Ex - String str = "abcd")
  -  문자열의 값은 `'String constant pool'`이라는 별도의 메모리 공간을<br> 할당하여 그곳에 저장한다.(Heap 메모리 영역 내의 별도 영역에 위치함.)
  - 상수풀에 문자열 값이 `없을 경우` 값을 저장 후 `메모리 주소`를 반환.
  - 상수풀에 문자열 값이 `있을 경우` 해당 `문자열의 메모리 주소` 반환.

<br>

&nbsp; **new 연산자 생성 방식**
- 참조형의 기본 객체 생성 방식 (Heep 메모리 영역에 저장)<br>
  -> Ex) String str = new String("abc");

<br>

  ### **Code**
  
  <br>

 &nbsp;  **리터럴 방식**
 ```
package Chap5;

public class Literal {
	public static void main(String[] args) {
		String str1 = "abc";
		String str2 = "abc";
		String str3 = "abcde";
		
		System.out.println(str1);	// 출력 - abc
		System.out.println(str2);	// abc
		System.out.println(str3);	// abcde
		
		
		
		// 객체 주소(해시 코드)값을 구하기 위하여 System.iddentiyHashCode사용!!
		System.out.println(System.identityHashCode(str1));	// 주소 - 111
		System.out.println(System.identityHashCode(str2));	// 주소 - 111 (str1과 값이 같기때문에 같은 주소출력)
		System.out.println(System.identityHashCode(str3));	// 주소 - 123
	
		str1 = "abcde";		// str1값을 변경
		System.out.println(str1);	// 따라서 str1의 값은 abcde 출력
		System.out.println(System.identityHashCode(str1));	// 주소는 str3과 같아짐.
		
		
	}
}

 ```

 &nbsp; **new 연산자 생성 방식**
 ```
 package Chap5;

public class New {
	public static void main(String[] args) {
		String str = "ABC";
		String str2 = new String("ABC");
		
		System.out.println(System.identityHashCode(str));
		System.out.println(System.identityHashCode(str2));
		
		// 출력 - str과 str2의 값은 같지만 str2은 new연산자를 사용했기때문에 별도의 메모리 공간을 할당하여 그곳에 값을 저장하였기에 str과 str2의 주소는 일치하지 않는다.
		
	}
}

 ```
  


