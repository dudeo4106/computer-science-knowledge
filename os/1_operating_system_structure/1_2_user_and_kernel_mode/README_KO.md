# π μ¬μ©μμ μ»€λ λͺ¨λ

<br>

## π CPU Protection Rings

β CPUλ κΆν λͺ¨λλΌλ κ²μ κ°μ§κ³  μμ΅λλ€.
```
β μ¬μ©μ λͺ¨λ(user mode by applications)
β μ»€λ λͺ¨λ(kernel mode by OS): νΉκΆ λͺλ Ήμ΄ μ€νκ³Ό μνλ μμ μνμ μν μμ μ κ·Όμ κ°λ₯μΌ νλ λͺ¨λ
```
β λ§ λ³ μ¬μ© λμ
```
β Level 0: Kernel
β Level 1, 2: OS Service
β Level 3: Application Program
```
β λ κ°μ§ λͺ¨λ
```
β μ¬μ©μ λͺ¨λ (user mode): μμ© νλ‘κ·Έλ¨μ΄ μ¬μ©
β μ»€λ λͺ¨λ(kernel mode): OSκ° μ¬μ©
```
<br>

![ProtectionRing](./image/protection_ring.png)

<br>

## π Application Program and OS

β μ»€λ λͺ¨λμμλ§ μ€ν κ°λ₯ν κΈ°λ₯λ€μ΄ μμ<br>
β μ»€λ λͺ¨λλ‘ μ€ννλ €λ©΄, λ°λμ μμ€ν μ½μ μ¬μ©ν΄μΌν¨(κ±°μ³μΌ ν¨)<br>
β μμ€ν μ½μ μ΄μμ²΄μ  μ κ³΅<br>
<br>

![ApplicationProgramAndOs](./image/application_program_and_os.png)

<br>

## π μ¬μ©μ λͺ¨λμ μ»€λ λͺ¨λ

β ν¨λΆλ‘ μμ© νλ‘κ·Έλ¨μ΄ μ μ²΄ μ»΄ν¨ν° μμ€νμ ν€μΉμ§ λͺ»ν¨<br>
β μ£Όλ―Όλ±λ‘λ±λ³Έμ κΌ­ λμ¬λ¬΄μ λλ λ―Όμ24μ(μ λΆ μ¬μ΄νΈ)μμ νΉλ³ν μ μ²­μλ₯Ό μ¨μΌλ§ λ°κΈ
```
β λμ¬λ¬΄μ μ§μλΆλ€μ νΉλ³ν κΆνμ κ°μ§κ³ , μ£Όλ―Όλ±λ‘λ±λ³Έ μΆλ ₯ λͺλ Ήμ μ€ν
```

<br>

## π μ λ¦¬

β μ΄μμ²΄μ λ μμ€ν μ½ μ κ³΅<br>
β νλ‘κ·Έλλ° μΈμ΄λ³λ‘ μ΄μμ²΄μ  κΈ°λ₯μ νμ©νκΈ° μν΄, μμ€ν μ½μ κΈ°λ°μΌλ‘ API μ κ³΅<br>
β μμ© νλ‘κ·Έλ¨μ μ΄μμ²΄μ  κΈ°λ₯ νμμ, ν΄λΉ APIλ₯Ό μ¬μ©ν΄μ νλ‘κ·Έλ¨μ μμ±<br>
β μμ© νλ‘κ·Έλ¨μ΄ μ€νλμ, μ΄μμ²΄μ  κΈ°λ₯μ΄ νμν APIλ₯Ό νΈμΆνλ©΄, μμ€ν μ½μ΄ νΈμΆλμ, μ»€λλͺ¨λλ‘ λ³κ²½λμ΄ OS λ΄λΆμμ ν΄λΉ λͺλ Ήμ΄ μ€νλκ³ , λ€μ μμ© νλ‘κ·Έλ¨μΌλ‘ λμκ°λ€.<br>


<br>
<br>

---

##### π μ°Έκ³ κ°μοΌ[μ»΄ν¨ν° κ³΅ν μ κ³΅ νμ μ¬μΈμ ν¨ν€μ§ Online](https://fastcampus.co.kr/dev_online_cs)