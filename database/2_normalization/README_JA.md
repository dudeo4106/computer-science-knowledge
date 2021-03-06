# ð Normalization

<br>

## ð What is normalization?

â ãã¼ãã«éã§éè¤ãããã¼ã¿ãè¨±å®¹ãã¾ããã<br>
â ãã¼ã¿ãè«ççã«ä¿å­ãã¾ãã<br>
â éè¤ãããã¼ã¿ãèªããªããã¨ã§å®å¨æ§ãç¶­æã§ããå®¹éãæ¸ãããã¨ãã§ãã¾ãã<br>

<br>

## ð ç¬¬1æ­£è¦å

ããrelationã«å±ããå¨ã¦ã®domainãåå­å¤ã®ã¿ã¨ãªã£ã¦ãã¾ãã<br>
ã¾ãããã¹ã¦ã®attributeã«ç¹°ãè¿ãããã°ã«ã¼ããç¾ãããããã©ã«ãã­ã¼ãä½¿ç¨ãã¦é¢é£ãã¼ã¿ã®åéåãåºæã«è­å¥ã§ãã¾ãã
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

## ð ç¬¬2æ­£è¦å

ç¬¬2æ­£è¦åã¯ããã¼ãã«ã®ãã¹ã¦ã®ã«ã©ã ãå®å¨é¢æ°çå¾å±ãæºè¶³ããåºæ¬ã­ã¼ã®ä¸­ã«ç¹å®ã®ã«ã©ã ã«ã®ã¿å¾å±ãããã«ã©ã ï¼é¨åçå¾å±ï¼ããã£ã¦ã¯ãªãã¾ããã<br>
ä»¥ä¸ã®[beforenormalization]ã§ã¯ãããã©ã«ãã­ã¼ãstudentãlecture ã®2ã¤ã§ç¢ºèªãããã¨ãã§ãã¾ãã<br>
ããããnameã®å ´åãããã©ã«ãã­ã¼ã®ãã¡studentã«ã®ã¿å¾å±ããã¦ããã®ã§ãstudentã«ã©ã ãåããã°nameåããã®ã§ãnameã2åå¥ããã®ã¯ä¸è¦ã ã¨è¨ãã¾ãã
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

## ð ç¬¬3æ­£è¦å

ç¬¬3æ­£è¦å½¢ã¯ãç¬¬2æ­£è¦åãé²ãããã¼ãã«ã«å¯¾ãã¦ç§»è¡çå¾å±ããªããããã«ãã¼ãã«ãåè§£ãããã®ã§ãã<br>
ç§»è¡çå¾å±ã¨ã¯ãA->BãB->Cã®æç«æã«AâCãæç«ãããã¨ãæå³ãã¾ãã<br>
[beforenormalization]ã§1çªã®å­¦çãmathã¨ããææ¥­ãåããã«englishã«å¤æ´ãããã¨ä»®å®ãã¾ãããã<br>
ãã®å­¦çã¯ãenglishã¨ããææ¥­ã150ã«èãã¦ãå¿è«åè¬æãããä¸åº¦å¤æ´ã§ãã¾ããããã®ãããªç©ããããè§£æ±ºããããã«ç¬¬3æ­£è¦åãããªããã°ãªããªãã®ã§ãã
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

## ð BCNF(Boyce and Codd Normal Form)

BCNFã¯ã3æ¬¡æ­£è¦åãããã«å¼·åãããã¼ã¸ã§ã³ã§ã3æ¬¡æ­£è¦åã§ã¯è§£æ±ºã§ããªãç°å¸¸ç¾è±¡ãè§£æ±ºã§ãã¾ãã<br>
BCNFã¨ã¯ã3æ¬¡æ­£è¦å½¢ãæºè¶³ãã¤ã¤ããã¹ã¦ã®æ±ºå®èãåè£éµéåã«å±ããæ­£è¦å½¢ã§ãã<br>
Trivial FDã¯YãXã®é¨åéåã®å ´åãæããAâAãABâAã®ãããªå ´åãæãã¾ãã<br>
[before normalization]åè£ã­ã¼ã¯ student, lecture ã§ãã­ã¼ãå¯ä¸åºåã§ãã¾ãã<br>
professorãæ±ºã¾ãã¨ç§ç®ãæ±ºå®ããããããã®ãã¼ãã«ã®æ±ºå®èã¯professorã§ãã<br>
ãããprofessorã¯åè£ã­ã¼ã§ã¯ãªãã®ã§BCNFãæºè¶³ãããã¨ãã§ãã¾ããã<br>
æ´çããã¨3æ¬¡æ­£è¦åã«æºè¶³ããBCNFã¯æºè¶³ããªãå ´åãä¸è¬ã«ã©ã ãåè£ã­ã¼ãæ±ºããå ´åã§ãã<br>

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

## ð ç¬¬4æ­£è¦å

ç¬¬4æ­£è¦åã¯ãªã¬ã¼ã·ã§ã³Rã«å¤å¤å¾å±ãåé¢ããéç¨ã§ãã<br>
Aâ>Bãå­å¨ããæãRã®ãã¹ã¦ã®å±æ§ãAã«é¢æ°å¾å±ã§ããã°ããªã¬ã¼ã·ã§ã³Rã¯ç¬¬4æ­£è¦å½¢ã«å±ãã¾ãã<br>
[before normalization]ã§scienceã®ææã¯kane,messiææã³ã¼ããAAãABãªã[before normalization]ã«ã¯4ã¤ã®ãã¥ã¼ãã«ãå«ã¾ããªããã°ãªãã¾ããã<br>
ãã®ããã«ãªã¬ã¼ã·ã§ã³ãæ§æãããã¨ãå¤ãã®ãã¼ã¿ã®éè¤ãæããç°å¸¸ç¾è±¡ãçºçãã¾ãã<br>
ãããã£ã¦[beformalization]ã§ã¯ç§ç®ã¼>>ææã³ã¼ãï½ææã³ã¼ããå­å¨ããã®ã§[afternormalization]ã®ããã«ç¡æå¤±åè§£ã§ãã¾ãã

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

## ð ç¬¬5æ­£è¦å

å¨ã¦ã®èª¿å°å¾å±ããªã¬ã¼ã·ã§ã³Rã®åè£ã­ã¼ãä»ãã¦æç«ãããªããç¬¬5æ­£è¦å½¢ã«å±ããã¨ããã¾ãã<br>
ä¾ãã°ãAãBãCããªã¬ã¼ã·ã§ã³Rã®é¨åéåã¨ããã¨ãã<br>
ãªã¬ã¼ã·ã§ã³Rã«ããã¦ãAãBãCããã­ã¸ã§ã¯ã·ã§ã³ãããã®ã¨èª¿å°ãããã®ã¨åã®ãªã¬ã¼ã·ã§ã³Rãåããªããèª¿å°å¾å±ãæºè¶³ããããã¨ãã§ãã¾ãã<br>

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

## ð DeNormalization

æ­£è¦åã«ãã£ã¦åè§£ããããªã¬ã¼ã·ã§ã³ã«ããã¦æå ±ãå¾ãããã«ã¯ãjoinãä½¿ç¨ããªããã°ãªãã¾ããã<br>
çµè·¯ãé ããå¤ãã®joinãä½¿ç¨ããã¨ãå¿ç­éåº¦ãè½ã¡ã¾ãã<br>
æ´çããã¨æ­£è¦åã«ã¯éåããããæ§è½åä¸ã®ããã«ãã¼ãã«ãçµåãããå ´åãéæ­£è¦åã¨ããã¾ãã<br>

<br>

---

ð åè
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
