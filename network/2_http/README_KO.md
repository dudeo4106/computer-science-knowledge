# 🔑 HTTP

<br>

## 📌 What is HTTP?

HTTP는 HyperText Transfer Protocol의 약자며 하이퍼텍스트(HTML) 문서를 교환하기 위해 만들어진 protocol이다<br>
즉 웹상에서 네트워크로 서버끼리 통신을 할 때 어떠한 형식으로 통신을 하자고 규정해 놓은 통신구조이다.

프론트앤드 서버와 클라이언트간 통신, 백앤드와 프론트앤드 서버간에서의 통신에도 사용된다.<br>
HTTP는 application layer, TCP/IP 기반으로 되어있으며 기본 포트는 80번이다.

<br>

## 📌 HTTP 통신방식

HTTP는 기본적으로 클라이언트의 요청(Request) 서버의 응답(Response) 구조로 이루어져있고 server/client 모델을 따른다.<br>
또한 Stateless, 요청이오면 그 요청에 대한 응답을 하지 여러 요청과 응답이 연결되어있지 않고 독립적인 요청과 응답이다.<br>

● 장점

클라이언트와 서버가 계속 연결된 형태가 아니기 때문에 클라이언트와 서버간의 최대 연결 수 보다 훨씬 많은 요청/응답을 처리할 수 있다.<br>
그렇기에 불특정 다수를 대상으로 하는 서비스에 적합할 수 있다.

● 단점

일방적으로 연결을 끊어버리기 때문에, 클라이언트는 이전 상황을 알 수가 없어(Stateless) 정보를 유지하기 위해 Cookie 같은 기술이 등장하였다. 

<br>

## 📌 HTTP Request 구조

● Start line

> GET /user HTTP/1.1

Start line은 3부분으로 구성되어 있다.<br>

1. HTTP Method: actions을 정의하는 부분으로 GET, POST등이있다.
2. Request target: 전송되는 URL
3. HTTP Version: 버전으로 1.0, 1.1, 2.0 등이있다.

● Headers

Request에 대한 추가 정보를 담고 있는 부분으로 body의 총길이, User-Agent등이 담겨 있다.<br>
key, value값으로 되어있고 Headers도 크게 (general, request, entity)등으로 나뉘어있다.

```
[General]
Request URL: https://stats.g.doubleclick.net/j/collect?t=dc&aip=1&_r=3&v=1&_v=j94&tid=UA-36116321-5&cid=1220086081.1633797781&jid=115805083&gjid=95221981&_gid=697110753.1635251935&_u=QACAAAAAAAAAAC~&z=1203385225
Request Method: POST
Status Code: 200 
Remote Address: 74.125.23.157:443
Referrer Polic
...
```

[자주 사용되는 header 정보]<br>
Host: 요청이 전송되는 target의 host url<br>
User-Agent: 요청을 보내는 클라이언트의 대한 정보<br>
Accept: 해당 요청이 받을 수 있는 응답(response) 타입<br>
Connection: Request 후 연결을 닫을 것인지 유지할 것인지를 나타낸다. Close / Keep-Alive<br>
Content-Type: 해당 요청이 보내는 메세지 body의 타입으로 application/json, text/plain등이 있다.<br>
Content-Length: 메세지 body의 길이<br>

● Body

실제 메세지의 내용이다.<br>

<br>

## 📌 HTTP Response 구조

● Start line

> HTTP/1.1 401 BadRequest

1. HTTP Version: 버전
2. Status code: 응답 상태를 나타내는 숫자 코드
3. Status Text: 응탑 상태를 설명해 주는 부분

● Headers

Request Header와 기본적으로 동일하며, Response에서 사용되는 특정 Header가 있는데 User-Agent 대신에 Server가 들어간다.

● Body

Request body와 마찬가지로 실제 데이터 전송이 필요없는 경우 body가 빈다<br>

<br>

## 📌 URL

URL(Uniform Resource Locators)은 개발자가 아니더라도 이미 우리에게 익숙한 용어이며, 서버에 자원을 요청하기 위해 입력하는 영문주소<br>

> https://www.google.com:443/path/resource?a=1&b=2

http: protocol<br>
www.google.com: host<br>
443: port<br>
path/resource: resource path<br>
query: a=1&b=2<br>

<br>

## 📌 HTTP Request Method

URL를 이용하면 서버에 특정 데이터를 요청할 수 있는데 요청하는 데이터에 특정 동작을 수행하고 싶으면 HTTP Request Method를 사용

● GET: 존재하는 자원에 대한 요청<br>
● POST: 새로운 자원 생성<br>
● PUT: 존재하는 자원에 대한 변경<br>
● DELETE: 존재하는 자원에 대한 삭제<br>

● HEAD: 서버 헤더정보 요청, ResponseBody 반환하지 않음<br>
● OPTIONS: 서버 옵셕들을 확인하기 위한 요청. CORS에서 사용<br>

<br>

## 📌 HTTP Request Method

● 2xx: 성공<br>
● 3xx: 리다이렉션<br>
● 4xx: 클라이언트 에러<br>
● 500: 서버 에러<br>

<br>

---

📚 참고 : <br>
[https://velog.io/@teddybearjung/HTTP-%EA%B5%AC%EC%A1%B0-%EB%B0%8F-%ED%95%B5%EC%8B%AC-%EC%9A%94%EC%86%8C](https://velog.io/@teddybearjung/HTTP-%EA%B5%AC%EC%A1%B0-%EB%B0%8F-%ED%95%B5%EC%8B%AC-%EC%9A%94%EC%86%8C)
<br>
[https://ryanclaire.blogspot.com/2020/10/HTTP-Overview.html](https://ryanclaire.blogspot.com/2020/10/HTTP-Overview.html)
<br>
[https://joshua1988.github.io/web-development/http-part1/](https://joshua1988.github.io/web-development/http-part1/)
<br>
[https://developer.mozilla.org/ko/docs/Web/HTTP/Overview](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)
<br>
[https://hyoveloper.tistory.com/entry/8-%EC%9B%B9%EC%9D%98-%EB%8F%99%EC%9E%91-HTTP-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C-%EC%9D%B4%ED%95%B4](https://hyoveloper.tistory.com/entry/8-%EC%9B%B9%EC%9D%98-%EB%8F%99%EC%9E%91-HTTP-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C-%EC%9D%B4%ED%95%B4)
<br>