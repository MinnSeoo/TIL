## **Code**

```java
package Chap7;

abstract class Unit {			// 추상클래스
	int x, y;
	public Unit(int x, int y) {
		this.x = x;
		this.y = y;
	}
	abstract void move();		// 추상 메소드
	void stop() {
		System.out.println(x + "," + y + "에서 멈춥니다");
	}
}

class Marine extends Unit {
	public Marine(int x, int y) {
		super(x,y);
	}
	
	void move() {
		System.out.println("Marine 좌표 : " + x + "," + y);
		x += 10;
		y += 10;
	}	
}

class Tank extends Marine {
	public Tank(int x, int y) {
		super(x,y);
	}
	
	void move() {
		System.out.println("Tank 좌표 : " + x + "," + y);
		x += 5;
		y += 5;
	}
}

class Plane extends Tank {
	public Plane(int x, int y) {
		super(x,y);
	}
	
	void move() {
		System.out.println("Tank 좌표 : " + x + "," + y);
		x += 20;
		y += 20;
	}
}


public class UnitTest {
	public static void main(String[] args) {
		Unit []group = new Unit[4];
		group[0] = new Marine(0,0);
		group[1] = new Tank(10,10);
		group[2] = new Marine(20,20);
		group[3] = new Plane(30,30);
		
		for(int i = 0; i < group.length; i++) {
			group[i].move();
			group[i].stop();
		}
	}
}
```