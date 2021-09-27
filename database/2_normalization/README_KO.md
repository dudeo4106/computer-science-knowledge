# 🔑 Normalization

<br>

## 📌 What is normalization?

● 테이블 간에 중복된 데이터를 허용하지 않는다<br>
● 데이터를 논리적으로 저장한다.<br>
● 중복된 데이터를 허용하지 않음으로써 무결성을 유지할 수 있으며 용량 역시 줄일 수 있다.<br>

<br>

## 📌 제1 정규화

어떤 relation에 속한 모든 domain이 원자값만으로 되어 있다.<br>
또한 모든 attribute에 반복되는 그룹이 나타나지 않으며 기본 키를 사용하여 관련 데이터의 각 집합을 고유하게 식별할 수 있어야 한다.
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

## 📌 제2 정규화

제2 정규형은 테이블의 모든 컬럼이 완전 함수적 종속을 만족하며 기본키중에 특정 컬럼에만 종속된 컬럼(부분적 종속)이 없어야 한다<br>
아래 [before normalization]에는 기본키가 student, lecture 2개로 볼 수 있다.<br>
그러나 name의 경우 기본키중 student에만 종속되어있어서 student컬럼을 알면 name알 수 있기때문에, name이 두 번 들어가는 것은 불필요한 것으로 볼 수 있다.

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

## 📌 제3 정규화

제3 정규형은 제2 정규화를 진행한 테이블에 대해 이행적 종속을 없애도록 테이블을 분해하는 것이다.<br>
이행적 종속이란 A->B, B->C가 성립할 때 A->C가 성립되는 것을 의미한다.<br>
[before normalization]에서 1번 학생이 math라는 수업을 듣지 않고 english로 변경되었다고 가정해보자.<br>
이 학생은 english라는 수업을 150에 듣게 되며, 물론 수강료를 다시 변경할 수 있지만 이러한 번거로움을 해결하기 위해 제3 정규화를 해야하는 것이다.<br>
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

BCNF는 3차 정규형을 조금 더 강화한 버전이며 3차 정규형으로 해결할 수 없는 이상현상을 해결할 수 있습니다.<br>
BCNF란 3차 정규형을 만족하면서 모든 결정자가 후보키 집합에 속한 정규형입니다.<br>
Trivial FD는 Y가 X의 부분집합인 경우를 말하며, A->A 이거나 AB->A 같은 경우를 말합니다.<br>
[before normalization]후보키는 student, lecture이며 로우를 유일하게 구분할 수 있습니다.<br>
professor가 정해지면 과목이 결정되기에 이 테이블의 결정자는 professor 입니다.<br>
그러나 professor는 후보키가 아니기때문에 BCNF를 만족하지 못합니다.<br>
정리하면 3차 정규형을 만족하면서 BCNF는 만족하지 않는 경우 일반 컬럼이 후보키를 결정하는 경우입니다.<br>

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

## 📌 제4 정규화

제 4정규형은 릴레이션 R에 다치 종속을 분리하는 과정입니다.<br>
A ->>B가 존재할 때 R의 모든 속성도 A에 함수 종속이면 릴레이션 R은 제4 정규형에 속합니다.<br>
[before normalization]에서 science의 교수는 kane, messi 교재 코드가 AA, AB라면 [before normalization]에는 4개의 튜플이 포함되어야 합니다.<br>
이렇게 릴레이션이 구성되면 많은 데이터의 중복이 초래되고 이상현상이 발생합니다.<br>
따라서 [before normalization]에서는 과목 ->> 교수코드|교재코드가 존재하므로 [after normalization]과 같이 무손실 분해를 할 수 있습니다.

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

---

📚 참고
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