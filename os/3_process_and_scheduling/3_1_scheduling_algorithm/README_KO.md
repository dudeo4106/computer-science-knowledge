# π scheduling algorithm basic

<br>

## π νλ‘μΈμ€λ?

β μ€ν μ€μΈ νλ‘κ·Έλ¨μ νλ‘μΈμ€λΌκ³  ν¨
```
β νλ‘μΈμ€: λ©λͺ¨λ¦¬μ μ¬λ €μ Έμ, μ€ν μ€μΈ νλ‘κ·Έλ¨
β μ½λ μ΄λ―Έμ§(λ°μ΄λλ¦¬): μ€ν νμΌ(EX: ELF format)
```
νλ‘μΈμ€λΌλ μ©μ΄λ μμ, task, job μ΄λΌλ μ©μ΄μ νΌμ©

<br>

## π μμ© νλ‘κ·Έλ¨κ³Ό νλ‘μΈμ€

β μμ© νλ‘κ·Έλ¨ =! νλ‘μΈμ€
```
β μμ© νλ‘κ·Έλ¨μ μ¬λ¬ κ°μ νλ‘μΈμ€λ‘ μ΄λ£¨μ΄μ§ μ μμ
```
β νλμ μμ© νλ‘κ·Έλ¨μ μ¬λ¬ κ°μ νλ‘μΈμ€(νλ‘κ·Έλ¨)κ³Ό μνΈμμ©μ νλ©΄μ μ€ν λ  μλ μμ
```
β κ°λ¨ν νλ‘κ·Έλ¨μ λ§λ λ€λ©΄ -> νλμ νλ‘μΈμ€
β μ¬λ¬ νλ‘κ·Έλ¨μ λ§λ€μ΄μ, μλ‘ ν΅μ νλ©΄μ νλ‘κ·Έλ¨μ μμ±ν  μλ μμ (IPC κΈ°λ²)
```

<br>

## π Scheduler

β νλ‘μΈμ€λ₯Ό μ€ν / κ΄λ¦¬

<br>

## π Scheduling Algorithm

β λͺ©ν
```
β μλΆν  μμ€ν μ: νλ‘μΈμ€ μλ΅ μκ°μ κ°λ₯ν μ§§κ²
β λ©ν° νλ‘κ·Έλλ° μ: CPU νμ©λλ₯Ό μ΅λλ‘ λνμ, νλ‘μΈμ€λ₯Ό λΉ¨λ¦¬ μ€ν
```

<br>

## π FIFO scheduler

β EX) νλ‘μΈμ€κ° μ μ₯λ§€μ²΄λ₯Ό μ½λ λ€λ μ§, νλ¦°νμ νλ€λ μ§ νλ μμ μμ΄, μ­ CPUλ₯Ό μ²μλΆν° λκΉμ§ μ¬μ©νλ€.<br>
β κ°μ₯ κ°λ¨ν μ€μΌμ₯΄λ¬ (batch-processing)<br>
β FCFS (First Come First Served) scheduler<br>

<br>

## π μ΅λ¨ μμ μ°μ  (SJF) μ€μΌμ₯΄λ¬

β κ°μ₯ νλ‘μΈμ€ μμ₯μ΄ μ§§μ νλ‘μΈμ€λΆν° λ¨Όμ  μ€ν μν€λ μκ³ λ¦¬μ¦

<br>

## π μ°μ μμ κΈ°λ° μ€μΌμ₯΄λ¬

β Priority-Based Scheduler
```
β μ μ  μ°μ μμ
  - νλ‘μΈμ€λ§λ€ μ°μ μμλ₯Ό λ―Έλ¦¬μ§μ 
β λμ  μ°μ μμ
  - μ€μΌμ₯΄λ¬κ° μν©μ λ°λΌ μ°μ μμλ₯Ό λμ μΌλ‘ λ³κ²½
```

<br>

## π Round Robin scheduler

β νλ‘μΈμ€λ€ μ¬μ΄μ μ°μ μμλ₯Ό λμ§ μκ³ , μμλλ‘ μκ°λ¨μ(Time Quantum/Slice)λ‘ CPUλ₯Ό ν λΉνλ λ°©μμ μκ³ λ¦¬μ¦<br>
β μ»΄ν¨ν° μμμ μ¬μ©ν  μ μλ κΈ°νλ₯Ό, νλ‘μΈμ€λ€μκ² κ³΅μ νκ² λΆμ¬νκΈ° μν ν λ°©λ²<br>

<br>

## π μ λ¦¬

β λ€μν κΈ°λ³Έ μ€μΌμ₯΄λ§ μκ³ λ¦¬μ¦
```
β FIFO (FCFS) μ€μΌμ₯΄λ§ μκ³ λ¦¬μ¦ (batch-processing)
β μ΅λ¨ μμ μ°μ (SJF) μ€μΌμ₯΄λ§ μκ³ λ¦¬μ¦
β μ°μ μμ κΈ°λ° μ€μΌμ₯΄λ§ μκ³ λ¦¬μ¦
  - μ μ  μ°μ μμ, λμ  μ°μ μμ
β Round Robin μ€μΌμ₯΄λ§ μκ³ λ¦¬μ¦
  - μλΆν  μμ€ν κΈ°λ°
```

<br>
<br>

---

##### π μ°Έκ³ κ°μοΌ[μ»΄ν¨ν° κ³΅ν μ κ³΅ νμ μ¬μΈμ ν¨ν€μ§ Online](https://fastcampus.co.kr/dev_online_cs)