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

---

📚 参考
<br>
[https://nesoy.github.io/articles/2019-05/Database-Transaction-isolation](https://nesoy.github.io/articles/2019-05/Database-Transaction-isolation)
<br>
