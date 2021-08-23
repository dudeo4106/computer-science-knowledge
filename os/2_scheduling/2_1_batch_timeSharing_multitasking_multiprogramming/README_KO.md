# 🔑 batch-processing, time-sharing system, multi-tasking, multi-programming

<br>

## 📌 batch-processing

● 일괄 처리, 배치 처리라고 부름<br>
● 컴퓨터 프로그램 실행 요청 순서에 따라 순차적으로 프로그램을 실행하는 방식<br>
● 한번에 등록된 여러 프로그램을 순차적으로 실행 가능<br>
<br>

## 📌 batch-processing과 time-sharing system / multi-programming

● 여러 프로그램을 순차적으로 실행시킬 수 있도록 했으면 좋겠다.
```
○ 어떤 프로그램은 실행이 너무 시간이 많이 걸려서, 다른 프로그램이 실행는데 시간을 많이 기다려야 한다.
○ 나는 MP3 음악을 들으면서, 문서 작성을 하고 싶어요!(동시에 여러 응용 프로그램 실행)
○ 여러 사용자가 동시에 하나의 컴퓨터를 사용 하려면?(다중 사용자 지원)
```
이러한 이유로 multi-programming / time-sharing system이 등장

<br>

## 📌 time-sharing system

● 다중 사용자 지원을 위해 컴퓨터 응답 시간을 최소화하는 시스템<br>

<br>

## 📌 multi-tasking

● 단일 CPU에서, 여러 응용 프로그램이 동시에 실행되는 것처럼 보이도록 하는 시스템
```
○ 나는 음악을 들으면서, 문서를 작성한다.
```

<br>

## 📌 실제 multi-tasking

● 1000밀리초(ms) = 1초<br>
● 10 ~ 20ms 단위로도 실행 응용 프로그램이 바뀌다<br>
● 사용자에게 동시에 실행되는 것처럼 보임<br>

<br>

## 📌 multi-tasking과 multi-processing

● multi-tasking: 단일 CPU<br>
● multi-processing: 여러 CPU에 하나의 프로그램을 병렬로 실행해서 실행속도를 극대화시키는 시스템<br>

<br>

## 📌 multi-programming

● 최대한 CPU를 많이 활용하도록 하는 시스템
```
○ 시간 대비 CPU 활용도를 높이는게 목적
○ 응용 프로그램을 짧은 시간 안에 실행 완료를 시킬 수 있음
```
● 응용 프로그램은 온전히 CPU를 사용하기 보다, 다른 작업을 중간에 필요로 하는 경우가 많습니다.
```
○ 응용 프로그램이 실행되다가 파일을 읽는다.
○ 응용 프로그램이 실행되다가 프린팅을 한다.
```

<br>

## 📌 정리
● time-sharing system: 다중 사용자 지원, 컴퓨터 응답시간을 최소화하는 시스템<br>
● multi-tasking: 단일 CPU에서 여러 응용 프로그램을 동시에 실행하는 것처럼 보이게 하는 시스템<br>
● multi-processing: 여러 CPU에서 하나의 응용 프로그램을 병렬로 실행하게 해서, 실행속도를 높이는 기법<br>
● multi-programming: 최대한 CPU를 일정 시간당 많이 활용하는 시스템(실제로는 time-sharing system, multi-programming, multi-tasking이 유사한 의미로 통용)
```
○ 여러 응용 프로그램을 실행 가능토록 함
○ 응용 프로그램이 동시에 실행되는 것처럼 보이도록 함
○ CPU를 쉬지 않고 응용 프로그램을 실행토록 해서, 짧은 시간 안에 응용 프로그램이 실행완료 될 수 있도록 함
○ 컴퓨터 응답 시간도 짧게 해서, 다중 사용자도 지원
```


<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)