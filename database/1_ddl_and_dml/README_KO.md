# π DDL and DML

<br>

## π SQL κ°λ

β κ΅­μ  νμ€ λ°μ΄ν°λ² μ΄μ€ μΈμ΄μ΄λ©° RDBλ₯Ό μ§μνλ μΈμ΄λ‘ μ±ν<br>
β κ΄κ³λμμ κ΄κ³ν΄μμ κΈ°μ΄λ‘ ν νΌν© λ°μ΄ν° μΈμ΄<br>

|DDL<br>(Data Define Language)|DML<br>(Data Manipulation Language)|DCL<br>(Data Control Language)|
|---|---|---|
|create<br>alter<br>delete<br>|select<br>insert<br>delete<br>update<br>|commit<br>rollback<br>grant<br>|

<br>

## π DDL

β μ€ν€λ§/λλ©μΈ/νμ΄λΈ/λ·°/μΈλ±μ€λ₯Ό μ μνκ±°λ λ³κ²½, μ κ±°ν  λ μ¬μ©νλ μΈμ΄<br>
β λ°μ΄ν°λ² μ΄μ€ κ΄λ¦¬μ νΉμ μ€κ³μκ° μ¬μ©<br>
β schema λ? λ°μ΄ν°λ² μ΄μ€ κ΅¬μ‘°μ μ μ½μ‘°κ±΄μ κ΄ν μ λ°μ μΈ λͺμΈλ₯Ό κΈ°μ νλ©° λ°μ΄ν° κ°μ²΄, κ΄κ³ λ° μ μ½μ‘°κ±΄ λ±μ κ΄ν΄ μ λ°μ μΌλ‘ μ μν κ²
```
β create: μ€ν€λ§, νμ΄λΈ, λ·° λ±μ μ μ
β alter: νμ΄λΈμ λν μ μλ₯Ό λ³κ²½
β drop: μ€ν€λ§, νμ΄λΈ, λ·° λ±μ μ­μ 
β truncate: νμ΄λΈμ΄ μ μ§λ μνλ‘ λ°μ΄ν°λ§ μ­μ (νμ΄λΈ μ©λ, μΈλ±μ€λ λ€ μ­μ λλ©° μ­μ  ν λλλ¦΄ μ μλ€)
```

<br>

## π DML

β μ¬μ©μκ° μ§μ λ λ°μ΄ν°λ₯Ό μ²λ¦¬ν  λ μ¬μ©(μλ ₯, μμ , μ­μ , κ²μ)<br>
β λ°μ΄ν°λ² μ΄μ€ μ¬μ©μμ κ΄λ¦¬ μμ€ν κ°μ μΈν°νμ΄μ€ μ μ΄<br>
β tuple μ΄λ? table(relation)μ κ΅¬μ±νλ κ°κ°μ νμ λ»νλ€. λν μ΄κ²μ λ μ½λλΌκ³  λΆλ₯΄λλ° μ’ λ κ³΅μμ μΌλ‘ ννμ΄λΌκ³  νλ€. 
```
β select: νμ΄λΈμμ μ‘°κ±΄μ λ§λ ννμ κ²μ
β insert: νμ΄λΈμμ μλ‘μ΄ ννμ μ½μ
β delete: νμ΄λΈμμ μ‘°κ±΄μ λ§λ ννμ μ­μ 
β update: νμ΄λΈμμ μ‘°κ±΄μ λ§λ ννμ λ΄μ©μ λ³κ²½
```

<br>

## π DCL

β λ°μ΄ν°μ λ³΄μ, λ¬΄κ²°μ±, νλ³΅, λ³ν μ μ΄ λ±μ μ μνλλ° μ¬μ©λλ μΈμ΄<br>
β λ°μ΄ν° κ΄λ¦¬ λͺ©μ <br>
```
β commit: νΈλμ­μμ΄ μ±κ³΅μ μΌλ‘ λλ ν λ³κ²½λ λ΄μ©μ λ°μ΄ν°λ² μ΄μ€μ λ°μ
β rollback: "commit" λμ§ μμ λ³κ²½λ λ΄μ©μ μ·¨μνκ³  μ΄μ  μνλ‘ λλλ¦¬λ λͺλ Ή
β grant: λ°μ΄ν°λ² μ΄μ€ κ΄λ¦¬μκ° μ¬μ©μμκ² κΆν λΆμ¬
β revoke: λ°μ΄ν°λ² μ΄μ€ κ΄λ¦¬μκ° μ¬μ©μμκ² κΆν μ·¨μ
β savepoint: νΈλμ­μ λ΄μ "rollback"ν  μμΉμΈ μ μ₯μ μ μ μ₯
```

<br>

---

π μ°Έκ³ 
<br>
[https://rosypark.tistory.com/301](https://rosypark.tistory.com/301)
<br>
[https://sung0woo.tistory.com/68](https://sung0woo.tistory.com/68)
<br>
[https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=potter777777&logNo=220740559802](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=potter777777&logNo=220740559802)