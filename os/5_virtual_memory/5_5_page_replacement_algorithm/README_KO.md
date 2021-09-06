# 🔑 Page Replacement Algorithm

<br>

## 📌 page replacement policy

> 어떤 페이지를 물리 메모리에서, 저장 매체로 내릴 것인가? -> Page Replacement (Swapping) Algorithm

● 운영체제가 특정 페이지를 물리 메모리에 올리려 하는데, 물리 메모리가 다 차있다면?
```
○ 기본 페이지 중 하나를 물리 메모리에서 저장 매체로 내리고(저장)
○ 새로운 페이지를 해당 물리 메모리 공간에 올린다.
```

<br>

## 📌 FIFO

● FIFO Page Replacement Algorithm
```
○ 가장 먼저 들어온 페이지를 내리자
```

<br>

## 📌 OPT

● OPT Page Replacement Algorithm
```
○ 앞으로 가장 오랫동안 사용하지 않을 페이지를 내리자
○ 일반 OS에서는 구현 불가
```

<br>

## 📌 LRU

● Least Recently Used Page Replacement Algorithm
```
○ 가장 오래 전에 사용된 페이지를 교체
○ OPT 교체 알고리즘이 구현이 불가하므로, 과거 기록을 기반으로 시도
```

<br>

## 📌 LFU

● Least Frequently Used Page Replacement Algorithm
```
○ 가장 적게 사용된 페이지를 내리자
```

<br>

## 📌 NUR

● Not Used Frequently Page Replacement Algorithm
```
○ LRU와 마찬가지로 최근에 사용하지 않은 페이지부터 교체하는 기법
○ 각 페이지마다 참조비트 (R), 수정 비트 (M)을 둔다.(R, M)
  - (0, 0), (0, 1), (1, 0), (1, 1)순으로 페이지 교체
```

<br>

## 📌 Thrashing

● 반복적으로 페이지 폴트가 발생해서, 과도하게 페이지 교체 작업이 일어나, 실제로는 아무일도 하지 못하는 상황<br>

![Thrashing](./image/thrashing.png)<br>

<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)