# 🔑 Context Switching

<br>

## 📌 Context Switchingとは

● CPUに実行するプロセスを入れ替える技術です

<br>

## 📌 Context Switching Example

● 手順①: 実行中止するプロセス情報を該当プロセスのPCBにアップデートして、メインメモリに保存<br>
● 手順②: 次に実行されるプロセス情報のメインメモリにある該当PCB（PC、SP）情報を、CPUのレジスタに入れて実行します。<br>

> dispatch: ready状態のプロセスをrunning状態に置き換えます。

> 実際にはとても短い時間（ms）単位で、プロセススイッチングが起こります。

<br>

### 📌 まとめ

● プロセス状態情報をPCBからCPUにロードして、実行します。

<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)