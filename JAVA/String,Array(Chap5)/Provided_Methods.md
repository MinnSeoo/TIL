## **Methods provided by the String class (String 클래스에서 제공하는 메서드)**

<br>

- **char charAt(int index) -** index가 `지정한 문자`를 반환.
- **String concat(String s) -** 주어진 문자열 s를 `현재 문자열 뒤`에 연결
- **boolean contains(String s) -** 문자열 s를 `포함`하는지 조사.
- **int length() -** 길이를 반환.
- **String substring(int index) -** index부터 시작하는 문자열의 일부를 반환 ()
- **String toLowerCase() -** 모두 소문자로 변환.
- **String toUpperCase() -** 모두 대분자로 변환.
- **String trim() -** 앞뒤에 있는 공백 제거 후 반환.

<br>

## **Code**
```
package Chap5;

public class StringMethod {
	public static void main(String[] args) {
		String s1 = "Hi, ";
		String s2 = "Java";
		String s3, s4;
		
		System.out.println("문자열 길이 : " + s1.length());
		// 출력 - s1의 길이는 공백, 쉼표포함 4
		
		char c = s1.charAt(1);	// charAt는 index가 지정한 문자를 반환 하므로 i반환
		System.out.println(c);	// 따라서 출력결과 -> i
		
		
		s1 = s1.concat(s2);		// concat 메서드 사용 -> Hi, Java가 출력됨
		
		s3 = s1.toLowerCase();	// s1의 문자열을 모두 소문자로 반환 -> hi
		s4 = s1.substring(4,8);	
		// s1은 현재 - > Hi, Java 인데 substring 메서드 사용 4~7번째 인덱스 문자까지만 반환 -> Java 
		
		System.out.println(s1 + "!");
		System.out.println(s3 + "!");
		System.out.println(s4 + "!");
		
		
	}
}
```