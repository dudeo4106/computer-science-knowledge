# ð IPC Technique

<br>

## ð pipe

â ê¸°ë³¸ íì´íë ë¨ë°í¥ íµì <br>
â fork()ë¡ ìì íë¡ì¸ì¤ ë§ë¤ìì ë, ë¶ëª¨ì ììê°ì íµì 
```
char* msg = "Hello Child Process!";
int main()
{
    char buf[255];
    int fd[2], pid, nbytes;
    if (pipe(fd) < 0)
        exit(1);
    pid = fork();
    if (pid >0) {
        write(fd[1], msg, MSGSIZE);
        exit(0);
    }
    else {
        nbytes = read(fd[0], buf, MSGSIZE);
        print("%d %s\n", nbytes, buf);
        exit(0);
    }
    return 0;
}
```

<br>

## ð message queue

â ê¸°ë³¸ì FIFO ì ì±ì¼ë¡ ë°ì´í° ì ì¡<br>
â A process
```
msqid = msgget(key, msgflg)
msgsnd(msqid, &sbuf, buf_length, IPC_NOWAIT)
```
â B process
```
msqid = msgget(key, msgflg)
msgrcv(msqid, &rbuf, MSGSZ, 1, 0)
```

<br>

## ð pipe and message queue

â message queueë ë¶ëª¨ / ììì´ ìëë¼, ì´ë íë¡ì¸ì¤ ê°ìë¼ë ë°ì´í° ì¡ìì ì´ ê°ë¥<br>
â ë¨¼ì  ë£ì ë°ì´í°ê°, ë¨¼ì  ì½íì§ë¤.<br>

<br>

## ð pipe vs message queue

â ë¶ëª¨ / ìì íë¡ì¸ì¤ê° only or not<br>
â ë¨ë°©í¥ë§ ê°ë¥ or ìë°©í¥ ê°ë¥<br>

<br>

## ð IPC ê¸°ë²ê³¼ ì»¤ë ëª¨ë

â pipe, message queue ë ëª¨ë kernel ê³µê°ì ë©ëª¨ë¦¬ë¥¼ ì¬ì©í©ëë¤.<br>

![IPCKernelSpace](./image/ipc_kernel_space.png)

<br>

## ð shared memory

â ë¸ê³¨ì ì¼ë¡ kernel spaceì ë©ëª¨ë¦¬ ê³µê°ì ë§ë¤ê³ , í´ë¹ ê³µê°ì ë³ìì²ë¼ ì°ë ë°©ì<br>
â message queue ì²ë¼ FIFO ë°©ìì´ ìëë¼, í´ë¹ ë©ëª¨ë¦¬ ì£¼ìë¥¼ ë§ì¹ ë³ìì²ë¼ ì ê·¼íë ë°©ì<br>
â ê³µì ë©ëª¨ë¦¬ keyë¥¼ ê°ì§ê³ , ì¬ë¬ íë¡ì¸ì¤ê° ì ê·¼ ê°ë¥<br>

![IPCSharedMemory](./image/ipc_shared_memory.png)

<br>

## ð Shared Memory Code Example

â 1. ê³µì  ë©ëª¨ë¦¬ ìì± ë° ê³µì  ë©ëª¨ë¦¬ ì£¼ì ì»ê¸°
```
shmid = shmget((key_t)1234, SIZE, IPC_CREAT|0666))
shmaddr = shmat(shmid, (void *)0, 0)
```
â 2. ê³µì  ë©ëª¨ë¦¬ì ì°ê¸°
```
strcpy((char *) shmaddr, "Linux Programming")
```
â 3. ê³µì  ë©ëª¨ë¦¬ìì ì½ê¸°
```
printf("%s\n", (char *)shmaddr)
```

<br>

## ð ì ë¦¬

â ì£¼ì IPC ê¸°ë²
```
â pipe
â message queue
â shared memory
```
â ëª¨ë ì»¤ë ê³µê°ì íì©í´ì íë¡ì¸ì¤ê° ë°ì´í° ê³µì <br>

<br>
<br>

---

##### ð ì°¸ê³ ê°ìï¼[ì»´í¨í° ê³µí ì ê³µ íì ì¬ì¸ì í¨í¤ì§ Online](https://fastcampus.co.kr/dev_online_cs)