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

HTTPの限界を克服し、リアルタイム(双方向通信)サービスの開発のために作られました。<br>
つまりWebSocket プロトコルは接続確立にHTTP を使用するが、その後の通信はWebSocket 独自のプロトコルからなります。

クライアントとサーバ間の双方向通信を行うためには、クライアントがサーバにHTTP Upgradeの要請を送らなければなりません。 これをWebSocket Handshakeといいます。

サーバーがコネクションをUpgradeする場合、HTTP 101応答をクライアントに送り、サーバーはHandshake が成功的に実行されたと判断すると、サーバー/クライアント間のコネクションをWebSocketプロトコルにUpgradeします。<br>
つまり、クライアント/サーバ間のHTTP 101応答が伝達されると、双方向通信が可能になる。

素早いアップデートが必要なチャット、株式、ビデオ関連分野でPolling方式と比較して、より適しているといえるでしょう。

## 📌 Socket.io

JavaScriptを利用して、ブラウザの種類を問わずリアルタイムでWebを実現できるようにした技術です。<br>
標準技術ではなくNode.jsモジュールでありオープンソースです。

WebSocket、Ajax Long Polling, Ajax Multipart Streaming、Flash Socket、JSONP pollingなどを1つのAPIとして抽象化したものです。<br>

例えば、ブラウザにFlash Socket対応バージョンがインストールされていればFlash Socketを使用し、なければAjax Long Polling方式を使用します。<br>
開発者が各技術を深く理解できなくても使用でき、JavaScriptを利用してブラウザの種類を問わずリアルタイムでWebを実現できるようにした技術


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