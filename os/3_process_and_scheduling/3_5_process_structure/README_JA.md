# ð Process Structure

<br>

â ãã­ã»ã¹ï¼processï¼ã¯ä¸è¬çã«ã©ã®ãããªæ§æã«ãªã£ã¦ããã®ã§ããããï¼
```
â TEXT: ã³ã¼ã
  - program code
  - fixed size
â DATA: å¤æ° / åæåããããã¼ã¿
  - initialized global and static variables
  - fixed size
â BSS: å¤æ° / åæåããã¦ããªããã¼ã¿
  - uninitialized global and static variables
  - fixed size
â HEAP: ã³ã¼ãããåçã«ä½ããããã¼ã¿
  - dynamic variables, managed by malloc(), free(), etc
  - fixed size
â STACK: è¨æãã¼ã¿(é¢æ°å¼ã³åºããã­ã¼ã«ã«å¤æ°ç­)
  - stack frames consisting of parameters, return addresses and local variables
  - variable size
```
â PC(Program Counter) + SP(Stack Pointer)<br>

<br>

## ð Heap
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

## ð PCB
> PCÂ·SPã¯ã©ãã«ä¿å­ãã¾ããï¼

â PCBã«ä¿å­ãã¦Process Context Blockã¨ãå¼ã°ãããã­ã»ã¹ãå®è¡ä¸­ã®ç¶æãã­ã£ããã£ / æ§é åãã¦ä¿å­ãã¾ãã
```
â Process ID
â Register Value(PC, SP, Etc)
â Scheduling Info(Process State)
â Memory Info (Memory Size Limit)
```

<br>

## ð PCB: EX) Linux

![PCB](./image/pcb.png)

<br>

### ð ã¾ã¨ã

â ãã­ã»ã¹æ§é 
```
â STACK
â HEAP
â DATA(BSS, DATA)
â TEXT(CODE)
```
â PCB
```
â ãã­ã»ã¹ã®ç¶ææå ±
- PC
- SP
- Memory
- Scheduling Info
```

<br>
<br>

---

ð åèè¬ç¾©ï¼[ã³ã³ãã¥ã¼ã¿ã¼å·¥å­¦å°æ»å¿é ãªã¼ã«ã¤ã³ã¯ã³ããã±ã¼ã¸Online](https://fastcampus.co.kr/dev_online_cs)