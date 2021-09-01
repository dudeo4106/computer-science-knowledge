# 🔑 Synchronization Issue And Semaphore

<br>

## 📌 Synchronization Issue

● 동기화: 작업들 사이에 실행 시기를 맞추는 것<br>
● 여러 스레드가 동일한 자원(데이터) 접근시 동기화 이슈 발생
```
○ 동일 자원을 여러 스레드가 동시 수정시, 각 스레드 결과에 영향을 줌
```

<br>

## 📌 Synchronization Issue Solution

● Mutual exclusion<br>
● 쓰레드는 프로세스 모든 데이터를 접근할 수 있음
```
○ 여러 스레드가 변경하는 공유 변수에 대해 Exclusive Access 필요
○ 어느 한 스레드가 공유 변수를 갱신하는 동안 다른 스레드가 동시 접근하지 못도록 막아야함
```

<br>

## 📌 Mutual exclusion (상호 배제)

● critical resource<br>
● critical section
```
lock.acquire()
for i in range(100000):
    g_count +=1
lock.release()
```

<br>

## 📌 Mutex And Semaphore

● Critical Section에 대한 접근을 막기 위해 LOCKING 메커니즘이 필요
```
○ Mutex(binary semaphore)
  : 임계구역에 하나의 스레드만 들어갈 수 있음
○ Semaphore
  : counter를 두어서 동시에 리소스에 접근 할 수 있는 허용 가능한 스레드 수를 제어
```

<br>

## 📌 Semaphore

● P: 검사 (임계영역에 들어갈 때)
```
○ S값이 1이상이면, 임계 영역 진입 후, S값 1차감(S값이 0이면 대기)
```
● V: 증가 (임계영역에 나올 때)
```
○ S값을 1더하고, 임계 영역을 나옴
```
● S: Semaphore Value(초기 값만큼 여러 프로세스가 동시 임계 영역 접근 가능)
```
P(S): wait(S) {
    while S <= 0; // wait
        S--;      // limit access
}
```
```
V(S): signal(S) {
    S++; // allow access
}
```
● wakeup() 함수를 통해 대기큐에 있는 프로세스 재실행
```
signal(S) {
    S->count++;
    if (S->count > 0) {
        remove a process P from S->queue;
        wakeup(P)
    }
}
```

<br>

## 📌 Semaphore - 바쁜 대기

● wait()는 S가 0이라면, 임계영역에 들어가기 위해, 반복문 수행
```
○ busy waiting
```
```
P(S): wait(S) {
    while S <= 0; // busy waiting
        S--;      // limit access
}
```

<br>

## 📌 Semaphore - 대기 큐

> 운영체제 기술로 보완 - 대기큐

● S가 음수일 경우, 바쁜 대기 대신, 대기큐에 넣는다.

```
wait(S) {
    S->count--;
    if (S->count <= 0) {
        add this process to S->queue;
        block()
    }
}
```

<br>

## 📌 참고: 주요 세마포어 함수 (POSIX Semaphore)

● sem_open(): 세마포어를 생성<br>
● sem_wait(): 임계영역 접근 전, 세마포어를 잠그고, 세마포어가 잠겨있다면, 풀릴 때까지 대기<br>
● sem_post(): 공유자원에 대한 접근이 끝났을 때 세마포어 잠금을 헤체한다.<br>

<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)