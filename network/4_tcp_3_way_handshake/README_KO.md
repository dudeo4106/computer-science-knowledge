# 🔑 TCP 3-way handshake

<br>

## 📌 what is 3-way handshake

TCP가 속해있는 Transport Layer는 두 호스트 간에 녀결을 맺고 최종적인 목적지까지 데이터를 전달하는 기능을 한다.<br>
TCP에서 연결지향적인 특성을 갖게 해주는 과정이 3-way handshake 방식이다.

구체적으로는 TCP/IP 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에, 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정을 의미

Client → Server : TCP SYN<br>
Server → Client : TCP SYN ACK<br>
Client → Server : TCP ACK<br>

* SYN : synchronize sequence numbers
* ACK : acknowledgment

<br>

## 📌 TCP Header

TCP Header는 송신측과 스신측의 포트, sequence numbers 등을 나타내는 비트들로 이루어져있고 중요한 6개의 제어 플래그가 있다.

● SYN


<br>

---

📚 참고 : <br>
[https://ko.wikipedia.org/wiki/%ED%95%B8%EB%93%9C%EC%85%B0%EC%9D%B4%ED%82%B9](https://ko.wikipedia.org/wiki/%ED%95%B8%EB%93%9C%EC%85%B0%EC%9D%B4%ED%82%B9)
<br>
[https://sleepyeyes.tistory.com/4](https://sleepyeyes.tistory.com/4)
<br>
[https://haruhiism.tistory.com/10](https://haruhiism.tistory.com/10)
<br>
[https://mindnet.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-22%ED%8E%B8-TCP-3-WayHandshake-4-WayHandshake](https://mindnet.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-22%ED%8E%B8-TCP-3-WayHandshake-4-WayHandshake)