# 🔑 Transaction

<br>

## 📌 트랜잭션이란

데이터베이스의 상태를 변화시키기 위해 수행하는 작업 단위 또는 한꺼번에 모두 수행되어야 할 일련의 연산들을 의미

데이터베이스의 상태를 변화 시킨다는 것은 Select, Update, Insert, Delete와 같은 행동을 의미한다.<br>
이런 트랜잭션은 상황에 따라 여러개 만들어질 수 있고, Commit 되거나 Rollback 될 수 있다.

```
A은행에서 B은행으로 송금하려고할 때 출금과 입금이 각각 한번씩 발생하게 된다.
송금하려는 순간 문제가 발생해 입금이 되지 않은 상황이 발생한다면 거래를 성립시키지 않을 것이다.
만약 A은행에서 출금할 때 문제가 발생했을때 거래를 성립시키면, 출금한 돈이 사라져버리게 되기때문이다.

A은행에서 출금한 돈이 B은행에 잘 도착하면 송금처리를 완료시키고, 
만약 도착하지 않으면 거래를 성립시키지 않고 A은행에서 출금한 돈을 다시 돌려주는 처리를 데이터베이스에 대입해 볼 수 있다.
어떠한 데이터가 변경, 삭제 되었을 때(A은행에서 출금) 문제가 발생하면 Rollback(거래를 성립시키지 않는)을
문제가 발생하지 않았다면 Commit(송금처리)를 하여 데이터를 안정적으로 변경할 수 있다. 
```

<br>

## 📌 TCL

> TCL이란 트랜잭션을 제어하는 언어

● Commit: 트랜잭션이 성공적으로 끝난 후 변경된 내용을 데이터베이스에 반영<br>
● Rollback: "commit" 되지 않은 변경된 내용을 취소하고 이전 상태로 되돌리는 명령<br>
● SavePoint: 트랜잭션 내에 "rollback"할 위치인 저장점을 저장

<br>

## 📌 트랜잭션의 연산과정

> Success: Active -> Failed -> Aborted

> Fail: Active -> Partially Committed -> Committed

● Active: 트랜잭션이 정상적으로 종료된 상태<br>
● Fail: 트랜잭션 실행에 오류가 발생하여 중단된 상태<br>
● Aborted: 트랜잭션이 비정상적으로 종료되어 Rollback 연산을 수행한 상태<br>
● Partially Committed: 트랜잭션의 마지막연산까지 실행했지만, Commit 연산이 실행되기 직전의 상태<br>
● Committed: 트랜잭션이 성공적으로 종료되어 Commit 연산을 실행한 후의 상태<br>

<br>

## 📌 트랜잭션의 성질

● Atomicity: 트랜잭션은 데이터베이스에 모두 반영 or 모두 반여되지 않아야한다. 즉 어느하나라도 오류가 발생하면 전부 취소되어야 한다<br>
● Consistency: 트랜잭션이 성공적으로 완료되면 언제나 일관되어야 한다. 즉 시스템이 갖고 있는 고정요소는 트랜잭션 수행 전과 후의 상태가 같아야 한다.<br>
● Isolation: 둘 이상의 트랜잭션이 동시에 실행되는 경우, 수행중인 트랜잭션이 완전 완료될 때까지 다른 트랜잭션이 연산에 끼어들 수 없다.<br>
● Durability: 트랜잭션이 성공적으로 완료 되었으면 결과는 영구적으로 반영되어야 한다.<br>

<br>

## 📌 UNDO, REDO

> REDO: 다시 하다

> UNDO: 원상태로 돌리다.

● REDO: 이전 상태로 되돌아 간 후, 실패가 발생하기 전까지 과정을 그대로 따라가는 것을 의미하며 이 과정을 기록해야 하는데 이를 log라고 한다.<br>
● UNDO: 트랜잭션을 이전 상태로 되돌리는 것을 의미(RollBack, 읽기 일관성)<br>

```
복구는 UNDO를 이용해 복구를 한다. 즉 RollBack을 한다.
하지만 시스템 장애가 발생하면 UNDO 데이터도 모두 삭제되어, REDO 데이터를 이용해서 마지막 CheckPoint(SavePoint)부터 장애까지의 BufferCache를 복구하게 된다.
이게 완료 되면 UNDO를 이용해서 Commit 되지 않은 데이터를 모두 RollBack 함으로써 복구를 완료하게 된다.
결국 REDO가 UNDO를 복구하고 최종적으로 UNDO가 복구를 하게 됩니다.
```

<br>

---

📚 참고
<br>
[https://wonit.tistory.com/462](https://wonit.tistory.com/462)
<br>
[https://devuna.tistory.com/30](https://devuna.tistory.com/30)
<br>
[https://mozi.tistory.com/209](https://mozi.tistory.com/209)
<br>
[https://coding-factory.tistory.com/226](https://coding-factory.tistory.com/226)
<br>
[https://victorydntmd.tistory.com/130](https://victorydntmd.tistory.com/130)
<br>
[https://brownbears.tistory.com/181](https://brownbears.tistory.com/181)