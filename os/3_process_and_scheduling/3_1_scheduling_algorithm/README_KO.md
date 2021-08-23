# 🔑 scheduling algorithm basic

<br>

## 📌 프로세스란?

● 실행 중인 프로그램은 프로세스라고 함
```
○ 프로세스: 메모리에 올려져서, 실행 중인 프로그램
○ 코드 이미지(바이너리): 실행 파일(EX: ELF format)
```
프로세스라는 용어는 작업, task, job 이라는 용어와 혼용

<br>

## 📌 응용 프로그램과 프로세스

● 응용 프로그램 =! 프로세스
```
○ 응용 프로그램은 여러 개의 프로세스로 이루어질 수 있음
```
● 하나의 응용 프로그램은 여러 개의 프로세스(프로그램)과 상호작용을 하면서 실행 될 수도 있음
```
○ 간단한 프로그램을 만든다면 -> 하나의 프로세스
○ 여러 프로그램을 만들어서, 서로 통신하면서 프로그램을 작성할 수도 있음 (IPC 기법)
```

<br>

## 📌 Scheduler

● 프로세스를 실행 / 관리

<br>

## 📌 Scheduling Algorithm

● 목표
```
○ 시분할 시스템 예: 프로세스 응답 시간을 가능한 짧게
○ 멀티 프로그래밍 예: CPU 활용도를 최대로 높혀서, 프로세스를 빨리 실행
```

<br>

## 📌 FIFO scheduler

● EX) 프로세스가 저장매체를 읽는 다든지, 프린팅을 한다든지 하는 작업 없이, 쭉 CPU를 처음부터 끝까지 사용한다.<br>
● 가장 간단한 스케쥴러 (batch-processing)<br>
● FCFS (First Come First Served) scheduler<br>

<br>

## 📌 최단 작업 우선 (SJF) 스케쥴러

● 가장 프로세스 시장이 짧은 프로세스부터 먼저 실행 시키는 알고리즘

<br>

## 📌 우선순위 기반 스케쥴러

● Priority-Based Scheduler
```
○ 정적 우선순위
  - 프로세스마다 우선순위를 미리지정
○ 동적 우선순위
  - 스케쥴러가 상황에 따라 우선순위를 동적으로 변경
```

<br>

## 📌 Round Robin scheduler

● 프로세스들 사이에 우선순위를 두지 않고, 순서대로 시간단위(Time Quantum/Slice)로 CPU를 할당하는 방식의 알고리즘<br>
● 컴퓨터 자원을 사용할 수 있는 기회를, 프로세스들에게 공정하게 부여하기 위한 한 방법<br>

<br>

## 📌 정리

● 다양한 기본 스케쥴링 알고리즘
```
○ FIFO (FCFS) 스케쥴링 알고리즘 (batch-processing)
○ 최단 작업 우선(SJF) 스케쥴링 알고리즘
○ 우선순위 기반 스케쥴링 알고리즘
  - 정적 우선순위, 동적 우선순위
○ Round Robin 스케쥴링 알고리즘
  - 시분할 시스템 기반
```

<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)