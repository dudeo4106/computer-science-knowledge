# ๐ HTTP

<br>

## ๐ What is HTTP?

HTTP๋ HyperText Transfer Protocol์ ์ฝ์๋ฉฐ ํ์ดํผํ์คํธ(HTML) ๋ฌธ์๋ฅผ ๊ตํํ๊ธฐ ์ํด ๋ง๋ค์ด์ง protocol์ด๋ค<br>
์ฆ ์น์์์ ๋คํธ์ํฌ๋ก ์๋ฒ๋ผ๋ฆฌ ํต์ ์ ํ  ๋ ์ด๋ ํ ํ์์ผ๋ก ํต์ ์ ํ์๊ณ  ๊ท์ ํด ๋์ ํต์ ๊ตฌ์กฐ์ด๋ค.

ํ๋ก ํธ์ค๋ ์๋ฒ์ ํด๋ผ์ด์ธํธ๊ฐ ํต์ , ๋ฐฑ์ค๋์ ํ๋ก ํธ์ค๋ ์๋ฒ๊ฐ์์์ ํต์ ์๋ ์ฌ์ฉ๋๋ค.<br>
HTTP๋ application layer, TCP/IP ๊ธฐ๋ฐ์ผ๋ก ๋์ด์์ผ๋ฉฐ ๊ธฐ๋ณธ ํฌํธ๋ 80๋ฒ์ด๋ค.

<br>

## ๐ HTTP ํต์ ๋ฐฉ์

HTTP๋ ๊ธฐ๋ณธ์ ์ผ๋ก ํด๋ผ์ด์ธํธ์ ์์ฒญ(Request) ์๋ฒ์ ์๋ต(Response) ๊ตฌ์กฐ๋ก ์ด๋ฃจ์ด์ ธ์๊ณ  server/client ๋ชจ๋ธ์ ๋ฐ๋ฅธ๋ค.<br>
๋ํ Stateless, ์์ฒญ์ด์ค๋ฉด ๊ทธ ์์ฒญ์ ๋ํ ์๋ต์ ํ์ง ์ฌ๋ฌ ์์ฒญ๊ณผ ์๋ต์ด ์ฐ๊ฒฐ๋์ด์์ง ์๊ณ  ๋๋ฆฝ์ ์ธ ์์ฒญ๊ณผ ์๋ต์ด๋ค.<br>

โ ์ฅ์ 

ํด๋ผ์ด์ธํธ์ ์๋ฒ๊ฐ ๊ณ์ ์ฐ๊ฒฐ๋ ํํ๊ฐ ์๋๊ธฐ ๋๋ฌธ์ ํด๋ผ์ด์ธํธ์ ์๋ฒ๊ฐ์ ์ต๋ ์ฐ๊ฒฐ ์ ๋ณด๋ค ํจ์ฌ ๋ง์ ์์ฒญ/์๋ต์ ์ฒ๋ฆฌํ  ์ ์๋ค.<br>
๊ทธ๋ ๊ธฐ์ ๋ถํน์  ๋ค์๋ฅผ ๋์์ผ๋ก ํ๋ ์๋น์ค์ ์ ํฉํ  ์ ์๋ค.

โ ๋จ์ 

์ผ๋ฐฉ์ ์ผ๋ก ์ฐ๊ฒฐ์ ๋์ด๋ฒ๋ฆฌ๊ธฐ ๋๋ฌธ์, ํด๋ผ์ด์ธํธ๋ ์ด์  ์ํฉ์ ์ ์๊ฐ ์์ด(Stateless) ์ ๋ณด๋ฅผ ์ ์งํ๊ธฐ ์ํด Cookie ๊ฐ์ ๊ธฐ์ ์ด ๋ฑ์ฅํ์๋ค. 

<br>

## ๐ HTTP Request ๊ตฌ์กฐ

โ Start line

> GET /user HTTP/1.1

Start line์ 3๋ถ๋ถ์ผ๋ก ๊ตฌ์ฑ๋์ด ์๋ค.<br>

1. HTTP Method: actions์ ์ ์ํ๋ ๋ถ๋ถ์ผ๋ก GET, POST๋ฑ์ด์๋ค.
2. Request target: ์ ์ก๋๋ URL
3. HTTP Version: ๋ฒ์ ์ผ๋ก 1.0, 1.1, 2.0 ๋ฑ์ด์๋ค.

โ Headers

Request์ ๋ํ ์ถ๊ฐ ์ ๋ณด๋ฅผ ๋ด๊ณ  ์๋ ๋ถ๋ถ์ผ๋ก body์ ์ด๊ธธ์ด, User-Agent๋ฑ์ด ๋ด๊ฒจ ์๋ค.<br>
key, value๊ฐ์ผ๋ก ๋์ด์๊ณ  Headers๋ ํฌ๊ฒ (general, request, entity)๋ฑ์ผ๋ก ๋๋์ด์๋ค.

```
[General]
Request URL: https://stats.g.doubleclick.net/j/collect?t=dc&aip=1&_r=3&v=1&_v=j94&tid=UA-36116321-5&cid=1220086081.1633797781&jid=115805083&gjid=95221981&_gid=697110753.1635251935&_u=QACAAAAAAAAAAC~&z=1203385225
Request Method: POST
Status Code: 200 
Remote Address: 74.125.23.157:443
Referrer Polic
...
```

[์์ฃผ ์ฌ์ฉ๋๋ header ์ ๋ณด]<br>
Host: ์์ฒญ์ด ์ ์ก๋๋ target์ host url<br>
User-Agent: ์์ฒญ์ ๋ณด๋ด๋ ํด๋ผ์ด์ธํธ์ ๋ํ ์ ๋ณด<br>
Accept: ํด๋น ์์ฒญ์ด ๋ฐ์ ์ ์๋ ์๋ต(response) ํ์<br>
Connection: Request ํ ์ฐ๊ฒฐ์ ๋ซ์ ๊ฒ์ธ์ง ์ ์งํ  ๊ฒ์ธ์ง๋ฅผ ๋ํ๋ธ๋ค. Close / Keep-Alive<br>
Content-Type: ํด๋น ์์ฒญ์ด ๋ณด๋ด๋ ๋ฉ์ธ์ง body์ ํ์์ผ๋ก application/json, text/plain๋ฑ์ด ์๋ค.<br>
Content-Length: ๋ฉ์ธ์ง body์ ๊ธธ์ด<br>

โ Body

์ค์  ๋ฉ์ธ์ง์ ๋ด์ฉ์ด๋ค.<br>

<br>

## ๐ HTTP Response ๊ตฌ์กฐ

โ Start line

> HTTP/1.1 401 BadRequest

1. HTTP Version: ๋ฒ์ 
2. Status code: ์๋ต ์ํ๋ฅผ ๋ํ๋ด๋ ์ซ์ ์ฝ๋
3. Status Text: ์๋ต ์ํ๋ฅผ ์ค๋ชํด ์ฃผ๋ ๋ถ๋ถ

โ Headers

Request Header์ ๊ธฐ๋ณธ์ ์ผ๋ก ๋์ผํ๋ฉฐ, Response์์ ์ฌ์ฉ๋๋ ํน์  Header๊ฐ ์๋๋ฐ User-Agent ๋์ ์ Server๊ฐ ๋ค์ด๊ฐ๋ค.

โ Body

Request body์ ๋ง์ฐฌ๊ฐ์ง๋ก ์ค์  ๋ฐ์ดํฐ ์ ์ก์ด ํ์์๋ ๊ฒฝ์ฐ body๊ฐ ๋น๋ค<br>

<br>

## ๐ URL

URL(Uniform Resource Locators)์ ๊ฐ๋ฐ์๊ฐ ์๋๋๋ผ๋ ์ด๋ฏธ ์ฐ๋ฆฌ์๊ฒ ์ต์ํ ์ฉ์ด์ด๋ฉฐ, ์๋ฒ์ ์์์ ์์ฒญํ๊ธฐ ์ํด ์๋ ฅํ๋ ์๋ฌธ์ฃผ์<br>

> https://www.google.com:443/path/resource?a=1&b=2

http: protocol<br>
www.google.com: host<br>
443: port<br>
path/resource: resource path<br>
query: a=1&b=2<br>

<br>

## ๐ HTTP Request Method

URL๋ฅผ ์ด์ฉํ๋ฉด ์๋ฒ์ ํน์  ๋ฐ์ดํฐ๋ฅผ ์์ฒญํ  ์ ์๋๋ฐ ์์ฒญํ๋ ๋ฐ์ดํฐ์ ํน์  ๋์์ ์ํํ๊ณ  ์ถ์ผ๋ฉด HTTP Request Method๋ฅผ ์ฌ์ฉ

โ GET: ์กด์ฌํ๋ ์์์ ๋ํ ์์ฒญ<br>
โ POST: ์๋ก์ด ์์ ์์ฑ<br>
โ PUT: ์กด์ฌํ๋ ์์์ ๋ํ ๋ณ๊ฒฝ<br>
โ DELETE: ์กด์ฌํ๋ ์์์ ๋ํ ์ญ์ <br>

โ HEAD: ์๋ฒ ํค๋์ ๋ณด ์์ฒญ, ResponseBody ๋ฐํํ์ง ์์<br>
โ OPTIONS: ์๋ฒ ์ต์๋ค์ ํ์ธํ๊ธฐ ์ํ ์์ฒญ. CORS์์ ์ฌ์ฉ<br>

<br>

## ๐ HTTP Request Method

โ 2xx: ์ฑ๊ณต<br>
โ 3xx: ๋ฆฌ๋ค์ด๋ ์<br>
โ 4xx: ํด๋ผ์ด์ธํธ ์๋ฌ<br>
โ 500: ์๋ฒ ์๋ฌ<br>

<br>

---

๐ ์ฐธ๊ณ  : <br>
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