# ๐ Inode and virtual file system

<br>

## ๐ inode file system

โ ํ์ผ ์์คํ ๊ธฐ๋ณธ ๊ตฌ์กฐ
```
โ super block: ํ์ผ ์์คํ ์ ๋ณด ๋ฐ ํํฐ์ ์ ๋ณด ํฌํจ
โ inode block: ํ์ผ ์์ธ ์ ๋ณด
โ data block: ์ค์  ๋ฐ์ดํฐ
```

<br>

## ๐ inode and file

โ file: inode ๊ณ ์ ๊ฐ๊ณผ ์๋ฃ๊ตฌ์กฐ์ ์ํด ์ฃผ์ ์ ๋ณด ๊ด๋ฆฌ
```
โ ํ์ผ์ด๋ฆ: inode๋ก ํ์ผ์ด๋ฆ์ inode ๋ฒํธ์ ๋งค์นญ
โ ํ์ผ ์์คํ์์๋ inode๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ํ์ผ ์์ธ์ค
โ inode ๊ธฐ๋ฐ ๋ฉํ ๋ฐ์ดํฐ ์ ์ฅ
```

![InodeAndFile](./image/inode_and_file.png)<br>

<br>

## ๐ inode structure

โ inode ๊ธฐ๋ฐ ๋ฉํ ๋ฐ์ดํฐ(ํ์ผ ๊ถํ, ์์ ์ ์ ๋ณด, ํ์ผ ์ฌ์ด์ฆ, ์์ฑ์๊ฐ๋ฑ ์๊ฐ ๊ด๋ จ ์ ๋ณด, ๋ฐ์ดํฐ ์ ์ฅ ์์น๋ฑ)

![InodeStructure](./image/inode_structure.png)

<br>

## ๐ inode structure and file

![InodeStructureAndFile](./image/inode_structure_and_file.png)

<br>

## ๐ inode structure and file data

![InodeStructureAndFileData](./image/inode_structure_and_file_data.png)

<br>

## ๐ directory entry(dentry)

โ Linux search file example: -/home/ubuntu/test.txt
```
โ 1. ๊ฐ ๋๋ ํ ๋ฆฌ ์ํธ๋ฆฌ๋ฅผ ํ์(๊ฐ ์ํธ๋ฆฌ๋ ํด๋น ๋๋ ํ ๋ฆฌ ํ์ผ/๋๋ ํ ๋ฆฌ ์ ๋ณด๋ฅผ ๊ฐ์ง๊ณ  ์์)
โ 2. '/' dentry์์ 'home'์ ์ฐพ๊ณ , 'home'์์ 'ubuntu'๋ฅผ ์ฐพ๊ณ , 'ubuntu'์์ test.txt ํ์ผ์ด๋ฆ์ ํด๋นํ๋ inode๋ฅผ ์ป์
```

<br>

## ๐ virtual file system

โ Network๋ฑ ๋ค์ํ ๊ธฐ๊ธฐ๋ ๋์ผํ ํ์ผ ์์คํ ์ธํฐํ์ด์ค๋ฅผ ํตํด ๊ด๋ฆฌ ๊ฐ๋ฅ<br>
โ ex) read/write ์์คํ์ฝ ์ฌ์ฉ, ๊ฐ ๊ธฐ๊ธฐ๋ณ read_spec/write_spec ์ฝ๋ ๊ตฌํ(os ๋ด๋ถ)<br>

![VirtualFileSystem](./image/virtual_file_system.png)

<br>

## ๐ linux(unix) os and virtual file system

โ ๋ชจ๋  ๊ฒ์ ํ์ผ์ด๋ผ๋ ์ฒ ํ์ ๋ฐ๋ฆ
```
โ ๋ชจ๋  ์ธํฐ๋ ์์ ํ์ผ์ ์ฝ๊ณ , ์ฐ๋ ๊ฒ์ฒ๋ผ ์ด๋ฃจ์ด์ ธ์์
โ ๋ง์ฐ์ค, ํค๋ณด๋์ ๊ฐ์ ๋ชจ๋  ๋๋ฐ์ด์ค ๊ด๋ จ๋ ๊ธฐ์ ๋ ํ์ผ๊ณผ ๊ฐ์ด ๋ค๋ฃจ์ด์ง
โ ๋ชจ๋  ์์์ ๋ํ ์ถ์ํ ์ธํฐํ์ด์ค๋ก ํ์ผ ์ธํฐํ์ด์ค๋ฅผ ํ์ฉ
```

<br>
<br>

---

##### ๐ ์ฐธ๊ณ ๊ฐ์๏ผ[์ปดํจํฐ ๊ณตํ ์ ๊ณต ํ์ ์ฌ์ธ์ ํจํค์ง Online](https://fastcampus.co.kr/devonlinecs)