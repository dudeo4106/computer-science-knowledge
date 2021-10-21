# 🔑 Transaction Isolation Level

<br>

## 📌 What is transaction isolation level?

トランザクション隔離水準とは、同時に複数のトランザクションが処理される際に、特定のトランザクションが他のトランザクションで変更し、又はデータを照会できるように許可するかを決定すること<br>
データベースは、ACIDの特徴のようにトランザクションが独立的に実行されるようにLockingを行い、トランザクションの関与を防ぎます。<br>

しかし、無条件にLockingをしてトランザクションを順序どおりに処理するようにすると、性能が低下し、性能のためLockingを解除すると、間違った値が処理されてしまう可能性があります。

そのため効率的なLocking方法が必要です。

<br>

## 📌 What is Lock?

Lockとは、トランザクション処理の順次性を保障するための方法であり、一つのトランザクションが完璧に終了するまで、データの変更、削除、照会を防止します。

<br>

## 📌 Shared Lock and Exclusive Lock

> Shared Lock

データを読み込むときに使用される Lockであり、Shared LockはShared Lock同士で同時アクセスが可能です。<br>
つまり、1つのデータを読み込むことですから、複数のユーザが同時に可能ですが、Shared Lockに設定されたデータはExclusive Lockを使用することはできない。

> Exclusive Lock

データを変更するときに使用され、トランザクションが終了するまで維持されます。<br>
Exclusive Lockが解除されるまで、他のトランザクション(読み込み含む)は、該当リソースにアクセスできず、他のトランザクションが実行されているデータについては、一緒にLockを設定することはできません。

<br>

## 📌 Lock Level

● Database: データベース全体にLockを設定することを意味し、1つのセッションだけがデータにアクセスできます。<br>
● File: 実際にデータが使われる物理的なリポジトリにLockを設定することを意味<br>
● Table: TableレベルのLock設定を意味し、テーブルのすべての行をアップデートするなどの、テーブル全体に影響を与える変更を行うときに主に使用されます。<br>
● Page、Block: ファイルの一部であるページとBlockに基づいてLockを設定することを意味 <br>
● Column: Columnを基準にLockを設定することを意味し、Lock設定、そして解除時に多くのリソースが必要なため、一般的に使用しない<br>
● Row: 最も一般的に使用されているRowレベルのLockであり、DMLに対するLock<br>

<br>

## 📌 Blocking

ブロッキングは、Lock(Exclusive - Exclusive, Exclusive - Shared)の競合が発生して、特定のTransactionが作業を実行できずに止まった状態のことをいいます。<br>
Shared Lock同士はブロッキングが発生しないが、Exclusive Lockはブロッキングを発生させます。<br>
ブロッキングを解消するためには、以前のトランザクションがCommit or RollBackされなければならず、このような競合は性能を悪化させるために最小化しなければなりません。<br>

解消の仕方
- 1つのトランザクションの長さを長くしすぎないようにします。
- 同じデータを更新するトランザクションが同時に実行されないようにする必要があります。
- Isolation Levelを不必要に上向調整せずに、クエリー遂行時間を短くします。

<br>

## 📌 DeadLock

プロセスがリソースを得られずに次の処理ができない状態で、システム的に限られたリソースを複数箇所で使用しようとする時に発生<br>

発生する状況では、マルチプログラミング環境で限られた資源を使用しようと競争する状況が発生する場合<br>
あるプロセスが支援を要請した時その時刻にそのリソースを使用できない状況が発生、プロセスが待機状態になります。<br>
待機状態に入ったプロセスが実行状態に変更できないときDeadLockといいます。

* 詳細については、DeadLockパートにて再扱いすることにします。

---

📚 参考
<br>
[https://nesoy.github.io/articles/2019-05/Database-Transaction-isolation](https://nesoy.github.io/articles/2019-05/Database-Transaction-isolation)
<br>
[https://dar0m.tistory.com/225](https://dar0m.tistory.com/225)
<br>
[https://sabarada.tistory.com/121](https://sabarada.tistory.com/121)
<br>
[https://doooyeon.github.io/2018/09/29/transaction-isolation-level.html](https://doooyeon.github.io/2018/09/29/transaction-isolation-level.html)
<br>
[https://jwprogramming.tistory.com/12](https://jwprogramming.tistory.com/12)
<br>
