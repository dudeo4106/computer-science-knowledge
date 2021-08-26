# 🔑 Context Switching

<br>

## 📌 Context Switching 이란

● CPU에 실행할 프로세스를 교체하는 기술

<br>

## 📌 Context Switching Example

● 순서①: 실행 중지할 프로세스 정보를 해당 프로세스의 PCB에 업데이트해서, 메인 메모리에 저장<br>
● 순서②: 다음 실행할 프로세스 정보의 메인 메모리에 있는 해당 PCB(PC, SP) 정보를, CPU의 레지스터에 넣고 실행<br>

> dispatch: ready 상태의 프로세스를 running 상태로 바꾸는 것

> 실제로는 굉장히 짧은 시간(ms) 단위로, 프로세스 스위칭이 일어남

<br>

## 📌 정리

● 프로세스 상태 정보를 PCB로부터 CPU에 로드하고, 실행

<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)