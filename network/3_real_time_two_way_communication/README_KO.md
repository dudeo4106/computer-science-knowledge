# 🔑 Real-time two-way communication

<br>

## 📌 Polling

클라이언트가 서버에서 HTTP Request를 주기적으로 요청하고(Ajax), 서버가 응답하는 방식<br>
Header가 무거운 프로토콜인 HTTP요청을 주기적으로 하기 때문에 클라이언트의 수가 증가하면 서버의 부담이 커진다.<br>
또한 요청/응답후에는 연결이 끊어지기 때문에 요청할 때마다 항상 연결을 맺는 과정이 필요하기에 많은 비용이 소모된다.<br>
요청에 대한 서버 부담이 크지 않거나 실시간 메세지 전달이 크게 중요하지 않은 서비스에서 구현되어야하고, 요청 주기가 짧게 설정되어도 서버의 상태가 자주 변경되지 않는다면 불필요한 트래픽이 발생

## 📌 Long Polling

클라이언트가 서버에 HTTP Request를 요청하면 서버는 timeout이 될 때까지 기다리다가 중간에 보낼 데이터가 있다면 응답을 보내주는 방식<br>
Polling처럼 불필요한 요청에 계속 응답하는 것이 아니기 때문에 커넥션 과정에서 비용이 줄어든다.<br>
클라이언트의 수가 증가하면 응답수도 증가하기 때문에 Polling과 큰차이가 없다.<br>
다만 실시간 메시지 전달이 중요하지만 서버의 상태 변경이 빈번히 발생하지는 않는 서비스에는 적합할 수 있다.

## 📌 Streaming

서버에서 이벤트가 발생했을 때 응답을 해주는데, 응답을 완료 시키지 않고 계속 연결을 유지하는 방식이다.<br>
Polling, Long Polling과 달리 클라이언트와 서버 사이의 연결을 끊지 않고 메세지들 전달하나,<br>
연결을 길게 맺고 있는 경우 연결의 유효성 관리 등의 부담이 발생한다.<br>
보통 특정 시간을 주기로 연결을 재설정하도록 한다.

## 📌 WebSocket

HTTP의 한계를 극복하고 실시간(양방향통신) 서비스 개발을 위해 만들어졌다.

클라이언트와 서버간의 양방향 통신을 수행하려면 클라이언트가 서버로 HTTP Upgrade 요청을 보내야한다. 이를 WebSocket Handshake라고 한다.

서버가 커넥션을 Upgrade 할 경우, HTTP 101응답을 클라이언트로 보내고 서버는 Handshake가 성공적으로 수행되었다고 판단하면 서버/클라리언트 사이의 커넥션을 WebSocket 프로토콜로 Upgrade한다.<br>
즉 클라이언트/서버 사이의 HTTP 101응답이 전달되면 양방향 통신이 가능해진다.

## 📌 Socket.io

JavaScript를 이용하여 브라우저 종류에 상관없이 실시간 웹을 구현할 수 있도록 한 기술이다.

표준 기술이 아니고 Node.js모듈이며 오픈소스이다.

WebSocket, Ajax Long Polling / Multi part Streaming, JSONP polling등을 하나의 API로 추상화 한것이다.

<br>

---

📚 참고 : <br>
[https://valuefactory.tistory.com/263](https://valuefactory.tistory.com/263)
<br>
[https://lkhlkh23.tistory.com/121](https://lkhlkh23.tistory.com/121)
<br>
[https://velog.io/@nameunzz/Polling-vs-Websocket](https://velog.io/@nameunzz/Polling-vs-Websocket)
<br>
[https://winapp81.tistory.com/330](https://winapp81.tistory.com/330)
<br>
[https://velog.io/@jennyfromdeblock/%E3%85%87](https://velog.io/@jennyfromdeblock/%E3%85%87)