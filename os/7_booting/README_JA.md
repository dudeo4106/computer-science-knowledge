# 🔑 Booting

<br>

## 📌 what is file booting?

● パソコンをオンにして動作させる手続き<br>
● Boot Program
```
○ osカーネルをStorageから特定アドレスの物理メモリにコピーし、カーネルの最初の実行位置にProgram counterを読み込むプログラム
```

<br>

## 📌 booting process

● if you turn the computer on?
```
○ BIOSが特定のStorageを読み込み、bootstraploaderをメモリにアップロードして実行します。
○ bootstrap loaderプログラムがある場所を探して実行させます。
```

![Boot](./image/boot.png)<br>

<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)