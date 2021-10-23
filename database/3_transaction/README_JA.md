# 🔑 Transaction

<br>

## 📌トランザクションとは?

データベースの状態を変化させるために実行するジョブ単位又は一度に全て実行されなければならない一連の演算を意味します。

データベースの状態を変化させるということは、Select、Update、Insert、Deleteのような振る舞いを意味します。<br>
このようなトランザクションは状況に応じて複数作ることができ、CommitされたりRollbackされることがあります。

```
A銀行からB銀行に送金しようとすると出金と入金がそれぞれ一度ずつ発生するようになります。
送金しようとした瞬間に問題が発生し、入金できない状況が発生した場合、取引を成立させないことになります。
もしA銀行からの出金時に問題が発生した時に取引を成立させると、出金したお金が消えてしまうことになるからです。

A銀行から引き出されたお金がB銀行にちゃんと届いたら送金処理を完了させて、
もし到着しなければ、取引を成立させずにA銀行から引き出されたお金を払い戻すという処理をデータベースに代入してみることができます。
何らかのデータが変更、削除された時（A銀行からの出金）に問題が発生すると、Rollback（取引を成立させない）を
問題が発生しなかった場合は、Commit(送金処理)を施してデータを安定的に変更できます。
```

<br>

## 📌 TCL

TCLとはトランザクションを制御する言語。

● Commit:トランザクションが成功した後、変更された内容をデータベースに反映<br>
● Rollback: "commit" されていない変更された内容を取り消し、元の状態に戻す命令<br>
● Save Point:トランザクション内に"rollback"する場所である保存点を保存します。

<br>

## 📌 トランザクションの演算過程

> Success: Active -> Failed -> Aborted

> Fail: Active -> Partially Committed -> Committed

● Active:トランザクションが正常に終了した状態<br>
● Fail:トランザクションの実行にエラーが発生して中断した状態<br>
● Aborted:トランザクションが非正常的に終了し、Rollback演算を実行した状態<br>
● Partially Committed:トランザクションの最後の演算まで実行しましたが、Commit演算が実行される直前の状態<br>
● Committed:トランザクションが成功的に終了し、Commit演算を実行した後の状態<br>

<br>

## 📌トランザクションの性質

● Atomicity:トランザクションは、データベースにすべて反映orすべて反映されてはなりません。 1つでも間違いが発生したら、すべて取り消されるべきです。<br>
● Consistency:トランザクションが成功的に完了すると、常に一貫性がなければなりません。 つまり、システムが持っている固定要素は、トランザクションの実行前と後の状態が同じでなければなりません。<br>
● Isolation:2つ以上のトランザクションが同時に実行される場合、実行中のトランザクションが完全に完了するまで、他のトランザクションが演算に割り込むことができません。<br>
● Durability:トランザクションが成功裏に完了したら、結果は永久に反映されなければなりません。<br>

<br>

## 📌 UNDO, REDO

>REDO: やり直し

>UNDO: 元の状態に回す

●REDO: 以前の状態に戻った後、失敗が発生する前の過程をそのまま従うことを意味し、この過程を記録しなければならないが、これをlogといいます。<br>
●UNDO: トランザクションを元の状態に戻すことを意味します（RollBack、読み込み一貫性）<br>

```
復旧はUNDOを利用して復旧します。 つまりRollBackをします。
しかし、システム障害が発生するとUNDOデータもすべて削除され、REDOデータを利用して最後のCheckPoint(SavePoint)から障害までのBufferCacheが復旧される。
これが完了すると、UNDOを利用してCommitされていないデータをすべてRollBackすることで復旧を完了します。
結局、REDOがUNDOを復旧し、最終的にUNDOが復旧することになります。
```

<br>

---

📚 参考
<br>
[https://wonit.tistory.com/462](https://wonit.tistory.com/462)
<br>
[https://devuna.tistory.com/30](https://devuna.tistory.com/30)
<br>
[https://mozi.tistory.com/209](https://mozi.tistory.com/209)
<br>
[https://coding-factory.tistory.com/226](https://coding-factory.tistory.com/226)
<br>
[https://victorydntmd.tistory.com/130](https://victorydntmd.tistory.com/130)
<br>
[https://brownbears.tistory.com/181](https://brownbears.tistory.com/181)