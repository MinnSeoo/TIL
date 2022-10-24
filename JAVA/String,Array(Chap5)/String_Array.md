## **String Array (String 배열)**

<br>

### **Code**

```java
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

**Ex_CODE**

```java
package Char_String;    

import java.util.Arrays;
import java.util.Scanner;

public class StrArr_Ex5 {
	public static void main(String[] args) {
        Scanner in = new Scanner(System.in);        // 데이터 입력 변수
        String[] name = new String[] {"A", "B", "C", "D", "E"}; // 문자열 변수 선언과 동시에 초기화
        int[] score = new int[name.length];     // score의 배열 길이 = name배열의 길이
        int i = 0, sum = 0; 
        int max = 0;

        for (i = 0; i < name.length; i++) {     // i가 name배열의 길이보다 작을동안
            System.out.printf("%s 학생의 점수를 입력하세요 : ", name[i]);       
            score[i] = in.nextInt();         // 점수 입력 받음 (name배열에 값 저장)
            sum += score[i];                 // sum에 score[i]번째 값 더함
            if (score[max] < score[i]) {     // score[i]번째 원소값이 max보다 작을경우
                max = i;    // max에 i값 대입
            }
        }
        System.out.print("5명 점수 출력 : [");
        for (i = 0; i < name.length - 1; i++) {
            System.out.print(score[i] + ", ");
        }
        System.out.println("5명 점수 출력 : "+ Arrays.toString(score));     //toString - 문자열 반환
        System.out.println("합계 : " + sum);        // 합계출력
        System.out.println("평균 : " + (double)sum / name.length);  // 평균출력
        System.out.println("최고 점수 받은 학생 이름 : " + name[max]);      // 최고점학생 출력
    }
}
```


