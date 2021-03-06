# ð Page Replacement Algorithm

<br>

## ð page replacement policy

> ã©ã®ãã¼ã¸ãç©çã¡ã¢ãªã¼ãããä¿å­åªä½ã«ä¸ããã®ã§ããï¼ - > Page Replacement ( Swapping ) Algorithm

â ãªãã¬ã¼ãã£ã³ã°ã·ã¹ãã ãç¹å®ã®ãã¼ã¸ãç©çã¡ã¢ãªã¼ã«ä¸ãããã¨ãããã§ãããç©çã¡ã¢ãªã¼ãè©°ã¾ã£ã¦ãããã©ãã§ããã
```
â åºæ¬ãã¼ã¸ã®ãã¡ä¸ã¤ãç©çã¡ã¢ãªããä¿å­åªä½ã¸ä¸ãã¾ãã
â æ°ãããã¼ã¸ãè©²å½ç©çã¡ã¢ãªç©ºéã«è¼ãã¾ãã
```

<br>

## ð FIFO

â First In First Out Page Replacement Algorithm
```
â ä¸çªæ©ã å¥ã£ã¦ãã ãã¼ã¸ã ä¸ãã¾ãããã
```

<br>

## ð OPT

â Optimal Page Replacement Algorithm
```
âããããä¸çªé·ãéãä½¿ç¨ããªããã¼ã¸ãéããã¾ãããã
âä¸è¬OSã§ã¯å®è£ã§ãã¾ãã
```

<br>

## ð LRU

â Least Recently Used Page Replacement Algorithm
```
â ä¸çªåã«ä½¿ç¨ããããã¼ã¸ãæ´æ°ãã¾ãã
â OPTå¥ãæ¿ãã¢ã«ã´ãªãºã ãå®è£ã§ãã¾ããã®ã§ãéå»è¨é²ãåºã«ãã£ã¬ã³ã¸ãã¾ãã
```

<br>

## ð LFU

â Least Frequently Used Page Replacement Algorithm
```
â ä¸çªå°ãªãä½¿ããããã¼ã¸ãä¸ãã¾ãããã
```

<br>

## ð NUR

â Not Used Frequently Page Replacement Algorithm
```
â LRUã¨åæ§ãæè¿ä½¿ããã¦ããªããã¼ã¸ããåãæ¿ããææ³
â åãã¼ã¸ãã¨ã«åç§ãããï¼Rï¼ãä¿®æ­£ãããï¼Mï¼ãç½®ããï¼RãMï¼
  - (0, 0)ã (0, 1)ã (1, 0)ã (1, 1)ã®é ã«ãã¼ã¸ãäº¤ä»£ãã¾ãã
```

<br>

## ð Thrashing

â ç¹°ãè¿ããã¼ã¸ãã©ã¼ã«ããçºçãã¦ãéåº¦ã«ãã¼ã¸ã®å¥ãæ¿ãä½æ¥­ãèµ·ãããå®éã«ã¯ä½ãã§ããªãç¶æ³<br>

![Thrashing](./image/thrashing.png)<br>

<br>
<br>

---

ð åèè¬ç¾©ï¼[ã³ã³ãã¥ã¼ã¿ã¼å·¥å­¦å°æ»å¿é ãªã¼ã«ã¤ã³ã¯ã³ããã±ã¼ã¸Online](https://fastcampus.co.kr/dev_online_cs)