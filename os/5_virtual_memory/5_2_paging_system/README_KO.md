# 🔑 Paging System

<br>

## 📌 paging system - 1

● 크기가 동일한 페이지로 가상 주소 공간과 이에 매칭하는 물리 주소 공간을 관리<br>
● 하드웨어 지원이 필요
```
○ 예) intel x86 시스템(32bit)에서는 4KB, 2MB, 1GB 지원
```
● 리눅스에서는 4KB로 paging<br>
● 페이지 번호를 기반으로 가상 주소 / 물리 주소 매핑 정보를 기록 / 사용<br>

<br>

## 📌 paging system - 2

● 프로세스(4GB)의 PCB에 Page Table 구조체를 가리키는 수고가 들어 있음<br>
● Page Table에는 가상 주소와 물리 주소간 매핑 정보가 있음<br>

![PagingTable](./image/paging_table.png)

<br>

## 📌 paging system structure

● page 또는 page frame: 고정된 크기의 block(4KB)<br>
● paging system
```
○ 가상 주소 v = (p, d)
  - p: 가상 메모리 페이지
  - d: p안에서 참조하는 위치
```
● 페이지 크기가 4KB 예
```
○ 가상 주소의 0비트에서 11비트가 변위 (d)를 나타내고,
○ 12비트 이상이 페이지 번호가 될 수 있음
```

> 프로세스가 4GB를 사용하는 이유 - 32bit 시스템에서 2의 32이승 4GB

<br>

## 📌 paging table

● 물리 주소에 있는 페이지 번호와 해당 페이지의 첫 물리 주소 정보를 매핑한 표<br>
● 가상주소 v = (p, d) 라면
```
○ p: 페이지 번호
○ d: 페이지 처음부터 얼마 떨어진 위치인지
```

<br>

## 📌 paging system 동작

● 해당 프로세스에서 특정 가상 주소 엑세스를 하려면
```
○ 해당 프로세스의 paging table 에 해당 가상 주소가 포함된 page 번호가 있는지 확인
○ page 번호가 있으면 이 page가 매핑된 첫 물리 주소를 알아내고(p')
○ p' + d가 실제 물리 주소가 됨
```

<br>

## 📌 paging system and mmu

● CPU는 가상 주소 접근시
```
○ MMU 하드웨어 장치를 통해 물리 메모리 접근
```
● 프로세스 생성시, 페이지 테이블 정보 생성
```
○ PCB등에서 해당 페이지 테이블 접근 가능하고, 관련 정보는 물리 메모리에 적재
○ 프로세스 구동시, 해당 페이지 테이블 base 주소가 별도 레지스터에 저장(CR3)
○ CPU가 가상 주소 접근시, MMU가 페이지 테이블 base 주소를 접근해서, 물리 주소를 가져옴
```

<br>
<br>

---

##### 📚 참고강의：[컴퓨터 공학 전공 필수 올인원 패키지 Online](https://fastcampus.co.kr/dev_online_cs)