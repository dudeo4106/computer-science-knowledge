# ๐ Segmentation

<br>

## ๐ segmentation technique - 1

โ ๊ฐ์ ๋ฉ๋ชจ๋ฆฌ๋ฅผ ์๋ก ํฌ๊ธฐ๊ฐ ๋ค๋ฅธ ๋ผ๋ฆฌ์  ๋จ์์ธ segment๋ก ๋ถํ 
```
โ ํ์ด์ง ๊ธฐ๋ฒ์์๋ ๊ฐ์ ๋ฉ๋ชจ๋ฆฌ๋ฅผ ๊ฐ์ ํฌ๊ธฐ์ ๋ถ๋ก์ผ๋ก ๋ถํ 
โ ์: x86 ๋ฆฌ์ผ๋ชจ๋
  - CS(Code Segment), DS(Data Segment), SS(Stack Segment), ES(Extra Segment)๋ก ๋๋์ด ๋ฉ๋ชจ๋ฆฌ ์ ๊ทผ
```

<br>

## ๐ segmentation technique - 2

โ segment virtual address
```
โ v = (s, d): s๋ ์ธ๊ทธ๋จผํธ ๋ฒํธ, d๋ ๋ธ๋ก ๋ด ์ธ๊ทธ๋จผํธ์ ๋ณ์
```

![Segmentation](./image/segmentation.png)<br>

<br>

## ๐ segmentation technique - 3

โ segmentation์ ํฌ๊ธฐ๊ฐ ๋ค๋ฅธ segment ๋จ์๋ก ๋ฌผ๋ฆฌ ๋ฉ๋ชจ๋ฆฌ์ ๋ก๋ฉ<br>

![SegmentationAndPaging](./image/segmentation_and_paging.png)<br>

<br>

## ๐ ์ฐธ๊ณ 

โ ๋ด๋ถ ๋จํธํ (paging)
```
โ ํ์ด์ง ๋ธ๋ก๋งํผ ๋ฐ์ดํฐ๊ฐ ๋ฑ ๋ง๊ฒ ์ฑ์์ ธ ์์ง ์์ ๋ ๊ณต๊ฐ ๋ญ๋น
```
โ ์ธ๋ถ ๋จํธํ (segmentation)
```
โ ๋ฌผ๋ฆฌ ๋ฉ๋ชจ๋ฆฌ๊ฐ ์ํ๋ ์ฐ์๋ ํฌ๊ธฐ์ ๋ฉ๋ชจ๋ฆฌ๋ฅผ ์ ๊ณตํด์ฃผ์ง ๋ชปํ๋ ๊ฒฝ์ฐ
```
โ segmentation / paging ๋ชจ๋ ํ๋์จ์ด ์ง์ ํ์
```
โ ๋ค์ํ ์ปดํจํฐ ์์คํ์ ์ด์์ฑ์ ์ค์ํ๋ ๋ฆฌ๋์ค๋ ํ์ด์ง ๊ธฐ๋ฒ์ ๊ธฐ๋ฐ์ผ๋ก ๊ตฌํ
```

<br>
<br>

---

##### ๐ ์ฐธ๊ณ ๊ฐ์๏ผ[์ปดํจํฐ ๊ณตํ ์ ๊ณต ํ์ ์ฌ์ธ์ ํจํค์ง Online](https://fastcampus.co.kr/dev_online_cs)