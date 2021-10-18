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

---

📚 参考
<br>
[https://mangkyu.tistory.com/110](https://mangkyu.tistory.com/110)
<br>
[https://3months.tistory.com/193](https://3months.tistory.com/193)
<br>
[https://wkdtjsgur100.github.io/database-normalization/](https://wkdtjsgur100.github.io/database-normalization/)
<br>
[https://yaboong.github.io/database/2018/03/10/database-normalization-2/](https://yaboong.github.io/database/2018/03/10/database-normalization-2/)
<br>
[https://minimax95.tistory.com/entry/%EC%A0%95%EA%B7%9C%ED%99%94Normalization-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%A0%95%EA%B7%9C%ED%99%94-%EA%B3%BC%EC%A0%954NF-5NF](https://minimax95.tistory.com/entry/%EC%A0%95%EA%B7%9C%ED%99%94Normalization-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%A0%95%EA%B7%9C%ED%99%94-%EA%B3%BC%EC%A0%954NF-5NF)
