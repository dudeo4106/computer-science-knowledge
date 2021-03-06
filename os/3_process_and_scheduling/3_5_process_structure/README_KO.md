# π Process Structure

<br>

## π Process Structure

β νλ‘μΈμ€ (process) λ μΌλ°μ μΌλ‘ μ΄λ»κ² κ΅¬μ±λμ΄ μμκΉ?
```
β TEXT: μ½λ
  - program code
  - fixed size
β DATA: λ³μ / μ΄κΈ°νλ λ°μ΄ν°
  - initialized global and static variables
  - fixed size
β BSS: λ³μ / μ΄κΈ°ν λμ§ μμ λ°μ΄ν°
  - uninitialized global and static variables
  - fixed size
β HEAP: μ½λμμ λμ μΌλ‘ λ§λ€μ΄μ§λ λ°μ΄ν°
  - dynamic variables, managed by malloc(), free(), etc
  - fixed size
β STACK: μμ λ°μ΄ν° (ν¨μ νΈμΆ, λ‘μ»¬ λ³μ λ±)
  - stack frames consisting of parameters, return addresses and local variables
  - variable size
```
β PC(Program Counter) + SP(Stack Pointer)<br>

<br>

## π Heap
```
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *data;
    data = (int *) malloc(sizeof(int));
    *data = 1;

    return 0;
}
```

<br>

## π PCB
> PC, SPλ μ΄λμ μ μ₯νλ?

β PCBμ μ μ₯νλ©° Process Context Block μ΄λΌκ³ λ νλ©° νλ‘μΈμ€κ° μ€νμ€μΈ μνλ₯Ό μΊ‘μ³/κ΅¬μ‘°νν΄μ μ μ₯
```
β Process ID
β Register Value(PC, SP, Etc)
β Scheduling Info(Process State)
β Memory Info (Memory Size Limit)
```

<br>

## π PCB: EX) Linux

![PCB](./image/pcb.png)

<br>

## π μ λ¦¬

β νλ‘μΈμ€ κ΅¬μ‘°
```
β STACK
β HEAP
β DATA(BSS, DATA)
β TEXT(CODE)
```
β PCB
```
β νλ‘μΈμ€ μν μ λ³΄
  - PC
  - SP
  - Memory
  - Scheduling Info
```


<br>
<br>

---

##### π μ°Έκ³ κ°μοΌ[μ»΄ν¨ν° κ³΅ν μ κ³΅ νμ μ¬μΈμ ν¨ν€μ§ Online](https://fastcampus.co.kr/dev_online_cs)