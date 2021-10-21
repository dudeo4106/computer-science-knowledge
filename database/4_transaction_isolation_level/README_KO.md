# 🔑 Transaction Isolation Level

<br>

## 📌 What is transaction isolation level?

트랜잭션 격리수준이란 동시에 여러 트랜잭션이 처리될 때, 특정 트랜잭션이 다른 트랜잭션에서 변경하거나 데이터를 조회할 수 있게 허용할지를 결정하는 것<br>
데이터베이스는 ACID 특징과 같이 트랜잭션이 독립적인 수행을 하도록 Locking을 하여, 트랜잭션의 관여를 막는다.<br>

하지만 무조건 Locking을 하여 트랜잭션이 순서대로만 처리하게 만들면 성능이 저하하게 되고, 성능을 위해 Locking을 해제하게 되면 잘못된 값이 처리되어 버릴 수 있다.

그렇기에 효율적인 Locking 방법이 필요하다.

<br>

## 📌 What is Lock?

Lock이란 트랜잭션 처리의 순차성을 보장하기 위한 방법이며 하나의 트랜잭션이 완벽하게 종료할 때 까지 데이터의 변경, 삭제, 조회를 막아준다.

<br>

## 📌 Shared Lock and Exclusive Lock

> Shared Lock

데이터를 읽을 때 사용되는 Lock이며, Shared Lock은 Shared Lock끼리 동시 접근이 가능하다.<br>
즉 하나의 데이터를 읽는 것이기에 여러 사용자가 동시에 가능지만 Shared Lock으로 설정된 데이터는 Exclusive Lock을 사용 할 수 없다.

> Exclusive Lock

데이터를 변경하고자 할 때 사용되며, 트랜잭션이 종료 될 때까지 유지된다.<br>
Exclusive Lock이 해제될 때까지 다른 트랜잭션(읽기 포함)은 해당 리소스에 접근할 수 없으며, 다른 트랜잭션이 수행되고 있는 데이터에 대해서는 함께 Lock을 설정할 수 없다.

<br>

## 📌 Lock Level

● Database: 데이터베이스 전체에 Lock을 설정하는 것을 의미하며 1개의 세션만이 데이터에 접근 가능하다.<br>
● File: 실제 데이터가 쓰여지는 물리적인 저장소에 Lock을 설정하는 것을 의미<br>
● Table: Table 수준의 Lock 설정을 의미하며, 테이블의 모든행을 업데이트 하는 등의 테이블 전체에 영향을 주는 변경을 수행할 때 주로 사용된다.<br>
● Page, Block: 파일의 일부인 Page와 Block을 기준으로 Lock을 설정하는 것을 의미<br>
● Column: Column을 기준으로 Lock을 설정하는 것을 의미하며 Lock설정, 그리고 해제시 많은 리소스가 필요하기 때문에 일반적으로 사용하지 않음<br>
● Row: 가장 일반적으로 사용되는 Row 수준의 Lock이며 DML에 대한 Lock<br>

<br>

## 📌 Blocking

블로킹은 Lock(Exclusive - Exclusive, Exclusive - Shared)의 경합이 발생하여 특정 Transaction이 작업을 진행하지 못하고 멈춰선 상태를 말합니다.<br>
Shared Lock끼리는 블로킹이 발생하지 않지만 Exclusive Lock은 블로킹을 발생시킵니다.<br>
블로킹을 해소하기 위해서는 이전 트랜잭션이 Commit or RollBack 되어야하며, 이러한 경합은 성능을 안좋게 만들기때문에 최소화 시켜야한다.<br>

해소방법

- 한 트랜잭션의 길이를 너무 길게 하지않는다.
- 같은 데이터를 갱신하는 트랜잭션이 동시에 수행되지 않도록 해야한다.
- Isolation Level을 불필요하게 상향조정하지 않고 쿼리 수행시간을 짧게 한다.

<br>

## 📌 DeadLock

프로세스가 자원을 얻지 못해 다음 처리를 하지 못하는 상태로, 시스템적으로 한정된 자원을 여러 곳에서 사용하려 할 때 발생<br>

발생되는 상황으론 멀티 프로그래밍 환경에서 한정된 자원을 사용하려고 서로 경쟁하는 상황이 발생 할 때<br>
어떤 프로세스가 지원을 요청 했을 때 그 시각에 그 자원을 사용할 수 없는 상황이 발생, 프로세스가 대기 상태가 된다.<br>
대기상태로 들어간 프로세스들이 실행 상태로 변경 될 수 없을 때 DeadLock이라고 한다.

* 상세내용은 DeadLock 파트에서 다시 다루기로 한다.

<br>

---

📚 참고
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