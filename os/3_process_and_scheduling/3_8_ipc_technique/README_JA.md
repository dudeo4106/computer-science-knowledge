# 🔑 IPC Technique

<br>

## 📌 pipe

● 基本パイプは単向通信<br>
● fork()で子プロセスを作成したとき、親子間の通信
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

## 📌 message queue

● 基本、FIFOポリシーでデータ転送<br>
● A process
```
msqid = msgget(key, msgflg)
msgsnd(msqid, &sbuf, buf_length, IPC_NOWAIT)
```
● B process
```
msqid = msgget(key, msgflg)
msgrcv(msqid, &rbuf, MSGSZ, 1, 0)
```

<br>

## 📌 pipe and message queue

● message queueは親/子ではなく、どのプロセスでもデータの送受信が可能<br>
● 先に入れたデータが、先読みになる。<br>

<br>

## 📌 pipe vs message queue

● 親/子プロセス間only or not<br>
● 片方向のみ可能 or 両方向可<br>

<br>

## 📌 IPC技法とカーネルモード。

● pipe、message queue はすべてkernel 空間のメモリを使用します。<br>

![IPCKernelSpace](./image/ipc_kernel_space.png)

<br>

## 📌 shared memory

●露骨にkernel spaceにメモリ空間を作り、該当空間を変数のように使う方式<br>
●message queueのようにFIFO方式ではなく、該当メモリアドレスをまるで変数のように接近する方式<br>
●共有メモリキーを持ち、複数のプロセスがアクセス可能<br>

![IPCSharedMemory](./image/ipc_shared_memory.png)

<br>

## 📌 Shared Memory Code Example

● 1. 共有メモリ生成及び共有メモリアドレスを取得
```
shmid = shmget((key_t)1234, SIZE, IPC_CREAT|0666))
shmaddr = shmat(shmid, (void *)0, 0)
```
● 2. 共有メモリに書き込み
```
strcpy((char *) shmaddr, "Linux Programming")
```
● 3. 共有メモリで読む
```
printf("%s\n", (char *)shmaddr)
```

<br>

## 📌 まとめ

● 主なIPC手法
```
○ pipe
○ message queue
○ shared memory
```
● いずれもカーネル空間を活用してプロセス間のデータ共有<br>

<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)