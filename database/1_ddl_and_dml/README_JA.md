# 🔑 DDL and DML

<br>

## 📌 SQL概念

● 国際標準データベース言語であり、RDBをサポートする言語として採用<br>
● 関係代数と関係解析を基礎とした混合データ言語<br>

|DDL<br>(Data Define Language)|DML<br>(Data Manipulation Language)|DCL<br>(Data Control Language)|
|---|---|---|
|create<br>alter<br>drop<br>truncate|select<br>insert<br>delete<br>update|commit<br>rollback<br>grant<br>savepoint|

<br>

## 📌 DDL

● スキーマドメインテーブルビューインデックスを定義したり変更、削除する際に使用する言語<br>
● データベース管理者もしくは設計者が使用<br>
● schemaとは? データベース構造と制約条件に関する全般的な明細を記述し、データ個体、関係および制約条件などに関して全般的に定義したものです。
```
○ create: スキーマ、テーブル、ビューなどを定義します
○ alter: テーブルの定義を変更します
○ drop: スキーマ、テーブル、ビューなどを削除します
○ truncate: テーブルが維持された状態でデータのみ削除（テーブル容量、インデックスもすべて削除され、削除後に戻すことができません）
```

<br>

## 📌 DML

● ユーザー指定のデータを処理する際に使用（入力、修正、削除、検索）<br>
● データベースユーザーと管理システム間のインタフェース制御<br>
● tupleとは？ table（relation）を構成するそれぞれの行を意味します。 また、これをレコードと呼びますが、より公式的にチュープルといいます。
```
○ select:テーブルで条件に合うチュープルを検索します。
○ insert:テーブルから新しいチュープルを挿入します
○ delete:テーブルから条件に合うチュープルを削除します
○ update:テーブルで条件に合ったチュープルの内容を変更します
```

<br>

## 📌 DCL

● データのセキュリティ·完全性·回復·並行制御などを定義するのに使用される言語<br>
● データ管理目的<br>
```
○ commit:トランザクションが成功した後、変更された内容をデータベースに反映します
○ rollback: "commit"されていない変更内容を取り消し、元の状態に戻す命令
○ grant:データベース管理者がユーザーに権限を付与します
○ revoke:データベース管理者がユーザーに対して権限をキャンセルします
○ savepoint:トランザクション内に"rollback"する場所である保存点を保存します。
```

<br>

---

📚 参考
<br>
[https://rosypark.tistory.com/301](https://rosypark.tistory.com/301)
<br>
[https://sung0woo.tistory.com/68](https://sung0woo.tistory.com/68)
<br>
[https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=potter777777&logNo=220740559802](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=potter777777&logNo=220740559802)