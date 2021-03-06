# ð IPC Technique

<br>

## ð pipe

â åºæ¬ãã¤ãã¯ååéä¿¡<br>
â fork()ã§å­ãã­ã»ã¹ãä½æããã¨ããè¦ªå­éã®éä¿¡
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

â åºæ¬ãFIFOããªã·ã¼ã§ãã¼ã¿è»¢é<br>
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

â message queueã¯è¦ª/å­ã§ã¯ãªããã©ã®ãã­ã»ã¹ã§ããã¼ã¿ã®éåä¿¡ãå¯è½<br>
â åã«å¥ãããã¼ã¿ããåèª­ã¿ã«ãªãã<br>

<br>

## ð pipe vs message queue

â è¦ª/å­ãã­ã»ã¹éonly or not<br>
â çæ¹åã®ã¿å¯è½ or ä¸¡æ¹åå¯<br>

<br>

## ð IPCææ³ã¨ã«ã¼ãã«ã¢ã¼ãã

â pipeãmessage queue ã¯ãã¹ã¦kernel ç©ºéã®ã¡ã¢ãªãä½¿ç¨ãã¾ãã<br>

![IPCKernelSpace](./image/ipc_kernel_space.png)

<br>

## ð shared memory

âé²éª¨ã«kernel spaceã«ã¡ã¢ãªç©ºéãä½ããè©²å½ç©ºéãå¤æ°ã®ããã«ä½¿ãæ¹å¼<br>
âmessage queueã®ããã«FIFOæ¹å¼ã§ã¯ãªããè©²å½ã¡ã¢ãªã¢ãã¬ã¹ãã¾ãã§å¤æ°ã®ããã«æ¥è¿ããæ¹å¼<br>
âå±æã¡ã¢ãªã­ã¼ãæã¡ãè¤æ°ã®ãã­ã»ã¹ãã¢ã¯ã»ã¹å¯è½<br>

![IPCSharedMemory](./image/ipc_shared_memory.png)

<br>

## ð Shared Memory Code Example

â 1. å±æã¡ã¢ãªçæåã³å±æã¡ã¢ãªã¢ãã¬ã¹ãåå¾
```
shmid = shmget((key_t)1234, SIZE, IPC_CREAT|0666))
shmaddr = shmat(shmid, (void *)0, 0)
```
â 2. å±æã¡ã¢ãªã«æ¸ãè¾¼ã¿
```
strcpy((char *) shmaddr, "Linux Programming")
```
â 3. å±æã¡ã¢ãªã§èª­ã
```
printf("%s\n", (char *)shmaddr)
```

<br>

## ð ã¾ã¨ã

â ä¸»ãªIPCææ³
```
â pipe
â message queue
â shared memory
```
â ããããã«ã¼ãã«ç©ºéãæ´»ç¨ãã¦ãã­ã»ã¹éã®ãã¼ã¿å±æ<br>

<br>
<br>

---

ð åèè¬ç¾©ï¼[ã³ã³ãã¥ã¼ã¿ã¼å·¥å­¦å°æ»å¿é ãªã¼ã«ã¤ã³ã¯ã³ããã±ã¼ã¸Online](https://fastcampus.co.kr/dev_online_cs)