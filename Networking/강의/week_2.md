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

&nbsp; Simplexing(단방향) - 데이터의 흐름이 한 방향으로만 한정되어 있는 통신방식으로 일방적인 송신,수신만 가능<br>
&nbsp; ex) 라디오를 틀 수 있으나 데이터 수신만 가능한 경우

&nbsp; Duplexing(반 이중) - 컴퓨터 채널이나 단말기, 통신회선, 변복조장치 등에서 통신의 가능 방향을 구분하는 통신 방식의 한 가지이다.<br>
&nbsp; 양쪽방향으로 신호 전송이 가능하지만 경우에 따라 반드시 한쪽 방향으로만 전송이 이루어지게 한 방식을 말한다.

&nbsp; full Duplexing(전 이중) - 송신을 하면서 동시에 수신도 할 수 있는 방식이다.

<br>

### **DNS (Domain Name Service)**

&nbsp; IP 와 VRI를 Mapping(서로 싱크를 맞춤)을 시킨 후 mapping된 정보를 serv에 넣음 (serv는 list방식으로 관리를 하고 있음)  

&nbsp; user가 srv에 대한 주소를 찾아갈때 먼저 DNS srv에게 찾고자 하는 srv 주소를 물어보고(Request) DNS는 list에 user가 찾고자 하는<br>
&nbsp; srv의 주소가 있으면 user에게 response를 주고
user는 해당 srv에 접근(enables)을 하게 도와주는 서비스.

&nbsp; `DNS서비스는 mapping을 중점을 두고 함`

&nbsp; **Client가 srv에 접근하기 위해서 편리하게 접근정보를 관리하고있는 서버임.(mapping,list)**


<br>

### **DHCP (list를 관리하는 서버)**

&nbsp; IPv4의 취약점을 보완하기 위해 사용됨.


<br>

네트워크 상 : 소스IP(출발지) -> 포워딩(Proxy)  -> 타겟IP(도착지) 으로 나뉨

기존에는 소스 -> 타켓으로 연결이 됐었음 but 타겟IP는 직접적으로 데이터를 받기 싫어함 (결벽증)

ex )

1) A(출발지)는 당근마켓을 통해서 거래(아이폰12 판매)를 하고싶어함 (B에게)

2) B(도착지)는 직접적으로 받기 싫어서 C(Proxy)에게 부탁해서 대신받은 후 가져다 달라고 함.

3) C(Proxy)는 A에게 12를 받은 후 B에게 전달을 함

4) B는 12를 받은 후 C에게 돈(Response)을 전달함 

5) C는 A에게 돈을 받음

6) A는 거래가 완료됐으니 더이상 거래를 마침

!! 여기서 중요한것 [포워딩] - 어떤 데이터가 왔을때 자신이 알고있는 데이터를 전달
타켓IP에 대한 Response가 왔을때 포워딩 하고있는 srv에서 데이터를 전달 할 수있는 역할이 됨!!

Proxy - 요청이 왔을경우 정상적인 데이터인지 판단을 한 후 
판단된 결과에 따라서 전달 혹은 거부(DENY)를 하는 역할을 함.

A - > C - > B   


