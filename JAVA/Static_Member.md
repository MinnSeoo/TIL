## **Static Member (정적 멤버)**

**CODE**

```
package Chap3;

class Circle1 {
	double radius;		// double 타입의 변수 선언
	static int numOfCircles = 0;	// static 키워드 사용 -> 모든 객체에서 메모리 공유가능  (따라서 어디서든 참조가능하다!!)
	int numCircles = 0;
	
	public Circle1(double radius) {
		this.radius = radius;
		numOfCircles++;
		numCircles++;
	}
}

public class StaticCircle {
	public static void main(String[] args) {
		Circle1 myCircle = new Circle1(10.0);
		// myCircle -> Circle1을 참조하면서 Circle1 생성자에게 10.0을 넘겨줌
		
		Circle1 yourCircle = new Circle1(5.0);
		// yourCircle -> Circle1을 참조하면서 Circle1 생성자에게 5.0을 값으로 넘겨줌. 
		
		System.out.println("원의 개수 : " + Circle1.numOfCircles);	
		// 출력 결과 - 2개 (numOfCircles은 전역변수이므로 외부 클래스에서도 사용가능)
		
		System.out.println("원의 개수 : " + yourCircle.numCircles);
		// 출력 결과 - 1개 (numCircles는 지역변수 이므로 Circle1클래스 종료시 소멸된다.)
	}
}
```
