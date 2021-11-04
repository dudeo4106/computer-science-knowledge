# 🔑 Real-time two-way communication

<br>

## 📌 Polling

クライアントがサーバからHTTP Requestを周期的に要請して(Ajax)、サーバが応答する方法<br>
ヘッダーが重いプロトコルであるHTTP要請を周期的に行うため、クライアントの数が増加するとサーバの負担が大きくなります。<br>
また、要請/応答後は接続が切れるため、要請するたびにいつも接続を結ぶ過程が必要なため、多くの費用が費やされます。<br>
要請に対するサーバー負担が大きくなくて、リアルタイムのメッセージ伝達が重要ではないサービスに向いている、しかし要請周期が短く設定されてもサーバーのステータスが頻繁に変更されなければ不必要なトラフィックが発生します。

## 📌 Long Polling

クライアントがサーバにHTTP Requestを要請すると、サーバはタイムアウトになるまで待ち、途中に送信するデータがあれば応答を送る方法<br>
Pollingのように不必要な要請に応答し続けるのではないため、コネクション過程でコストが減少します。<br>
クライアントの数が増加すると、応答数も増加するため、Polling と大差はありません。<br>
ただし、リアルタイムのメッセージ伝達は重要ではあるが、サーバーのステータス変更が頻繁に発生しないサービスには適している可能性があります。

## 📌 Streaming

サーバでイベントが発生した時に応答してくれますが、応答を完了させずに続けて接続を維持する方法です。<br>
PollingやLong Pollingとは異なり、クライアントとサーバ間の接続を切らずにメッセージを送信しますが、<br>
接続を長く結んでいる場合、接続の有効性管理などの負担が発生します。<br>
通常、特定の時間を周期に接続を再設定するようにします。

## 📌 WebSocket

## 📌 Socket.io

<br>

---

📚 参考 : <br>
[https://valuefactory.tistory.com/263](https://valuefactory.tistory.com/263)
<br>
[https://lkhlkh23.tistory.com/121](https://lkhlkh23.tistory.com/121)
<br>
[https://velog.io/@nameunzz/Polling-vs-Websocket](https://velog.io/@nameunzz/Polling-vs-Websocket)
<br>
[https://winapp81.tistory.com/330](https://winapp81.tistory.com/330)
<br>
[https://velog.io/@jennyfromdeblock/%E3%85%87](https://velog.io/@jennyfromdeblock/%E3%85%87)