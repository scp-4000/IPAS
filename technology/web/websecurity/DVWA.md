
# 

https://blog.csdn.net/qq_32400847/article/details/53697849

# dvwa安裝和使用指南
```
https://www.itread01.com/content/1502196979.html

```
### Owasp TOP 10[2010]
```
Owasp TOP 10 2010年發布的數據
The OWASP Top 10 Web ApplicationSecurity Risks for 2010 are:
A1: Injection // 註入漏洞
A2: Cross-Site Scripting (XSS) //跨站腳本
A3: Broken Authentication and Session Management //錯誤的授權和會話管理
A4: Insecure Direct Object References //不正確的直接對象引用
A5: Cross-Site Request Forgery (CSRF)//偽造跨站請求
A6: Security Misconfiguration//安全性錯誤配置
A7: Insecure Cryptographic Storage//不安全的加密存儲
A8: Failure to Restrict URL Access//未驗證的重定向和傳遞
A9: Insufficient Transport Layer Protection//不足的傳輸層防護
A10: Unvalidated Redirects and Forwards//無效的重定向和轉向
```
```
DVWA裏面具體包括如下這些漏洞:
1.暴力破解漏洞通過brute force登錄頁面進入到該漏洞的測試位置。這個漏洞是用來測試暴力破解工具和展示不安全的弱密碼。
2.命令執行漏洞在存在風險的系統上執行命令。
3.CSRF偽造跨站請求漏洞，允許攻擊者去修改應用的管理員密碼。
4.SQL註入，DVWA包括盲註和錯誤型註入兩種SQL註入漏洞類型。
5.不安全的文件上傳漏洞，允許攻擊者上傳惡意的文件到web服務器上
6.XSS跨站腳本漏洞，允許攻擊者註入他們自己的腳本到web服務器上。DVWA系統裏面包含了反射性XSS和存儲型XSS兩種類型。
7.文件包含漏洞，允許進行本地文件包含執行和遠程文件包含執行
8.驗證碼繞過（但由於驗證碼使用了google的，我們網絡太和諧，需要代理或者VPN連接，經過VPN環境測試，也不太靠譜）


6.DVWA的安全級別和漏洞位置說明

在DVWA上有三種安全級別分別是
High:在這個級別下所有有漏洞的代碼都被修補過了你可以通過查看源代碼來查看修補過的漏洞。
通過高級別漏洞代碼的查看可以跟低級別的代碼做一些對比從而讓安全人員更加深入的理解漏洞是怎麽出現的。
Medium中級別表示代碼已經被開發人員嘗試加固過了但是加固的不夠徹底因此漏洞還是存在。
這讓開發人員能夠跟進一步認識漏洞。同時對學習者來說因為這個漏洞加大了難度要拿下這個漏洞也是一個挑戰。
Low在個級別下所有的漏洞均沒有被修復過。你可以在這個級別下測試所有的漏洞。並且通過查看源代碼來了解漏洞是如何發生的。
```
