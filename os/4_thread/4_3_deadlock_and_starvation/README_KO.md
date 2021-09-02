# 🔑 Deadlock And Starvation

<br>

## 📌 Deadlock

● 두 개 이상의 작업이 서로 상대방의 작업이 끝나기 만을 기다리고 있기 때문에, 다음 단계로 진행하지 못하는 상태
```
○ 무한 대기 상태
○ 배치 처리 시스템에서는 발생하지 않으나 프로세스, 스레드에서는 발생할 수 있음
```

![Deadlock](./image/deadlock.png)

<br>

## 📌 Cause of Deadlock

> 다음 네 가지 조건이 모두 성립될 때, 교착상태 발생 가능성이 있음

● Mutual exclusion: 프로세스들이 필요로 하는 자원에 대해 배타적인 통제권을 요구한다.<br>
● Hold and wait: 프로세스가 할당된 자원을 가진 상태에서 다른 자원을 기다린다.<br>
● No preemption: 프로세스가 어떤 자원의 사용을 끝낼 때까지 그 자원을 뺏을 수 없다.<br>
● Circular wait: 각 프로세스는 순환적으로 다음 프로세스가 요구하는 자원을 가지고 있다.<br>

<br>

## 📌 Deadlock Solution

● Deadlock Prevention<br>
● Deadlock Avoidance<br>
● Deadlock Detection<br>
● Deadlock Recovery<br>

<br>

## 📌 Deadlock Prevention

> 4가지 조건 중 하나를 제거하는 방법

● Mutual exclusion elimination: 임계 영역 제거<br>
● Hold and wait elimination: 한번에 모든 필요 자원 점유 및 해제<br>
● No preemption elimination: 선점 가능 기법을 만들어줌<br>
● Circular wait elimination: 자원 유형에 따라 순서를 매김<br>

<br>

## 📌 Deadlock Avoidance

> 교착상태 조건 1,2,3은 놔두고, 4번만 제거(1,2,3 제거시, 프로세스 실행 비효율성이 증대)

> 교착상태 조건 중, 자원 할당 순서를 정의하지 않음(Circular wait elimination)

● Mutual exclusion elimination: 임계 영역 제거<br>
● Hold and wait elimination: 한번에 모든 필요 자원 점유 및 해제<br>
● No preemption elimination: 선점 가능 기법을 만들어줌<br>
● Circular wait elimination: 자원 유형에 따라 순서를 매김<br>

<br>

## 📌 Deadlock Detection and Deadlock Recovery

● Deadlock Detection
```
○ 교착상태가 발생했는지 점검하여 교착 상태에 있는 프로세스와 자원을 발견하는 것
```
● Deadlock Recovery
```
○ 교착 상태를 일으킨 프로세스를 종료하거나 교착상태의 프로세스에 할당된 자원을 선점하여 프로세스나 자원을 회복하는 것
```

<br>

## 📌 Starvation

● 특정 프로세스의 우선순위가 낮아서 원하는 자원을 계속 할당 받지 못하는 상태<br>
● Deadlock And Starvation
```
○ Deadlock은 여러 프로세스가 동일한 자원 점유를 요청할 때 발생
○ Starvation은 여러 프로세스가 부족한 자원을 점유하기 위해 경쟁할 때, 특정 프로세스는 영원히 자원 할당이 안되는 경우를 주로 의미함
```

<br>

## 📌 Starvation Solution

● 우선순위 변경
```
○ 프로세스 우선순위를 수시로 변경해서, 각 프로세스가 높은 우선순위를 가질 기회주기
○ 오래 기다린 프로세스의 우선순위를 높여주기
○ 우선순위가 아닌, 요청 순서대로 처리하는 FIFO 기반 요청큐 사용
```

<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)