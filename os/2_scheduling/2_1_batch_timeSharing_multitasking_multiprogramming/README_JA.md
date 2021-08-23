# 🔑 batch-processing, time-sharing system, multi-tasking, multi-programming

<br>

## 📌 batch-processing

● 一括処理·配置処理と呼びます<br>
● コンピュータプログラム実行リクエスト順に順次プログラムを実行する方式<br>
● 一度に登録された複数のプログラムを順次実行可能 <br>
<br>

## 📌 batch-processing과 time-sharing system / multi-programming

● 複数のプログラムを順次実行できるようにしたいと思います。
```
○ あるプログラムは実行がとても時間がかかるので、他のプログラムが実行するのに時間を長くお待ちいただく必要があります。
○ 私はMP3音楽を聴きながら、文書を作成したいです！（同時に複数アプリケーションを実行）
○ 複数のユーザーが同時に1つのパソコンを使用する場合はですね？（複数ユーザー対応）
```
このような理由から、multi-programmingtime-sharing systemが登場します。

<br>

## 📌 time-sharing system

● マルチユーザー対応のために応答時間を最小化するシステム<br>

<br>

## 📌 multi-tasking

● 単一CPUで、複数のアプリケーションが同時に実行されているように見えるようにするシステム
```
○ 私は音楽を聴きながら、文書を作成します。
```

<br>

## 📌 実際のmulti-tasking

● 1000ミリ秒（ms）=1秒<br>
● 10 ~ 20ms単位でも実行応用プログラムが変わります<br>
● ユーザーに同時に実行されているように見えます<br>

<br>

## 📌 multi-taskingとmulti-processing

● multi-tasking:  単一CPU<br>
● multi-processing:複数のCPUに1つのプログラムを並列して実行速度を極大化させるシステム<br>

<br>

## 📌 multi-programming

● 最大限CPUを多く活用するようにするシステムです
```
○ 時間に対してCPUの活用度を高めることが狙いです
○ アプリケーションを短時間で実行完了させることができます。
```
● アプリケーションは完全にCPUを使用するよりも、異なる作業を途中で必要とする場合が多いです。
```
○ アプリケーションが実行されてからファイルを読みます。
○ アプリケーションが実行されてからプリンティングをします。
```

<br>

### 📌 まとめ
● time-sharing system: 多重ユーザー対応、パソコン応答時間を最小化するシステム<br>
● multi-tasking: 単一CPUで複数のアプリケーションを同時に実行しているように見せるシステム<br>
● multi-processing: 複数のCPUで1つのアプリケーションを並列に実行させることで、実行速度を上げる手法<br>
● multi-programming: 最大限CPUを一定時間当たり多く活用するシステム（実際にはtime-sharing system、multi-programming、multi-taskingが類似した意味で通用）
```
○ 様々な応用プログラムを実行できるようにします
○ アプリケーションが同時に実行されているように見えるようにします
○ CPUを休まず応用プログラムを実行するようにして、短時間で応用プログラムを実行完了するようにします。
○ パソコン応答時間も短くしているので、マルチプレイヤーにも対応します
```


<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)