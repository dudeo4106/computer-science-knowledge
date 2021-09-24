# 🔑 Normalization

<br>

## 📌 What is normalization?

● テーブル間で重複したデータを許容しません。<br>
● データを論理的に保存します。<br>
● 重複したデータを認めないことで完全性を維持でき、容量も減らすことができます。<br>

<br>

### 📌 第1正規化

あるrelationに属する全てのdomainが原子値のみとなっています。<br>
また、すべてのattributeに繰り返されるグループが現れず、デフォルトキーを使用して関連データの各集合を固有に識別できます。
<br>

* [before normalization]

  |student code|name|lecture|
  |---|---|---|
  |1|messi|math, science|
  |2|kane|science, english|

* [after normalization]

  |student code|name|lecture|
  |---|---|---|
  |1|messi|math|
  |1|messi|science|
  |2|kane|science|
  |2|kane|english|

<br>

### 📌 第2正規化

第2正規型は、テーブルのすべてのカラムが完全関数的従属を満足し、基本キーの中に特定のカラムにのみ従属されたカラム（部分的従属）があってはなりません。<br>
以下の[beforenormalization]では、デフォルトキーをstudent、lecture の2つで確認することができます。<br>
しかし、nameの場合、デフォルトキーのうちstudentにのみ従属されているので、studentカラムが分かればname分かるので、nameを2回入れるのは不要だと言えます。
<br>

* [before normalization] - students

  |student code|name|lecture|
  |---|---|---|
  |1|messi|math|
  |1|messi|science|
  |2|kane|science|
  |2|kane|english|

* [after normalization] - students

  |student code|name|
  |---|---|
  |1|messi|
  |2|kane|

* [after normalization] - lectures

  |student code|lecture|
  |---|---|
  |1|math|
  |1|science|
  |2|science|
  |2|english|

<br>

### 📌 第3正規化

第3正規形は、第2正規化を進めたテーブルに対して移行的従属をなくすようにテーブルを分解するものです。<br>
移行的従属とは、A->B、B->Cの成立時にA→Cが成立することを意味します。<br>
[beforenormalization]で1番の学生がmathという授業を受けずにenglishに変更されたと仮定しましょう。<br>
この学生は、englishという授業を150に聞いて、勿論受講料をもう一度変更できますが、このような煩わしさを解決するために第3正規化をしなければならないのです。
<br>

* [before normalization] - lectures taken by students

  |student code|lecture|price|
  |---|---|---|
  |1|math|300|
  |1|science|200|
  |2|science|200|
  |2|english|150|

* [after normalization] - lectures taken by students

  |student code|lecture|
  |---|---|
  |1|math|
  |1|science|
  |2|science|
  |2|english|

* [after normalization] - price per lecture

  |lecture|price|
  |---|---|
  |math|300|
  |science|200|
  |english|150|


<br>

---

📚 参考
<br>
[https://mangkyu.tistory.com/110](https://mangkyu.tistory.com/110)
<br>
[https://3months.tistory.com/193](https://3months.tistory.com/193)
<br>
[https://wkdtjsgur100.github.io/database-normalization/](https://wkdtjsgur100.github.io/database-normalization/)
