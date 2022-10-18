package Chap3;

class Phone {
	String model;	// String 타입 필드 선언 (핸드폰 모델 저장)
	int value;		// int 타입 필드 선언 (가격 정보 저장)
	
	void print() {
		System.out.println( value + "만 원짜리 " + model + "스마트폰");
	}
}

public class PhoneDemo {
	public static void main(String[] args) {
		Phone myPhone = new Phone();	// myphone은 Phone을 참조함.
		myPhone.model = "갤럭시 S8 ";		// Phone class의 model에 값 저장
		myPhone.value = 100;			// Phone class의 vaule에 값 저장
		myPhone.print();				// print 메서드 호출
		
		Phone yourPhone = new Phone();	// yourphone은 Phone을 참조함.
		yourPhone.model = "G6 ";		// Phone class의 model에 값 저장.
		yourPhone.value = 85;			// Phone class의 value에 값 저장.
		yourPhone.print();				// print 메서드 호출.
		
	}
}
