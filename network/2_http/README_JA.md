# ð HTTP

<br>

## ð What is HTTP?

HTTPã¯ãHyperText Transfer Protocolã®ç¥å­ã§ããããã¤ãã¼ãã­ã¹ã(HTML)ææ¸ãäº¤æããããã«ä½ãããprotocolã§ãã<br>
ã¤ã¾ããã¦ã§ãä¸ã§ãããã¯ã¼ã¯ããµã¼ãéã®éä¿¡ãããéã«ãä½ããã®å½¢å¼ã§éä¿¡ãããã¨è¦å®ãããéä¿¡æ§é ã®ãã¨ã§ãã

ãã­ã³ãã¢ã³ããµã¼ãã¼ã¨ã¯ã©ã¤ã¢ã³ãéã®éä¿¡ãããã¯ã¢ã³ãã¨ãã­ã³ãã¢ã³ããµã¼ãã¼éã§ã®éä¿¡ã«ãä½¿ç¨ããã¾ãã<br>
HTTPã¯application layerãTCP/IPãã¼ã¹ã§æ§æããã¦ãããåºæ¬ãã¼ãã¯80çªã§ãã

<br>

## ð HTTP éä¿¡æ¹å¼

HTTPã¯ãåºæ¬çã«ã¯ã©ã¤ã¢ã³ãã®è¦è«(Request)ãµã¼ãã®å¿ç­(Response)æ§é ãããªããserver/clientã¢ãã«ã«å¾ãã¾ãã<br>
ã¾ãStatelessãè¦è«ãããã°ãã®è¦è«ã«å¯¾ããå¿ç­ãããè¤æ°ã®è¦è«ã¨å¿ç­ãã¤ãªãã£ã¦ããããç¬ç«ããè¦è«ã¨å¿ç­ã§ãã<br>

â é·æ

ã¯ã©ã¤ã¢ã³ãã¨ãµã¼ããæ¥ç¶ããç¶ããå½¢æã§ã¯ãªããããã¯ã©ã¤ã¢ã³ãã¨ãµã¼ãéã®æå¤§æ¥ç¶æ°ãããå¤ãã®è¦è«å¿ç­ãå¦çãããã¨ãã§ãã¾ãã<br>
ãã®ããä¸ç¹å®å¤æ°ãå¯¾è±¡ã¨ãããµã¼ãã¹ã«é©ãã¦ããã®ã§ãã

â ç­æ

ä¸æ¹çã«æ¥ç¶ãåæ­ãã¦ãã¾ããããã¯ã©ã¤ã¢ã³ãã¯ä»¥åã®ç¶æ³ãããããªãï¼Statelessï¼ãæå ±ãç¶­æããããã«Cookieã®ãããªæè¡ãç»å ´ãã¾ããã

<br>

## ð HTTP Request æ§é 

â Start line

> GET /user HTTP/1.1

Start lineã¯ã3é¨åã§æ§æããã¦ãã¾ãã<br>

1.HTTP Method: actionsãå®ç¾©ããé¨åã¨ãã¦ãGETãPOSTãªã©ãããã¾ãã
2.Request target:éä¿¡ãããURL
3.HTTP Version:ãã¼ã¸ã§ã³ã§ã1.0ã1.1ã2.0ãªã©ãããã¾ãã

â Headers

ãªã¯ã¨ã¹ãã«å¯¾ããè¿½å æå ±ãå«ãã§ããé¨åã¨ãã¦ãbodyã®ç·ä¸ãUser-Agentãªã©ãå«ã¾ãã¦ãã¾ãã<br>
keyãvalueå¤ã¨ãªã£ã¦ãããHeadersãå¤§ããï¼generalãrequestãentityï¼ãªã©ã«åããã¦ãã¾ãã

```
[General]
Request URL: https://stats.g.doubleclick.net/j/collect?t=dc&aip=1&_r=3&v=1&_v=j94&tid=UA-36116321-5&cid=1220086081.1633797781&jid=115805083&gjid=95221981&_gid=697110753.1635251935&_u=QACAAAAAAAAAAC~&z=1203385225
Request Method: POST
Status Code: 200
Remote Address: 74.125.23.157:443
Referrer Polic
...
```

ãããä½¿ç¨ãããheaderæå ±ã<br>
Host:è¦è«ãéä¿¡ãããtargetã®host url<br>
User-Agent:ãªã¯ã¨ã¹ããéãã¯ã©ã¤ã¢ã³ãã«å¯¾ããæå ±<br>
Accept:å½è©²è¦è«ãåããå¿ç­(response)ã¿ã¤ã<br>
Connection:Requestå¾ã«æ¥ç¶ãéãããç¶­æããããç¤ºãã¾ãã Close / Keep-Alive<br>
Content-Type:è©²å½è¦è«ãéãã¡ãã»ã¼ã¸ body ã®ã¿ã¤ãã¨ãã¦ãapplication/jsonãtext/plain ãªã©ãããã¾ãã<br>
Content-Length:ã¡ãã»ã¼ã¸bodyã®é·ã<br>

â Body

å®éã®ã¡ãã»ã¼ã¸ã®åå®¹ã§ãã<br>

<br>

## ð HTTP Response æ§é 

â Start line

> HTTP/1.1 401 BadRequest

1. HTTP Version: ãã¼ã¸ã§ã³ã§ãã
2. ã¹ãã¼ã¿ã¹ã³ã¼ã: å¿ç­ç¶æãç¤ºãæ°å­ã³ã¼ã
3. Status Text: å¿ç­ç¶æãèª¬æãã¾ãã

â Headers

Request Headerã¨åºæ¬çã«åãã§ãããResponseã§ä½¿ç¨ãããç¹å®ã®ãããã¼ãããããUser-Agentã®ä»£ããã«Serverãå¥ãã

â Body

Request bodyã¨åæ§ãå®éã«ãã¼ã¿ãéä¿¡ããå¿è¦ããªãå ´åã¯bodyãç©ºã<br>

## ð URL

URL(Uniform Resource Locators)ã¯ãéçºèã§ãªãã¦ããã§ã«ç§ãã¡ãä½¿ãæ£ããç¨èªã§ããã¾ãããµã¼ãã«ãªã½ã¼ã¹ãè¦è«ããããã«å¥åããè±æã¢ãã¬ã¹<br>

> https://www.google.com:443/path/resource?a=1&b=2

http: protocol<br>
www.google.com: host<br>
443: port<br>
path/resource: resource path<br>
query: a=1&b=2<br>

<br>

## ð HTTP Request Method

URLãå©ç¨ããã¨ãµã¼ãã¼ã«ç¹å®ã®ãã¼ã¿ãè¦æ±ãããã¨ãã§ãã¾ãããè¦æ±ãããã¼ã¿ã«ç¹å®ã®åä½ãå®è¡ãããå ´åã¯HTTP Request Methodãä½¿ç¨

â GET: å­å¨ããè³æºã¸ã®è¦æ<br>
â POST: æ°ããªè³æºçæ<br>
â PUT: å­å¨ããè³æºã¸ã®å¤æ´<br>
â DELETE: å­å¨ããè³æºã®åé¤<br>

â HEAD: ãµã¼ãã¼ãããã¼æå ±è¦è«ãResponseBodyè¿ããªã<br>
â OPTIONS: ãµã¼ãã®ãªãã·ã§ã³ãç¢ºèªããããã®ãªã¯ã¨ã¹ãã CORSã§ä½¿ç¨<br>

<br>

## ð HTTP Request Method

â 2xx: æå<br>
â 3xx: Redirection<br>
â 4xx: ã¯ã©ã¤ã¢ã³ãã¨ã©ã¼<br>
â 500: ãµã¼ãã¨ã©ã¼<br>

<br>

---

ð åè : <br>
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