## **Abstract Class (추상 클래스)**

<br>

&nbsp; 추상 클래스란 **메서드 본체{}**가 없거나 **미완성** 메서드를 <br> &nbsp; 가지고 있는 클래스를 의미한다. (보통은 하나 이상 포함, but 포함하지 않을 수도 있음.)<br>

&nbsp; 주의할점 - 미완성 설계도는 객체 생성이 불가능하기에<br>
&nbsp; 반드시 상속을 통해 자식 클래스에서 추장 메서드를 완<br>
&nbsp; 성해야만 객체 생성이 가능하다.<br>

## **Ex-Code**

```
package Test;

abstract class Player {
	abstract void play(int pos);	// 미완성 메서드, pos = 100
	abstract void stop();			// 미완성 메서드
}

abstract class VideoPlayer extends Player {
	void play(int pos) {
		System.out.println(pos + "위치부터 play합니다.");
		// VideoPlayer 메서드는 동작 x (호출 하지 않았기 때문.)
	}
}

class AudioPlayer extends Player {
	void play(int pos) {	// pos = 100
		System.out.println(pos + "위치부터 play합니다");	
		// 출력결과 - 100위치부터 play합니다.
	}
	void stop() {
		System.out.println("재생을 멈춥니다.");
		// main에서 AudioPlayer 메서드를 호출했으므로 문장 출력!!
	}
 }

public class PlayerTest {
	public static void main(String[] args) {
		//Player p = new Player();
		
		Player ap = new AudioPlayer();	// ap이라는 참조변수는 AudioPlayer을 지시함.
		ap.play(100);	// play란 함수에 100을 넘겨줌.
		ap.stop();	
	}
}


```



