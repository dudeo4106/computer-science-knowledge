# 🔑 Synchronization Issue And Semaphore

<br>

## 📌 Synchronization Issue

● 同期化: 作業の合間に実行時期を合わせること<br>
● 複数のスレッドが同じリソース(データ)アクセス時に同期化イシューが発生します。
```
○ 同一リソースを複数のスレッドが同時修正時、各スレッド結果に影響を与えます
```

<br>

## 📌 Synchronization Issue Solution

● Mutual exclusion 
● スレッドはプロセス全てのデータにアクセスできます。
```
○ 複数のスレッドが変更する共有変数に対してExclusive Accessが必要となります。
○ いずれのスレッドが共有変数を更新する間、他のスレッドが同時アクセスできないように防がなければなりません。
```

<br>

##📌 Mutual exclusion (相互排除)

● critical resource<br>
● critical section
```
lock.acquire()
for i in range(100000):
    g_count +=1
lock.release()
```

<br>

## 📌 Mutex And Semaphore

● Critical Sectionに対する接近を防ぐためにLOCKINGメカニズムが必要となります。
```
○ Mutex ( binary semaphore )
  : 臨界区域に1つのスレッドのみ入ることができます。
○ Semaphore
  : counterを置いて、同時にリソースにアクセスできる許容可能なスレッド数を制御します。
```

<br>

## 📌 Semaphore

● P: 検査（臨界領域に入るとき）
```
○ S値が1以上であれば、臨界領域入り後、S値1を引く（S値が0なら待機）
```
● V: 増加（臨界領域に出るとき）
```
○ S値を1足して、臨界領域を出ます。
```
● S: Semaphore Value(初期値だけ複数のプロセスが同時臨界領域に接近できます)
```
P(S): wait(S) {
    while S <= 0; // wait
        S--;      // limit access
}
```
```
V(S): signal(S) {
    S++; // allow access
}
```
● wakeup()関数により、待機キューにあるプロセスを再実行します。
```
signal(S) {
    S->count++;
    if (S->count > 0) {
        remove a process P from S->queue;
        wakeup(P)
    }
}
```

<br>

##📌 Semaphore - 忙しい待機。

● wait()はSが0なら、臨界領域に入るため、loop文修行します。
```
○ busy waiting
```
```
P(S): wait(S) {
    while S <= 0; // busy waiting
        S--;      // limit access
}
```

<br>

## 📌 Semaphore 待機キュー

> 運営体制技術で補完-待機キュー

● Sが負数の場合、忙しい待機の代わりに、待機キューに入れます。

```
wait(S) {
    S->count--;
    if (S->count <= 0) {
        add this process to S->queue;
        block()
    }
}
```

<br>

## 📌 参考: 主要セマポア関数(POSIX Semaphore)

● sem_open(): セマポアを生成<br>
● sem_wait(): 臨界領域接近前、セマフォアをロックして、セマポアがロックされていたら、解けるまで待機<br>
● sem_post（）: 共有資源へのアクセスが終わったとき、セマポアロックを削除します。

<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)