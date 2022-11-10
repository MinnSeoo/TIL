**Code** 
```java
package InterFace;

interface Animal {
	void Sound();
}

class Dog implements Animal {	
	 public void Sound() {
		System.out.println("멍멍");
	}
}

class Cat implements Animal {
	public void Sound() {
		System.out.println("냐옹");
	}
}



public class AnimalDemo {
	public static void main(String[] args) {
		Dog d = new Dog();
		Cat c = new Cat();
		
		makeSound(d);
		makeSound(c);
	}
	
	static void makeSound(Animal a) {
		// Animal 인터페이스를 구현한 클래스의 인스턴스만 가능!
		a.Sound();
	}
}
```