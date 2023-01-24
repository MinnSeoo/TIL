## **2주차 강의 정리**

<br>

### **TCP 3-way Handshaking**

TCP 장치들 사이 논리적 접속을 성립(establish)하기 위하여 three-way handshake를 
사용함.

tcp 3 way handshake는 TCP/IP프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전<br> 
먼저 "정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정 의미"

Client > Server : TCP SYN(Synchronize sequence numbers) 시퀸스 번호 동기화

Server > Client : TCP SYN ACK

Client > Server : TCP ACK(Acknowledgment)

#### **역할**

1) 양쪽 모두 data를 전송할 준비가 되었다는 것을 보장하고, 실제 data 전송 전 
      한쪽에서 다른 쪽이 준비되었다는 것을 알수 있도록 한다.

2) 양쪽 모두 상대편에 대한 초기 순차일련번호를 얻을 수 있도록 한다.


#### **과정**


[STEP1]

A_client는 B_server에 접속을 요청하는 SYN !패킷!을 보냄 (패킷- 네트워크를 전송하기 쉽도록 자른 데이터 전송 단위)

이때 A_client SYN을 보내고 SYN/ACK 응답을 기다리는 `SYN_SENT` 상태가 됨.

[STEP2]

B_server는 SYN요청을 받고 -> A_client에게(요청 수락)ACK와 SYN flag 가 설정된 패킷 발송 후
A가 다시 ACK으로 응답하기를 기다림. 이때 B_server는 `SYN_RECEIVED` 상태됨.

[STEP3]

A_client는 B_server에게 ACK를 보내고 이후부터는 연결이 이루어지고 데이터가 오가게 된다
이때 B_server 상태가 `Established` 이다.


위와 같은 방식으로 통신하는것이 신뢰성 있는 연결을 맺어줌!
(참고로 3-way handshake는 Tcp 연결을 초기화 할때 사용됨)

<br>


### **통신방식**

&nbsp; 단방향 통신 - 데이터의 흐름이 한 방향으로만 한정되어 있는 통신방식으로 일방적인 송신,수신만 가능<br>
&nbsp; ex) 라디오를 틀 수 있으나 데이터 수신만 가능한 경우

&nbsp; 반 이중 - 컴퓨터 채널이나 단말기, 통신회선, 변복조장치 등에서 통신의 가능 방향을 구분하는 통신 방식의 한 가지이다.<br>
&nbsp; 양쪽방향으로 신호 전송이 가능하지만 경우에 따라 반드시 한쪽 방향으로만 전송이 이루어지게 한 방식을 말한다.

&nbsp; 전 이중 - 송신을 하면서 동시에 수신도 할 수 있는 방식이다.

