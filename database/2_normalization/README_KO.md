# ๐ Normalization

<br>

## ๐ What is normalization?

โ ํ์ด๋ธ ๊ฐ์ ์ค๋ณต๋ ๋ฐ์ดํฐ๋ฅผ ํ์ฉํ์ง ์๋๋ค<br>
โ ๋ฐ์ดํฐ๋ฅผ ๋ผ๋ฆฌ์ ์ผ๋ก ์ ์ฅํ๋ค.<br>
โ ์ค๋ณต๋ ๋ฐ์ดํฐ๋ฅผ ํ์ฉํ์ง ์์์ผ๋ก์จ ๋ฌด๊ฒฐ์ฑ์ ์ ์งํ  ์ ์์ผ๋ฉฐ ์ฉ๋ ์ญ์ ์ค์ผ ์ ์๋ค.<br>

<br>

## ๐ ์ 1 ์ ๊ทํ

์ด๋ค relation์ ์ํ ๋ชจ๋  domain์ด ์์๊ฐ๋ง์ผ๋ก ๋์ด ์๋ค.<br>
๋ํ ๋ชจ๋  attribute์ ๋ฐ๋ณต๋๋ ๊ทธ๋ฃน์ด ๋ํ๋์ง ์์ผ๋ฉฐ ๊ธฐ๋ณธ ํค๋ฅผ ์ฌ์ฉํ์ฌ ๊ด๋ จ ๋ฐ์ดํฐ์ ๊ฐ ์งํฉ์ ๊ณ ์ ํ๊ฒ ์๋ณํ  ์ ์์ด์ผ ํ๋ค.
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

## ๐ ์ 2 ์ ๊ทํ

์ 2 ์ ๊ทํ์ ํ์ด๋ธ์ ๋ชจ๋  ์ปฌ๋ผ์ด ์์  ํจ์์  ์ข์์ ๋ง์กฑํ๋ฉฐ ๊ธฐ๋ณธํค์ค์ ํน์  ์ปฌ๋ผ์๋ง ์ข์๋ ์ปฌ๋ผ(๋ถ๋ถ์  ์ข์)์ด ์์ด์ผ ํ๋ค<br>
์๋ [before normalization]์๋ ๊ธฐ๋ณธํค๊ฐ student, lecture 2๊ฐ๋ก ๋ณผ ์ ์๋ค.<br>
๊ทธ๋ฌ๋ name์ ๊ฒฝ์ฐ ๊ธฐ๋ณธํค์ค student์๋ง ์ข์๋์ด์์ด์ student์ปฌ๋ผ์ ์๋ฉด name์ ์ ์๊ธฐ๋๋ฌธ์, name์ด ๋ ๋ฒ ๋ค์ด๊ฐ๋ ๊ฒ์ ๋ถํ์ํ ๊ฒ์ผ๋ก ๋ณผ ์ ์๋ค.

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

## ๐ ์ 3 ์ ๊ทํ

์ 3 ์ ๊ทํ์ ์ 2 ์ ๊ทํ๋ฅผ ์งํํ ํ์ด๋ธ์ ๋ํด ์ดํ์  ์ข์์ ์์ ๋๋ก ํ์ด๋ธ์ ๋ถํดํ๋ ๊ฒ์ด๋ค.<br>
์ดํ์  ์ข์์ด๋ A->B, B->C๊ฐ ์ฑ๋ฆฝํ  ๋ A->C๊ฐ ์ฑ๋ฆฝ๋๋ ๊ฒ์ ์๋ฏธํ๋ค.<br>
[before normalization]์์ 1๋ฒ ํ์์ด math๋ผ๋ ์์์ ๋ฃ์ง ์๊ณ  english๋ก ๋ณ๊ฒฝ๋์๋ค๊ณ  ๊ฐ์ ํด๋ณด์.<br>
์ด ํ์์ english๋ผ๋ ์์์ 150์ ๋ฃ๊ฒ ๋๋ฉฐ, ๋ฌผ๋ก  ์๊ฐ๋ฃ๋ฅผ ๋ค์ ๋ณ๊ฒฝํ  ์ ์์ง๋ง ์ด๋ฌํ ๋ฒ๊ฑฐ๋ก์์ ํด๊ฒฐํ๊ธฐ ์ํด ์ 3 ์ ๊ทํ๋ฅผ ํด์ผํ๋ ๊ฒ์ด๋ค.<br>
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

## ๐ BCNF(Boyce and Codd Normal Form)

BCNF๋ 3์ฐจ ์ ๊ทํ์ ์กฐ๊ธ ๋ ๊ฐํํ ๋ฒ์ ์ด๋ฉฐ 3์ฐจ ์ ๊ทํ์ผ๋ก ํด๊ฒฐํ  ์ ์๋ ์ด์ํ์์ ํด๊ฒฐํ  ์ ์์ต๋๋ค.<br>
BCNF๋ 3์ฐจ ์ ๊ทํ์ ๋ง์กฑํ๋ฉด์ ๋ชจ๋  ๊ฒฐ์ ์๊ฐ ํ๋ณดํค ์งํฉ์ ์ํ ์ ๊ทํ์๋๋ค.<br>
Trivial FD๋ Y๊ฐ X์ ๋ถ๋ถ์งํฉ์ธ ๊ฒฝ์ฐ๋ฅผ ๋งํ๋ฉฐ, A->A ์ด๊ฑฐ๋ AB->A ๊ฐ์ ๊ฒฝ์ฐ๋ฅผ ๋งํฉ๋๋ค.<br>
[before normalization]ํ๋ณดํค๋ student, lecture์ด๋ฉฐ ๋ก์ฐ๋ฅผ ์ ์ผํ๊ฒ ๊ตฌ๋ถํ  ์ ์์ต๋๋ค.<br>
professor๊ฐ ์ ํด์ง๋ฉด ๊ณผ๋ชฉ์ด ๊ฒฐ์ ๋๊ธฐ์ ์ด ํ์ด๋ธ์ ๊ฒฐ์ ์๋ professor ์๋๋ค.<br>
๊ทธ๋ฌ๋ professor๋ ํ๋ณดํค๊ฐ ์๋๊ธฐ๋๋ฌธ์ BCNF๋ฅผ ๋ง์กฑํ์ง ๋ชปํฉ๋๋ค.<br>
์ ๋ฆฌํ๋ฉด 3์ฐจ ์ ๊ทํ์ ๋ง์กฑํ๋ฉด์ BCNF๋ ๋ง์กฑํ์ง ์๋ ๊ฒฝ์ฐ ์ผ๋ฐ ์ปฌ๋ผ์ด ํ๋ณดํค๋ฅผ ๊ฒฐ์ ํ๋ ๊ฒฝ์ฐ์๋๋ค.<br>

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

## ๐ ์ 4 ์ ๊ทํ

์  4์ ๊ทํ์ ๋ฆด๋ ์ด์ R์ ๋ค์น ์ข์์ ๋ถ๋ฆฌํ๋ ๊ณผ์ ์๋๋ค.<br>
A ->>B๊ฐ ์กด์ฌํ  ๋ R์ ๋ชจ๋  ์์ฑ๋ A์ ํจ์ ์ข์์ด๋ฉด ๋ฆด๋ ์ด์ R์ ์ 4 ์ ๊ทํ์ ์ํฉ๋๋ค.<br>
[before normalization]์์ science์ ๊ต์๋ kane, messi ๊ต์ฌ ์ฝ๋๊ฐ AA, AB๋ผ๋ฉด [before normalization]์๋ 4๊ฐ์ ํํ์ด ํฌํจ๋์ด์ผ ํฉ๋๋ค.<br>
์ด๋ ๊ฒ ๋ฆด๋ ์ด์์ด ๊ตฌ์ฑ๋๋ฉด ๋ง์ ๋ฐ์ดํฐ์ ์ค๋ณต์ด ์ด๋๋๊ณ  ์ด์ํ์์ด ๋ฐ์ํฉ๋๋ค.<br>
๋ฐ๋ผ์ [before normalization]์์๋ ๊ณผ๋ชฉ ->> ๊ต์์ฝ๋|๊ต์ฌ์ฝ๋๊ฐ ์กด์ฌํ๋ฏ๋ก [after normalization]๊ณผ ๊ฐ์ด ๋ฌด์์ค ๋ถํด๋ฅผ ํ  ์ ์์ต๋๋ค.

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

## ๐ ์ 5 ์ ๊ทํ

๋ชจ๋  ์กฐ์ธ ์ข์์ด ๋ฆด๋ ์ด์ R์ ํ๋ณดํค๋ฅผ ํตํด์๋ง ์ฑ๋ฆฝ๋๋ค๋ฉด ์ 5 ์ ๊ทํ์ ์ํ๋ค๊ณ  ํ  ์ ์์ต๋๋ค.<br>
์๋ฅผ ๋ค์ด A, B, C๋ฅผ ๋ฆด๋ ์ด์ R์ ๋ถ๋ถ์งํฉ์ด๋ผ๊ณ  ํ  ๋,<br>
๋ฆด๋ ์ด์ R์์ A, B, C๋ฅผ ํ๋ก์ ์ํ ๊ฒ๋ค๊ณผ ์กฐ์ธํ ๊ฒ๊ณผ ์๋์ ๋ฆด๋ ์ด์ R์ด ๊ฐ๋ค๋ฉด ์กฐ์ธ์ข์์ ๋ง์กฑ์ํฌ ์ ์์ต๋๋ค.<br>

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

## ๐ DeNormalization

์ ๊ทํ๋ก ์ธํด ๋ถํด๋ ๋ฆด๋ ์ด์์์ ์ ๋ณด๋ฅผ ์ป๊ธฐ ์ํด์๋ ์กฐ์ธ์ ์ฌ์ฉํด์ผํ๋ค.<br>
๊ฒฝ๋ก๊ฐ ๋จผ, ๋ง์ ์กฐ์ธ์ ์ฌ์ฉํ๋ฉด ์๋ต์๋๊ฐ ๋จ์ด์ง๋ค.<br>
์ ๋ฆฌํ๋ฉด ์ ๊ทํ์๋ ์๋ฐฐ๋๋, ์ฑ๋ฅ ํฅ์์ ์ํด ํ์ด๋ธ์ ๊ฒฐํฉ์ํค๋ ๊ฒฝ์ฐ๋ฅผ ์ญ์ ๊ทํ๋ผ๊ณ  ํ๋ค.<br>

<br>

---

๐ ์ฐธ๊ณ 
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