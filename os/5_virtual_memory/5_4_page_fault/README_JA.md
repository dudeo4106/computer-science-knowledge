# 🔑 Page Fault

<br>

## 📌 what is page fault?

● 32bitシステムで4KBページのためのページングシステムとは？<br>
● オペレーティングシステムがpage faultが起きたら、該当ページを物理メモリにアップロードします。<br>

<br>

## 📌 page fault and interrupt

![PageFaultFlow](./image/page_fault_flow.png)

<br>

## 📌 ページングフォルトが頻繁に起きますと？

● 実行される前に、該当ページを物理メモリにアップロードしなければなりません。
```
○ 時間が長くかかります
```

<br>

## 📌 ページングフォルトが起きないようにするにはどうですか？

● 今後実行/参照されるコード/データを事前に物理メモリにアップロードしてください。
```
○ これからあることを予測しなければなりません-神の領域
```


<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)