# 🔑 HTTP

<br>

## 📌 What is HTTP?

HTTPは、HyperText Transfer Protocolの略字であり、ハイパーテキスト(HTML)文書を交換するために作られたprotocolです。<br>
つまり、ウェブ上でネットワークがサーバ間の通信をする際に、何らかの形式で通信しようと規定された通信構造のことです。

フロントアンドサーバーとクライアント間の通信、バックアンドとフロントアンドサーバー間での通信にも使用されます。<br>
HTTPはapplication layer、TCP/IPベースで構成されており、基本ポートは80番です。

<br>

## 📌 HTTP 通信方式

HTTPは、基本的にクライアントの要請(Request)サーバの応答(Response)構造からなり、server/clientモデルに従います。<br>
またStateless、要請があればその要請に対する応答をし、複数の要請と応答がつながっておらず、独立した要請と応答です。<br>

● 長所

クライアントとサーバが接続され続ける形態ではないため、クライアントとサーバ間の最大接続数よりも多くの要請応答を処理することができます。<br>
そのため不特定多数を対象とするサービスに適しているのです。

● 短所

一方的に接続を切断してしまうため、クライアントは以前の状況がわからない（Stateless）、情報を維持するためにCookieのような技術が登場しました。

<br>

## 📌 HTTP Request 構造

● Start line

> GET /user HTTP/1.1

Start lineは、3部分で構成されています。<br>

1.HTTP Method: actionsを定義する部分として、GET、POSTなどがあります。
2.Request target:送信されるURL
3.HTTP Version:バージョンで、1.0、1.1、2.0などがあります。

● Headers

リクエストに対する追加情報を含んでいる部分として、bodyの総丈、User-Agentなどが含まれています。<br>
key、value値となっており、Headersも大きく（general、request、entity）などに分かれています。

```
[General]
Request URL: https://stats.g.doubleclick.net/j/collect?t=dc&aip=1&_r=3&v=1&_v=j94&tid=UA-36116321-5&cid=1220086081.1633797781&jid=115805083&gjid=95221981&_gid=697110753.1635251935&_u=QACAAAAAAAAAAC~&z=1203385225
Request Method: POST
Status Code: 200
Remote Address: 74.125.23.157:443
Referrer Polic
...
```

【よく使用されるheader情報】<br>
Host:要請が送信されるtargetのhost url<br>
User-Agent:リクエストを送るクライアントに対する情報<br>
Accept:当該要請を受ける応答(response)タイプ<br>
Connection:Request後に接続を閉じるか維持するかを示します。 Close / Keep-Alive<br>
Content-Type:該当要請が送るメッセージ body のタイプとして、application/json、text/plain などがあります。<br>
Content-Length:メッセージbodyの長さ<br>

● Body

実際のメッセージの内容です。<br>

<br>

## 📌 HTTP Response 構造

● Start line

> HTTP/1.1 401 BadRequest

1. HTTP Version: バージョンです。
2. ステータスコード: 応答状態を示す数字コード
3. Status Text: 応答状態を説明します。

● Headers

Request Headerと基本的に同じであり、Responseで使用される特定のヘッダーがあるが、User-Agentの代わりにServerが入る。

● Body

Request bodyと同様、実際にデータを送信する必要がない場合はbodyが空く<br>

## 📌 URL

URL(Uniform Resource Locators)は、開発者でなくてもすでに私たちが使い慣れた用語です。また、サーバにリソースを要請するために入力する英文アドレス<br>

> https://www.google.com:443/path/resource?a=1&b=2

http: protocol<br>
www.google.com: host<br>
443: port<br>
path/resource: resource path<br>
query: a=1&b=2<br>

<br>

## 📌 HTTP Request Method

URLを利用するとサーバーに特定のデータを要求することができますが、要求するデータに特定の動作を実行したい場合はHTTP Request Methodを使用

● GET: 存在する資源への要望<br>
● POST: 新たな資源生成<br>
● PUT: 存在する資源への変更<br>
● DELETE: 存在する資源の削除<br>

● HEAD: サーバーヘッダー情報要請、ResponseBody返さない<br>
● OPTIONS: サーバのオプションを確認するためのリクエスト。 CORSで使用<br>

<br>

## 📌 HTTP Request Method

● 2xx: 成功<br>
● 3xx: Redirection<br>
● 4xx: クライアントエラー<br>
● 500: サーバエラー<br>

<br>

---

📚 参考 : <br>
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