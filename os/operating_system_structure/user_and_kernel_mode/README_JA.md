# 🔑 ユーザーとカーネルモード

<br>

## 📌 CPU Protection Rings

● CPUも権限モードというものを持っています。
```
○ ユーザー モード(user mode by applications)です。
○ カーネルモード(kernel mode by OS): 特権コマンドの実行と目的の作業遂行のための資源アクセスを可能にするモードです。
```
● リングごとのご使用の対象です。
```
○ Level 0: Kernel
○ Level 1, 2: OS Service
○ Level 3: Application Program
```
●二つのモードです
```
○ ユーザーモード(user mode): アプリケーションが使用します
○ カーネルモード(kernel mode): OSが使用します。
```
<br>

![ProtectionRing](./image/protection_ring.png)

<br>

## 📌 Application Program and OS

● カーネルモードでのみ実行可能な機能があります<br>
● カーネルモードへ実行するには、必ずシステムコールを使用する必要があります<br>
● システムコールはオペレーティングシステムが提供<br>
<br>

![ApplicationProgramAndOs](./image/application_program_and_os.png)

<br>

## 📌 ユーザーモードとカーネルモードです。

● むやみにアプリケーションがが全体のコンピュータシステムを損ないません<br>
● 住民票は必ず区役所で特別な申請書を書かなければなりません
```
○ 役所の職員は特別な権限を持ち、住民票の出力命令を実行します。
```

<br>

### 📌 まとめ

● オペレーティングシステムは、システムコールの提供<br>
● プログラミング言語ごとにOS機能を活用するため、システムコールを基盤としてAPIを提供<br>
● 応用プログラムは、OS機能が必要な場合、当該APIを使ってプログラムを作成<br>
● アプリケーションが実行され、OS機能が必要なAPIを呼び出すと、システムコールが呼び出され、カーネルモードに変更され、OS内部でこの命令が実行され、再びアプリケーションに戻ります。<br>


<br>
<br>

---

📚 参考講義：[コンピューター工学専攻必須オールインワンパッケージOnline](https://fastcampus.co.kr/dev_online_cs)