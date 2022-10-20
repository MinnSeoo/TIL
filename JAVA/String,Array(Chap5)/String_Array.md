## **String Array (String 배열)**

<br>

### **Code**

```
package Chap5;

public class String_Array {
	public static void main(String[] args) {
		String[] name = new String[3];	// new 연산자 사용하여 객체 생성
		
		name[0] = new String("아름"); 
		name[1] = "다운";		// new연산자 사용하지 않고 리터럴 방식으로 간략히 표현가능!
		name[2] = "나라";
		
		String[] name2 = new String[] {"안녕", "하세요"};
		String[] hi = new String[] {"hi", "by"};	// 괄호 사용 간략히 표현가능!!
		
		String[] name3 = {"hahah", "nananan"};	// new String[] 생략 가능!
		
		name3[name3.length-1] = "kakaka";	
		// name3의 길이-1의 index번호 -> 1이기 때문에 1번 index에 kakaka값 삽입.
		
		for(String n : name3) {
			System.out.println(n);
		}
	}
}
```


