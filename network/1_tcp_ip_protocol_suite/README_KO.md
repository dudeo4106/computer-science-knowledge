# 🔑 TCP / IP Protocol Suite

> It was 4 layers, it has been updated to 5 layers

<br>

## 📌 Physical Layer

> bit → analog signal
> <br>
> analog signal → bit

7계층 중 최하위 계층이며, 주로 전기적, 기계적등의 특성을 이용해 데이터를 전송한다.<br>
데이터는 0, 1이며(On, Off) 전기적 신호상태로 이루어져 있다.<br>
전선을 통해 전자기파를 보내 전기 신호를 송수신 하는데, 전선은 모든 전자기파를 다 통과 시킬수 없기에, 데이터의 손실이 발생한다.<br>
(주파수는 0 ~ 무한대의 주파수 범위를 갖기 때문에)<br>

송신자는 이러한 손실 없이 데이터를 보내기 위해서는 아날로그 신호로 변환시켜서 송신하고(encoding)<br>
수신자는 아날로그 신호 수신후, 0과 1로 해석해서 사용하면 된다(decoding)<br>

이렇게 변환하는 모듈은 PHY 칩이라는 이름으로 하드웨어적으로 만들어져 있다.

<br>

## 📌 Data Link Layer

> frame

설명에 앞서 여러대의 컴퓨터가 통신하기 위해서는 라우터(L3스위치)에 여러대의 컴퓨터를 연결하고 이것을 하나의 네트워크라고 한다.<br>
이렇게 라우터로 연결된 여러 네트워크를 하나로 연결하면 인터넷이라고 한다.<br>

송신측에서는 특정 컴퓨터와 데이터 송신을 하기 위해서는 바로 이웃 네트워크(라우터)만을 생각한다.<br>
그렇게 되면 목적지(특정 컴퓨터 = 특정 IP)까지 바로 이웃 네트워크를 거쳐가면서 통신이 진행되게 된다.<br>

수신 측에서는 010101010이라는 데이터가 오게되면 총 몇개의 컴퓨터에서 데이터가 왔고, 각 데이터 별 시작과 끝을 알 수가 없다.<br>
그렇기에 데이터의 맨 앞에 특정한 숫자(header)를, 그리고 끝에 특정한 숫자(tail)를 추가해서 데이터의 시작과 끝을 특정해서 데이터를 정확히 분류 할 수 있다.<br>

정리하자면 직접 연결된 서로 다른 2개의 네트워킹 장치간의 데이터 전송을 담당하며 전송되는 데이터를 frame　이라고 한다.<br>
이 계층에서는 프로토콜들의 용도에 따라 frame의 종류, 길이 등의 정보를 정의한다.<br>
MAC이라고 하는 매체 접근 제어 기능이 있으며 48비트의 주소를 갖고 있다.<br>

마지막으로 이 계층은 Lan card이며 1계층과 마찬가지로 하드웨어적으로 만들어져 있다.

<br>

## 📌 Internet Layer

> packet

특정 컴퓨터에 데이터를 보내기 위해서는 IP주소를 알아야한다.<br>
데이터와 대상 컴퓨터의 IP주소 등의 정보를 정해진 규칙대로 분할시켜서 송신하게 되는데, 이 단위를 패킷이라고 한다.<br>
이 패킷들은 수많은 라우터를 경유하며(routing) 특정 컴퓨터에 데이터를 전송하게 된다.<br>

패킷의 구조
1. 버전: IPv4 vs IPv6
2. TTL(Time to Live): 네트워크 상에서 남아있을 수 있는 시간이며, 라우터를 걷혀가며 카운터를 감소시킨다.
3. Protocol: TCP vs UDP
4. 패킷 헤더 체크섬: 중복 검사의 한형태로 송신된 자료의 무결성을 보호하는 방법이며 헤더가 손상되지 않은 경우 패킷이 양호 하다고 간주
5. 소스 주소: 네트워크로 보내는 장치의 IP Address
6. 대상 주소: 패킷이 전송되는 주소
7. 데이터

정리하면 논리적 주소를 바탕으로 패킷의 전달 경로는 결정하는 역할을 하며(routing),<br>
데이터를 패킷 단위로 분할하여 전송한 후 재결합시키는 역할을 한다.(패킷에는 논리 주소가 포함되어 있음)

마지막으로 이 계층은 운영체제의 커널에 소프트웨어 적으로 구현되어 있다.

[추가]

|Protocol Example|
|---|
|IP|
|ICMP|
|ARP|
|...|

<br>

## 📌 Transport Layer

> segment(tcp) / datagram(udp)

네트워크 계층은 패킷 전송을 담당하지만 최적의 경로 탐색, 존재여부, 패킷손상여부 등등의 문제를 신경 쓰지 않는다.<br>
패킷이 수신 컴퓨터에 제대로 도착할 수 있도록 패킷 전송을 제어하는 역할은 전송 계층이 담당한다.

데이터 전송을 위해서 Port 번호가 사용된다.<br>
Port 번호는 하나의 컴퓨터에서 동시에 실행되고 있는 프로세스들이 서로 겹치지 않게 가져야하는 정수값을 의미하며,<br>
송신자는 데이터를 보낼 때 데이터를 받을 수신자의 프로세스의 Port 번호를 붙여서 보내야 한다.<br>

정리하면 전송 계층부터는 컴퓨터 내부에 있는 애플리케이션의 전송을 담당하며, 통신하고자하는 애플리케이션 간에 가상 연결 통로를 만들어 연결을 확립하는 작업이다.<br>
네트워크 계층은 IP(컴퓨터)에 데이터를 보내는 것이 였다면, 전송 계층은 Port 번호를 사용하여 컴퓨터 안의 수신 받을 특정 애플리케이션을 식별 하게 해준다.

마지막으로 이 계층은 운영체제의 커널에 소프트웨어 적으로 구현되어 있다.

[추가]

|Protocol Example|
|---|
|TCP|
|UDP|
|...|

<br>

## 📌 Application Layer

> message, data

설명에 앞서 OSI 7 Layer는 개념적 모델이고, 현대의 인터넷은 OSI 모델이 아니라 TCP/IP 모델을 따르고 있습니다.<br>
OSI 7 Layer는 Session, Presentation, Application Layer로 분리 되는 형식을 사용하지만,<br>
TCP/IP 모델은 Application Layer로 통합해서 사용한다.

이 계층은 다른 계층의 서비스가 접근 할 수 있게 하는 어플리케이션을 제공하며 데이터 교환하기 위해 사용되는 프로토콜을 정의한다.<br>
예를 들어 TCP / IP 소켓 프로그래밍이 있다.<br>
운영체제의 Transport layer에서 제공하는 API를 활용해서 통신 가능한 프로그램을 만드는 것으로,<br>
소켓 프로그래밍을 통해서 누구나 자신만의 Application Layer에 인코더와 디코더를 만들 수 있다.

우리가 많이 보는 프로토콜이 이 계층이 있고 프로토콜의 종류는 다음과 같다

|Protocol Example|
|---|
|HTTP|
|FTP|
|Telnet|
|DNS|
|...|

<br>
<br>

---

📚 참고 : <br>
[https://www.youtube.com/watch?v=1pfTxp25MA8](https://www.youtube.com/watch?v=1pfTxp25MA8)
<br>
[https://jhnyang.tistory.com/373](https://jhnyang.tistory.com/373)
<br>
[https://enlqn1010.tistory.com/9](https://enlqn1010.tistory.com/9)
<br>
[https://better-together.tistory.com/134](https://better-together.tistory.com/134)
<br>
[https://goitgo.tistory.com/25](https://goitgo.tistory.com/25)
<br>
[https://devowen.com/344](https://devowen.com/344)
