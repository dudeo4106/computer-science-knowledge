# ð TCP / IP Protocol Suite

> It was 4 layers, it has been updated to 5 layers

<br>

## ð Physical Layer

> bit â analog signal
> <br>
> analog signal â bit

7éå±¤ä¸­æä¸ä½ã®éå±¤ã§ãããä¸»ã«é»æ°çãæ©æ¢°çãªã©ã®ç¹æ§ãå©ç¨ãã¦ãã¼ã¿ä¼éãè¡ãã¾ãã<br>
ãã¼ã¿ã¯0ã1ã§ããï¼OnãOffï¼ãé»æ°çä¿¡å·ç¶æã§æ§æããã¦ãã¾ãã<br>
é»ç·ãä»ãã¦é»ç£æ°æ³¢ãéãé»æ°ä¿¡å·ãéåä¿¡ãã¾ãããé»ç·ã¯ãã¹ã¦ã®é»ç£æ°æ³¢ãééãããã¨ãã§ããªãããããã¼ã¿ã®æå¤±ãçºçãã¾ãã<br>
(å¨æ³¢æ°ã¯ 0~ç¡éå¤§ã®å¨æ³¢æ°ç¯å²ãæã£ã¦ãã¾ãã®ã§)<br>

éä¿¡èã¯ãã®ãããªæå¤±ãªããã¼ã¿ãéãããã«ã¯ã¢ãã­ã°ä¿¡å·ã«å¤æãã¦éä¿¡ãã¾ãï¼encodingï¼<br>
åä¿¡èã¯ã¢ãã­ã°ä¿¡å·åä¿¡å¾ã0ã¨1ã§è§£æãã¦ä½¿ç¨ãã¾ããï¼decodingï¼<br>

ãã®ããã«å¤æããã¢ã¸ã¥ã¼ã«ã¯ãPHYãããã¨ããååã§ãã¼ãã¦ã§ã¢çã«ä½ããã¦ãã¾ãã

<br>

## ð Data Link Layer

> frame

èª¬æã«åç«ã¡ãè¤æ°å°ã®ã³ã³ãã¥ã¼ã¿ãéä¿¡ããããã«ã¯ãã«ã¼ã¿ï¼L3ã¹ã¤ããï¼ã«è¤æ°å°ã®ã³ã³ãã¥ã¼ã¿ãã¤ãªãããããä¸ã¤ã®ãããã¯ã¼ã¯ã¨ããã¾ãã<br>
ãã®ããã«ãã«ã¼ã¿ã§ã¤ãªãã£ãè¤æ°ã®ãããã¯ã¼ã¯ã1ã¤ã«ã¤ãªãã¨ã¤ã³ã¿ã¼ãããã¨å¼ã°ãã¾ãã<br>

éä¿¡å´ã§ã¯ãç¹å®ã®ã³ã³ãã¥ã¼ã¿ã¨ãã¼ã¿éä¿¡ãããããã«ã¯ãããã«é£ã®ãããã¯ã¼ã¯ï¼ã«ã¼ã¿ï¼ã ããèãã¾ãã<br>
ãããªãã¨ãç®çå°ï¼ç¹å®ã³ã³ãã¥ã¼ã¿=ç¹å®IPï¼ã¾ã§ç´è¿ã®ãããã¯ã¼ã¯ãçµç±ããªããéä¿¡ãé²ãããã«ãªãã¾ãã<br>

åä¿¡å´ã§ã¯ã01010101010ãã¨ãããã¼ã¿ãæ¥ãã¨ãå¨é¨ã§ããã¤ãã®ãã½ã³ã³ãããã¼ã¿ãå±ããããããã®ãã¼ã¿ã®å§ã¾ãã¨çµãããåããã¾ããã<br>
ãã®ããããã¼ã¿ã®ä¸çªåã«ç¹å®ã®æ°å­(header)ããæå¾ã«ç¹å®ã®æ°å­(tail)ãè¿½å ãããã¨ã§ããã¼ã¿ã®å§ã¾ãã¨çµãããç¹å®ãã¦ãã¼ã¿ãæ­£ç¢ºã«åé¡ã§ãã¾ãã<br>

æ´çãã¾ãã¨ãç´æ¥é£çµãããç°ãªã2ã¤ã®ãããã¯ã¼ã­ã³ã°è£ç½®éã®ãã¼ã¿éä¿¡ãæå½ããéä¿¡ããããã¼ã¿ãframeã¨ããã¾ãã<br>
ãã®éå±¤ã§ã¯ãã­ãã³ã«ã®ç¨éã«å¿ãã¦frameã®ç¨®é¡ãé·ããªã©ã®æå ±ãå®ç¾©ãã¾ãã<br>
MACã¨ããåªä½ã¢ã¯ã»ã¹å¶å¾¡æ©è½ãããã48ãããã®ã¢ãã¬ã¹ãæã£ã¦ãã¾ãã<br>

æå¾ã«ããã®éå±¤ã¯Lan cardã§ããã1éå±¤ã¨åæ§ã«ãã¼ãã¦ã§ã¢çã«ä½ããã¦ãã¾ãã

<br>

## ð Internet Layer

> packet

ç¹å®ã®ã³ã³ãã¥ã¼ã¿ã«ãã¼ã¿ãéãããã«ã¯IPã¢ãã¬ã¹ãç¥ãå¿è¦ãããã¾ãã<br>
ãã¼ã¿ã¨å¯¾è±¡ã³ã³ãã¥ã¼ã¿ã®IPã¢ãã¬ã¹ãªã©ã®æå ±ããæ±ºããããã«ã¼ã«éãã«åå²ããã¦éä¿¡ãã¾ããããã®åä½ããã±ããã¨ããã¾ãã<br>
ãã®ãã±ããã¯æ°å¤ãã®ã«ã¼ã¿ãçµç±ããªããï¼routingï¼ç¹å®ã³ã³ãã¥ã¼ã¿ã«ãã¼ã¿ãä¼éãããã¨ã«ãªãã¾ãã<br>

ãã±ããã®ä»çµã¿ã§ãã
1. ãã¼ã¸ã§ã³: IPv4 vs IPv6
2. TTL(Time to Live):ãããã¯ã¼ã¯ä¸ã«æ®ãæéã§ãããã«ã¼ã¿ããªãããã¨ã§ã«ã¦ã³ã¿ã¼ãæ¸å°ããã¾ãã
3. Protocol: TCP vs UDP
4. ãã±ãã ãããã¼ ãã§ãã¯ãµã : éè¤æ¤æ»ã®ä¸å½¢æã§éä¿¡ãããè³æã®æ´åæ§ãä¿è­·ããæ¹æ³ã§ããããããã¼ãç ´æãã¦ããªãå ´åã¯ãã±ãããè¯å¥½ã¨ã¿ãªãã¾ãã
5. ã½ã¼ã¹ã¢ãã¬ã¹:ãããã¯ã¼ã¯ã«éä¿¡ããè£ç½®ã®IP Addressã§ãã
6. å¯¾è±¡ã¢ãã¬ã¹:ãã±ãããéä¿¡ãããã¢ãã¬ã¹
7. ãã¼ã¿ã§ãã

æ´çããã¨ãè«ççã¢ãã¬ã¹ããã¨ã«ãã±ããã®éä¿¡çµè·¯ãæ±ºå®ããå½¹å²ãæããã¾ããï¼routingï¼ã<br>
ãã¼ã¿ããã±ããåä½ã«åå²ãã¦è»¢éããåçµåãããå½¹å²ãæãããï¼ãã±ããã«ã¯è«çã¢ãã¬ã¹ãå«ã¾ãã¦ãã¾ãï¼

æå¾ã«ããã®éå±¤ã¯OSã®ã«ã¼ãã«ã«ã½ããã¦ã§ã¢çã«å®è£ããã¦ãã¾ãã

[è¿½å ]

|Protocol Example|
|---|
|IP|
|ICMP|
|ARP|
|...|

<br>

## ð Transport Layer

> segment(tcp) / datagram(udp)

ãããã¯ã¼ã¯éå±¤ã¯ãã±ããã®è»¢éãæå½ãã¾ãããæé©çµè·¯ã®æ¢ç´¢ãå­å¨ã®æç¡ããã±ããã®æå·ç­ã®åé¡ãæ°ã«ãã¾ããã<br>
ãã±ãããåä¿¡ã³ã³ãã¥ã¼ã¿ã«æ­£ããå°çããããããã±ããè»¢éãå¶å¾¡ããå½¹å²ã¯ãè»¢ééå±¤ãæããã

ãã¼ã¿è»¢éã®ããã«Portçªå·ãä½¿ç¨ããã¾ãã<br>
ãã¼ãçªå·ã¯ãä¸ã¤ã®ã³ã³ãã¥ã¼ã¿ã§åæã«å®è¡ããã¦ãããã­ã»ã¹ãäºãã«éãªããªãããã«æã¤ã¹ãæ´æ°å¤ãæå³ãã¾ãã
éä¿¡èã¯ãã¼ã¿ãéãæããã¼ã¿ãåä¿¡èã®ãã­ã»ã¹ã®Portçªå·ãè²¼ã£ã¦éããªããã°ãªãã¾ããã<br>

æ´çããã¨ãéä¿¡éå±¤ããã¯ã³ã³ãã¥ã¼ã¿åã«ããã¢ããªã±ã¼ã·ã§ã³ã®éä¿¡ãæå½ããéä¿¡ãããã¨ããã¢ããªã±ã¼ã·ã§ã³éã«ä»®æ³é£çµéè·¯ãä½ããæ¥ç¶ãç¢ºç«ããä½æ¥­ã§ãã<br>
ãããã¯ã¼ã¯éå±¤ã¯IP(ã³ã³ãã¥ã¼ã¿)ã«ãã¼ã¿ãéãã®ã§ããã°ãä¼ééå±¤ã¯Port çªå·ãä½¿ç¨ãã¦ã³ã³ãã¥ã¼ã¿ã®ä¸­ã®åä¿¡ãåããç¹å®ã®ã¢ããªã±ã¼ã·ã§ã³ãè­å¥ã§ããããã«ãã¦ããã¾ãã

æå¾ã«ããã®éå±¤ã¯OSã®ã«ã¼ãã«ã«ã½ããã¦ã§ã¢çã«å®è£ããã¦ãã¾ãã

[è¿½å ]

|Protocol Example|
|---|
|TCP|
|UDP|
|...|

## ð Application Layer

> message, data

èª¬æã«åç«ã¡ãOSI7Layerã¯æ¦å¿µçã¢ãã«ã§ãç¾ä»£ã®ã¤ã³ã¿ã¼ãããã¯OSIã¢ãã«ã§ã¯ãªãTCP/IPã¢ãã«ã«å¾ã£ã¦ãã¾ãã<br>
OSI 7 Layerã¯ãSessionãPresentationãApplication Layerã«åé¢ãããå½¢å¼ãä½¿ç¨ãã¾ããã<br>
TCP/IPã¢ãã«ã¯Application Layerã«çµ±åãã¦ä½¿ç¨ãã¾ãã

ãã®éå±¤ã¯ãä»ã®éå±¤ã®ãµã¼ãã¹ã«ã¢ã¯ã»ã¹ã§ããã¢ããªã±ã¼ã·ã§ã³ãæä¾ãããã¼ã¿äº¤æã®ããã«ä½¿ç¨ããããã­ãã³ã«ãå®ç¾©ãã¾ãã<br>
ä¾ãã°ãTCP/IP ã½ã±ãããã­ã°ã©ãã³ã°ãããã¾ãã<br>
OSã®Transport layerãæä¾ããAPIãæ´»ç¨ãã¦éä¿¡å¯è½ãªãã­ã°ã©ã ãä½ããã¨ã§ã<br>
ã½ã±ãããã­ã°ã©ãã³ã°ãéãã¦èª°ã§ãèªåã ãã®Application Layerã«ã¨ã³ã³ã¼ãã¨ãã³ã¼ããä½ããã¨ãã§ãã¾ãã

ç§ãã¡ãããè³ã«ãããã­ãã³ã«ã«ã¯ãã®éå±¤ããã, ãã­ãã³ã«ã®ç¨®é¡ã¯æ¬¡ã®éãã§ã

|Protocol Example|
|---|
|HTTP|
|FTP|
|Telnet|
|DNS|
|...|

<br>
<br>

---

ð åè : <br>
[https://www.youtube.com/watch?v=1pfTxp25MA8](https://www.youtube.com/watch?v=1pfTxp25MA8)
<br>
[https://jhnyang.tistory.com/373](https://jhnyang.tistory.com/373)
<br>
[https://enlqn1010.tistory.com/9](https://enlqn1010.tistory.com/9)
<br>
[https://better-together.tistory.com/134](https://better-together.tistory.com/134)
<br>
[https://goitgo.tistory.com/25](https://goitgo.tistory.com/25)
<br>
[https://devowen.com/344](https://devowen.com/344)
