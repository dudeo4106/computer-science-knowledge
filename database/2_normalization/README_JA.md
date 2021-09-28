# 🔑 Normalization

<br>

## 📌 What is normalization?

● テーブル間で重複したデータを許容しません。<br>
● データを論理的に保存します。<br>
● 重複したデータを認めないことで完全性を維持でき、容量も減らすことができます。<br>

<br>

## 📌 第1正規化

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

## 📌 第2正規化

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

## 📌 第3正規化

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

## 📌 BCNF(Boyce and Codd Normal Form)

BCNFは、3次正規型をさらに強化したバージョンで、3次正規型では解決できない異常現象を解決できます。<br>
BCNFとは、3次正規形を満足しつつ、すべての決定者が候補鍵集合に属する正規形です。<br>
Trivial FDはYがXの部分集合の場合を指し、A→AやAB→Aのような場合を指します。<br>
[before normalization]候補キーは student, lecture で、ローを唯一区分できます。<br>
professorが決まると科目が決定されるためこのテーブルの決定者はprofessorです。<br>
しかしprofessorは候補キーではないのでBCNFを満足することができません。<br>
整理すると3次正規型に満足し、BCNFは満足しない場合、一般カラムが候補キーを決める場合です。<br>

* [before normalization] - lectures taken by students

  |student code|lecture|price|professor|
  |---|---|---|---|
  |1|math|300|messi|
  |1|science|200|kane|
  |2|science|200|kane|
  |3|english|150|cristiano|

* [after normalization] - lectures taught by professor

  |professor|lecture|
  |---|---|
  |messi|math|
  |kane|science|
  |cristiano|english|

* [after normalization] - lectures taken by students

  |student code|lecture|price|
  |---|---|---|
  |1|math|300|
  |1|science|200|
  |2|science|200|
  |2|english|150|

<br>

## 📌 第4正規化

第4正規型はリレーションRに多値従属を分離する過程です。<br>
A→>Bが存在する時、Rのすべての属性もAに関数従属であれば、リレーションRは第4正規形に属します。<br>
[before normalization]でscienceの教授はkane,messi教材コードがAA、ABなら[before normalization]には4つのチュープルが含まれなければなりません。<br>
このようにリレーションが構成されると、多くのデータの重複を招き、異常現象が発生します。<br>
したがって[beformalization]では科目ー>>教授コード｜教材コードが存在するので[afternormalization]のように無損失分解できます。

* [before normalization] - lectures taken by students

  |professor|lecture|book|
  |---|---|---|
  |messi|science|AA|
  |messi|science|AB|
  |messi|math|AC|
  |kane|science|AA|
  |kane|science|AD|
  |kane|english|AF|

* [after normalization] - lectures taught by professor

  |professor|lecture|
  |---|---|
  |messi|math|
  |messi|science|
  |kane|science|
  |kane|english|

* [after normalization] - lectures taken by students

  |lecture|book|
  |---|---|
  |science|AA|
  |science|AB|
  |science|AD|
  |math|AC|
  |english|AF|

<br>

## 📌 第5正規化

全ての調印従属がリレーションRの候補キーを介して成立するなら、第5正規形に属するといえます。<br>
例えば、A、B、CをリレーションRの部分集合としたとき、<br>
リレーションRにおいて、A、B、Cをプロジェクションしたものと調印したものと元のリレーションRが同じなら、調印従属を満足させることができます。<br>

* [relation R]

  |A|B|C|
  |---|---|---|
  |a1|b1|c2|
  |a1|b2|c1|
  |a2|b1|c1|
  |a1|b1|c1|

* [projection]

  |A|B| |B|C| |C|A|
  |---|---|---|---|---|---|---|---|
  |a1|b1| |b1|c2| |c2|c1|
  |a1|b2| |b2|c1| |c1|c1|
  |a2|b1| |a1|c1| |c1|c2|

* [A,B projection join B,C projection]

  |A|B|C|
  |---|---|---|
  |a1|b1|c2|
  |a1|b1|c1|
  |a1|b2|c1|
  |a2|b1|c2|
  |a2|b1|c1|

* [A,B projection join B,C projection join C,A]

  |A|B|C|
  |---|---|---|
  |a1|b1|c2|
  |a1|b2|c1|
  |a2|b1|c1|
  |a1|b1|c1|

<br>

## 📌 DeNormalization

正規化によって分解されたリレーションにおいて情報を得るためには、joinを使用しなければなりません。<br>
経路が遠い、多くのjoinを使用すると、応答速度が落ちます。<br>
整理すると正規化には違反するが、性能向上のためにテーブルを結合させる場合を逆正規化といいます。<br>

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
