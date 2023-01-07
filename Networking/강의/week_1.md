## **1주차 강의 정리**

<br>

### **네트워크 탄생 배경**
&nbsp; 1960년대쯤 미국과 소련이 냉전 관계였고 그 당시 핵무기에 대하여 관심이 높을 때였다. 그래서 미국 국방부는 핵전쟁과 같은 중대한 전쟁이 발발했을 시에도<br>
&nbsp; 안정적으로 사용할 수있는 컴퓨터 네트워크 개발의 필요성을 인지했고 이를 대비하고자 미국 내 여러 대학의컴퓨터를 잇는 <br>
&nbsp; **아파넷(APARNET)** 프로젝트를 추진했다.<br>

&nbsp; 이 프로젝트에서는 하나의 메세지가 `패킷` 이라는 작은 메세지로
분활되어 목적지에서 합쳐지는 패킷교환방식이 채택되었다.<br>

&nbsp; 이를 바탕으로 하나의 컴퓨터가 적어도 두 가지 이상의 경로를 통해 접속하거나 하나의 메시지를 여러 조각을 분활할 수 있도록<br>
&nbsp; 네트워크가 설계되었는데 이것이 바로 `이더넷` 이다.

---

<br>

### **네트워크 통신 방식**
&nbsp; `Client(desktop) - switch - router - switch - server`<br>
&nbsp; Client,Server -> node라고함 (End Point or End User 라고 함)<br>
&nbsp; Switch, Router -> 네트워크를 중계 해 준다 그래서 **중계 node** 라고 한다.<br>
&nbsp; 그리고 각 노드와 중계 노드를 연결시켜주는 선을 **Link** 라고 한다.<br>

### **Client가 Server에 접근하기 위해서**
&nbsp; 1. client가 DNS라는 서버에 Request(요청)를 보낸다.<br>
&nbsp; 2. DNS는 client가 찾고있는 서버가 어디에 있는지 알려준다.<br>
&nbsp; 3. client가 원하는 서버에 Request를 보낸다.<br>
&nbsp; 4. 그 서버는 client에게 Respon(응답)를 보낸다.

### **OSI 7 Layer**
**1계층(물리계층) : Bit, Bandwidth, Ethernet, UTP, STP** <br>
&nbsp; UTP - 쉽게 끊어지고, 전기적 간섭이 많아 데이터 손실 가능성이 높다.<br>

&nbsp; STP - 전기적 간섭이 없고 질겨 쉽게 끊어지지 않지만 UTP케이블에 비해 비싸다는 단점이 있다. <br>

&nbsp; Bandwidth - 대역폭을 말한다.<br>

&nbsp; Bit - 전기적 신호를 말한다. (비트들은 대역폭에 따라 속도가 빠르거나 느려질 수도 있다.)<br>

&nbsp; Hub - 컴퓨터와 컴퓨터 사이, 네트워크와 네트워크 장비를 연결 해 주는 기능을 수행하는 장치이다.<br>

&nbsp; Dummy Hub - 인터넷 선을 연결하면 해당 포트에 여러개로 나뉘여서 여러 대의 PC와 서버들이 인터넷을 사용 가능하게끔 하는 기능이다.<br>

**2계층(데이터) Switch Hub, Bridge, ARP, RARP**

&nbsp; Switch Hub - Dummy Hub와 달리 각 Port별로 대역폭 즉 Brodwidth를 제공하며 자기에게 물려진 PC,Server들의 MAC주소를 저장한다.

&nbsp; Bridge - 다른 네트워크들의 대역을 연결시키는 장비 (1:1만 가능)<br>

&nbsp; ARP - Address Resolution Protocol의 약자로 IP 주소를 MAC 주소와 매칭 시키기 위한 프로토콜이다.<br>

&nbsp; RARP - Reserve Address Resolution Protocol의 약자로 MAC  주소를 IP 주소와 매칭 시키기 위한 프로토콜이다.<br>

**3계층 (네트워크) - Packet, IP Address, ICMP, Router, Rating**

&nbsp; Packet - 네트워크 상에서 주고받는 데이터.<br>

&nbsp; ICMP - TCP/IP에서 IP 패킷을 처리할 때 발생되는 문제를 알려주는 프로토콜이다.<br>

&nbsp; Router - 각각의 인터넷을 연결시켜주는 역할을 한다.

&nbsp; Rating - 라우터는 라우팅을 해서 request가 가장 빨리 갈 수 있는 최적의 경로를 탐색하여 알아낸다.

**4계층 (전송) - TCP, UDP, Socket, L4 Switch, Segmantation**

&nbsp; TCP - 전송 제어 프로토콜로 서버와 클라이언트간에 데이터를 신뢰성 있게 전달하기 위해 만들어진 프로토콜이다.<br>
`특징` <br>
&nbsp; 1) 연결형 서비스로 가상 회성 방식을 제공한다.

&nbsp; 2) 데이터의 경계를 구분하지 않는다.

&nbsp; 3) 데이터의 전송 순서를 보장한다.

---

&nbsp; UDP - User Datagram Protocol의 약자로 비연결성, 신뢰성이 없는 전송 프로토콜이다.<br>
`특징` <br> 
&nbsp; 1) 흐름제어, 오류제어 또는 손상된 세그먼트 수신에 대한 재전송을 하지 않는다.

&nbsp; 2) 내용 전송 중에 손실 될 수 있고, 전송되는 세그먼트의 순서가 바뀔 수 있다.

&nbsp; 3) UDP는 TCP보다 간단하고 빠르다.


---
<br>

&nbsp; L4 Switch - L4 스위치는 로드밸런싱(서버 부하 분산)을 처리하는 장비이다.

&nbsp; Segmantation - 각각의 데이터들을 분할하는 역할을 한다.












