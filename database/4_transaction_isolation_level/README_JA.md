# ð Transaction Isolation Level

<br>

## ð What is transaction isolation level?

ãã©ã³ã¶ã¯ã·ã§ã³éé¢æ°´æºã¨ã¯ãåæã«è¤æ°ã®ãã©ã³ã¶ã¯ã·ã§ã³ãå¦çãããéã«ãç¹å®ã®ãã©ã³ã¶ã¯ã·ã§ã³ãä»ã®ãã©ã³ã¶ã¯ã·ã§ã³ã§å¤æ´ããåã¯ãã¼ã¿ãç§ä¼ã§ããããã«è¨±å¯ããããæ±ºå®ãããã¨<br>
ãã¼ã¿ãã¼ã¹ã¯ãACIDã®ç¹å¾´ã®ããã«ãã©ã³ã¶ã¯ã·ã§ã³ãç¬ç«çã«å®è¡ãããããã«Lockingãè¡ãããã©ã³ã¶ã¯ã·ã§ã³ã®é¢ä¸ãé²ãã¾ãã<br>

ããããç¡æ¡ä»¶ã«Lockingããã¦ãã©ã³ã¶ã¯ã·ã§ã³ãé åºã©ããã«å¦çããããã«ããã¨ãæ§è½ãä½ä¸ããæ§è½ã®ããLockingãè§£é¤ããã¨ãééã£ãå¤ãå¦çããã¦ãã¾ãå¯è½æ§ãããã¾ãã

ãã®ããå¹ççãªLockingæ¹æ³ãå¿è¦ã§ãã

<br>

## ð What is Lock?

Lockã¨ã¯ããã©ã³ã¶ã¯ã·ã§ã³å¦çã®é æ¬¡æ§ãä¿éããããã®æ¹æ³ã§ãããä¸ã¤ã®ãã©ã³ã¶ã¯ã·ã§ã³ãå®ç§ã«çµäºããã¾ã§ããã¼ã¿ã®å¤æ´ãåé¤ãç§ä¼ãé²æ­¢ãã¾ãã

<br>

## ð Shared Lock and Exclusive Lock

> Shared Lock

ãã¼ã¿ãèª­ã¿è¾¼ãã¨ãã«ä½¿ç¨ããã Lockã§ãããShared Lockã¯Shared Lockåå£«ã§åæã¢ã¯ã»ã¹ãå¯è½ã§ãã<br>
ã¤ã¾ãã1ã¤ã®ãã¼ã¿ãèª­ã¿è¾¼ããã¨ã§ããããè¤æ°ã®ã¦ã¼ã¶ãåæã«å¯è½ã§ãããShared Lockã«è¨­å®ããããã¼ã¿ã¯Exclusive Lockãä½¿ç¨ãããã¨ã¯ã§ããªãã

> Exclusive Lock

ãã¼ã¿ãå¤æ´ããã¨ãã«ä½¿ç¨ããããã©ã³ã¶ã¯ã·ã§ã³ãçµäºããã¾ã§ç¶­æããã¾ãã<br>
Exclusive Lockãè§£é¤ãããã¾ã§ãä»ã®ãã©ã³ã¶ã¯ã·ã§ã³(èª­ã¿è¾¼ã¿å«ã)ã¯ãè©²å½ãªã½ã¼ã¹ã«ã¢ã¯ã»ã¹ã§ãããä»ã®ãã©ã³ã¶ã¯ã·ã§ã³ãå®è¡ããã¦ãããã¼ã¿ã«ã¤ãã¦ã¯ãä¸ç·ã«Lockãè¨­å®ãããã¨ã¯ã§ãã¾ããã

<br>

## ð Lock Level

â Database: ãã¼ã¿ãã¼ã¹å¨ä½ã«Lockãè¨­å®ãããã¨ãæå³ãã1ã¤ã®ã»ãã·ã§ã³ã ãããã¼ã¿ã«ã¢ã¯ã»ã¹ã§ãã¾ãã<br>
â File: å®éã«ãã¼ã¿ãä½¿ãããç©ççãªãªãã¸ããªã«Lockãè¨­å®ãããã¨ãæå³<br>
â Table: Tableã¬ãã«ã®Lockè¨­å®ãæå³ãããã¼ãã«ã®ãã¹ã¦ã®è¡ãã¢ãããã¼ããããªã©ã®ããã¼ãã«å¨ä½ã«å½±é¿ãä¸ããå¤æ´ãè¡ãã¨ãã«ä¸»ã«ä½¿ç¨ããã¾ãã<br>
â PageãBlock: ãã¡ã¤ã«ã®ä¸é¨ã§ãããã¼ã¸ã¨Blockã«åºã¥ãã¦Lockãè¨­å®ãããã¨ãæå³ <br>
â Column: Columnãåºæºã«Lockãè¨­å®ãããã¨ãæå³ããLockè¨­å®ãããã¦è§£é¤æã«å¤ãã®ãªã½ã¼ã¹ãå¿è¦ãªãããä¸è¬çã«ä½¿ç¨ããªã<br>
â Row: æãä¸è¬çã«ä½¿ç¨ããã¦ããRowã¬ãã«ã®Lockã§ãããDMLã«å¯¾ããLock<br>

<br>

## ð Blocking

ãã­ãã­ã³ã°ã¯ãLock(Exclusive - Exclusive, Exclusive - Shared)ã®ç«¶åãçºçãã¦ãç¹å®ã®Transactionãä½æ¥­ãå®è¡ã§ããã«æ­¢ã¾ã£ãç¶æã®ãã¨ãããã¾ãã<br>
Shared Lockåå£«ã¯ãã­ãã­ã³ã°ãçºçããªãããExclusive Lockã¯ãã­ãã­ã³ã°ãçºçããã¾ãã<br>
ãã­ãã­ã³ã°ãè§£æ¶ããããã«ã¯ãä»¥åã®ãã©ã³ã¶ã¯ã·ã§ã³ãCommit or RollBackãããªããã°ãªããããã®ãããªç«¶åã¯æ§è½ãæªåãããããã«æå°åããªããã°ãªãã¾ããã<br>

è§£æ¶ã®ä»æ¹
- 1ã¤ã®ãã©ã³ã¶ã¯ã·ã§ã³ã®é·ããé·ãããããªãããã«ãã¾ãã
- åããã¼ã¿ãæ´æ°ãããã©ã³ã¶ã¯ã·ã§ã³ãåæã«å®è¡ãããªãããã«ããå¿è¦ãããã¾ãã
- Isolation Levelãä¸å¿è¦ã«ä¸åèª¿æ´ããã«ãã¯ã¨ãªã¼éè¡æéãç­ããã¾ãã

<br>

## ð DeadLock

ãã­ã»ã¹ããªã½ã¼ã¹ãå¾ãããã«æ¬¡ã®å¦çãã§ããªãç¶æã§ãã·ã¹ãã çã«éããããªã½ã¼ã¹ãè¤æ°ç®æã§ä½¿ç¨ãããã¨ããæã«çºç<br>

çºçããç¶æ³ã§ã¯ããã«ããã­ã°ã©ãã³ã°ç°å¢ã§éãããè³æºãä½¿ç¨ãããã¨ç«¶äºããç¶æ³ãçºçããå ´å<br>
ãããã­ã»ã¹ãæ¯æ´ãè¦è«ããæãã®æå»ã«ãã®ãªã½ã¼ã¹ãä½¿ç¨ã§ããªãç¶æ³ãçºçããã­ã»ã¹ãå¾æ©ç¶æã«ãªãã¾ãã<br>
å¾æ©ç¶æã«å¥ã£ããã­ã»ã¹ãå®è¡ç¶æã«å¤æ´ã§ããªãã¨ãDeadLockã¨ããã¾ãã

* è©³ç´°ã«ã¤ãã¦ã¯ãDeadLockãã¼ãã«ã¦åæ±ããããã¨ã«ãã¾ãã

<br>

## ð Isolation Levels

> Level 0 - READ UNCOMMITTED

ãå®ç¾©ã<br>
åãã©ã³ã¶ã¯ã·ã§ã³ã§ã®å¤æ´åå®¹ãCommitãRollbackã§ãããã©ããã«é¢ããããä»ã®ãã©ã³ã¶ã¯ã·ã§ã³ã§å¤ãèª­ããã¨ãã§ãã¾ãã<br>
ãã®ãããã¼ã¿ãã¼ã¹ã®ä¸è²«æ§ãä¿ã¤ãã¨ãä¸å¯è½ã§ãã<br>

ãåé¡ã<br>
READ UNCOMMITTEDã¬ãã«ãä½¿ç¨ããã¨ãDirty Readï¼ãã©ã³ã¶ã¯ã·ã§ã³ãå®äºããåã«ä»ã®ãã©ã³ã¶ã¯ã·ã§ã³ã§ã®ç§ä¼ãå¯è½ï¼ãçºçãã¾ãã

> Level 1 - Read Committedï¼Oracle DBã§åºæ¬çã«ä½¿ç¨ï¼

ãå®ç¾©ã<br>
ãã©ã³ã¶ã¯ã·ã§ã³ã®å¤æ´åå®¹ãCommitãRollbackãããªããã°ãä»ã®ãã©ã³ã¶ã¯ã·ã§ã³ã§ç§ä¼ã§ãã¾ããã<br>
å®éã®ãã¼ãã«å¤ãåå¾ããã®ã§ã¯ãªããUndoé åã«ããã¯ã¢ãããããã¬ã³ã¼ãããå¤ãåå¾ãã¾ãã

ãåé¡ã<br>
ã²ã¨ã¤ã®ãã©ã³ã¶ã¯ã·ã§ã³åã§åãSelectãå®è¡ããã¨ãã«ãå¸¸ã«åãçµæã§ãªããã°ãªããªãã¨ããRepeatable Readã®æ´åæ§ã«åãããã®ã§ãã<br>
1. Aãã©ã³ã¶ã¯ã·ã§ã³ã§1çªã®å­¦çã®å­¦å¹´ç§ä¼: 3å¹´ç
2. Bãã©ã³ã¶ã¯ã·ã§ã³ã§1çªã®å­¦çå­¦å¹´ã4ã«å¤æ´ãã¦ãã³ããã
3. Aãã©ã³ã¶ã¯ã·ã§ã³ã§1çªã®å­¦çã®å­¦å¹´ç§ä¼: 4å¹´ç

> Level 2 - Repeatable Readï¼MySQLã§åºæ¬çã«ä½¿ç¨ï¼

ãå®ç¾©ã<br>
ãã©ã³ã¶ã¯ã·ã§ã³ãéå§ãããåã«ãã³ããããããåå®¹ã«ã®ã¿ç§ä¼ãããã¨ãã§ãã¾ãã<br>
MySQLã§ã¯ããã©ã³ã¶ã¯ã·ã§ã³ã®IDãè¨­å®ãã¦ãã¾ããããã©ã³ã¶ã¯ã·ã§ã³IDããå°ãããã©ã³ã¶ã¯ã·ã§ã³çªå·ããå¤æ´ãããã®ã®ã¿ãèª­ãã®ã§ããããå®ç¾ããããã¨ãã§ãã¾ãã<br>
ã¾ããUndoç©ºéã«ããã¯ã¢ãããã¦ããã¦ãå®éã®ã¬ã³ã¼ãå¤ãå¤æ´ãã¾ãããããã¯ã¢ãããã¼ã¿ãä¸è¦ã ã¨å¤æ­ããæç¹ã§åé¤ããã¾ããã¾ããããã¯ã¢ãããããã¬ã³ã¼ããå¤ãã¨ãµã¼ãå´ã®å¦çæ§è½ãè½ã¡ããã¨ãããã¾ãã<br>

ãåé¡ã<br>
Phantom Readãçºçãã¾ãã<br>
ã²ã¨ã¤ã®ãã©ã³ã¶ã¯ã·ã§ã³ã®ä¸­ã§ã¬ã³ã¼ãã2åä»¥ä¸èª­ã¿è¾¼ãã¨ããæåã®ã¯ã¨ãªã«ã¯ãªãã£ãã¬ã³ã¼ãã2åç®ã®ã¯ã¨ãªã§è¡¨ç¤ºãããç¾è±¡ã§ãã<br>
ãããé²æ­¢ããããã«writeã­ãã¯ããããªããã°ãªãã¾ããã

> Level 3 - Serializable

ãå®ç¾©ã<br>
æãå³æ ¼ãªéé¢æ°´æºã§å®ç§ãªèª­ã¿è¾¼ã¿ã®ä¸è²«æ§ãæä¾ãã¾ãã<br>
ãã®ä¸è²«æ§ã¯ãä»ã®ã¦ã¼ã¶ã¼ããã©ã³ã¶ã¯ã·ã§ã³é åã«è©²å½ãããã¼ã¿ãä¿®æ­£Â·å¥åä¸è½ã«ããããã§ãã<br>
å·ä½çã«ã¯Serializableã®å ´åãèª­ã¿è¾¼ã¿ä½æ¥­ã«ãShared Lockãããä»ã®ãã©ã³ã¶ã¯ã·ã§ã³ã§ã¯è©²å½ã¬ã³ã¼ããå¤æ´ã§ããªããªãã¾ãã

ãåé¡ã<br>
å³æ ¼ã§ãããåæå¦çè½åãè½ã¡ã¦æ§è½ãä½ãã®ã§ã»ã¨ãã©ä½¿ç¨ããã¦ãã¾ããã

<br>

---

ð åè
<br>
[https://nesoy.github.io/articles/2019-05/Database-Transaction-isolation](https://nesoy.github.io/articles/2019-05/Database-Transaction-isolation)
<br>
[https://dar0m.tistory.com/225](https://dar0m.tistory.com/225)
<br>
[https://sabarada.tistory.com/121](https://sabarada.tistory.com/121)
<br>
[https://doooyeon.github.io/2018/09/29/transaction-isolation-level.html](https://doooyeon.github.io/2018/09/29/transaction-isolation-level.html)
<br>
[https://jwprogramming.tistory.com/12](https://jwprogramming.tistory.com/12)
<br>
