# 🔑 DDL and DML

<br>

## 📌 SQL 개념

● 국제 표준 데이터베이스 언어이며 RDB를 지원하는 언어로 채택<br>
● 관계대수와 관계해석을 기초로 한 혼합 데이터 언어<br>

|DDL<br>(Data Define Language)|DML<br>(Data Manipulation Language)|DCL<br>(Data Control Language)|
|---|---|---|
|create<br>alter<br>delete<br>|select<br>insert<br>delete<br>update<br>|commit<br>rollback<br>grant<br>|

<br>

## 📌 DDL

● 스키마/도메인/테이블/뷰/인덱스를 정의하거나 변경, 제거할 때 사용하는 언어<br>
● 데이터베이스 관리자 혹은 설계자가 사용<br>
● schema 란? 데이터베이스 구조와 제약조건에 관한 전반적인 명세를 기술하며 데이터 개체, 관계 및 제약조건 등에 관해 전반적으로 정의한 것
```
○ create: 스키마, 테이블, 뷰 등을 정의
○ alter: 테이블에 대한 정의를 변경
○ drop: 스키마, 테이블, 뷰 등을 삭제
○ truncate: 테이블이 유지된 상태로 데이터만 삭제(테이블 용량, 인덱스도 다 삭제되며 삭제 후 되돌릴 수 없다)
```

<br>

## 📌 DML

● 사용자가 지정된 데이터를 처리할 때 사용(입력, 수정, 삭제, 검색)<br>
● 데이터베이스 사용자와 관리 시스템 간의 인터페이스 제어<br>
● tuple 이란? table(relation)을 구성하는 각각의 행을 뜻한다. 또한 이것을 레코드라고 부르는데 좀 더 공식적으로 튜플이라고 한다. 
```
○ select: 테이블에서 조건에 맞는 튜플을 검색
○ insert: 테이블에서 새로운 튜플을 삽입
○ delete: 테이블에서 조건에 맞는 튜플을 삭제
○ update: 테이블에서 조건에 맞는 튜플의 내용을 변경
```

<br>

## 📌 DCL

● 데이터의 보안, 무결성, 회복, 병행 제어 등을 정의하는데 사용되는 언어<br>
● 데이터 관리 목적<br>
```
○ commit: 트랜잭션이 성공적으로 끝난 후 변경된 내용을 데이터베이스에 반영
○ rollback: "commit" 되지 않은 변경된 내용을 취소하고 이전 상태로 되돌리는 명령
○ grant: 데이터베이스 관리자가 사용자에게 권한 부여
○ revoke: 데이터베이스 관리자가 사용자에게 권한 취소
○ savepoint: 트랜잭션 내에 "rollback"할 위치인 저장점을 저장
```

<br>

---

📚 참고
<br>
[https://rosypark.tistory.com/301](https://rosypark.tistory.com/301)
<br>
[https://sung0woo.tistory.com/68](https://sung0woo.tistory.com/68)
<br>
[https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=potter777777&logNo=220740559802](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=potter777777&logNo=220740559802)