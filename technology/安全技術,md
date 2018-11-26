# Honoypot

web蜜罐、ssh蜜罐、網路通訊協定棧蜜罐到系統主機型蜜罐

```
基于Docker的蜜罐平台搭建：T-Pot 17.10 枫夜丶2018-08-03
https://www.freebuf.com/sectool/178998.html


T-Pot 平臺整合了以下docker容器：

conpot：低交互工控蜜罐，提供一系列通用工業控制協議, 能夠類比複雜的工控基礎設施。

cowrie：基於kippo更改的中交互ssh蜜罐, 可以對暴力攻擊帳號密碼等記錄，並提供偽造的檔案系統環境記錄駭客操作行為, 
並保存通過wget/curl下載的檔以及通過SFTP、SCP上傳的檔。

dionaea：Dionaea是運行於Linux上的一個應用程式，將程式運行於網路環境下，它開放Internet常見服務的預設埠，
當有外來連接時，類比正常服務給予回饋，同時記錄下出入網路資料流程。
網路資料流經由檢測模組檢測後按類別進行處理，如果有 shellcode 則進行模擬執行；
程式會自動下載 shellcode 中指定或後續攻擊命令指定下載的惡意文件。

elasticpot：類比elastcisearch RCE漏洞的蜜罐，通過偽造函數在/,/search, /nodes的請求上回應脆弱ES實例的JSON格式消息。
elk-stack：ELK架構，可以同時實現日誌收集、日誌搜索和日誌分析的功能。
emobility：Kibana視覺化的外掛程式，能建立更美觀的Dashboard。
ewsposter：資料分析工具ewsposter，將蜜罐資料進行關聯。

glastopf：低交互型Web應用蜜罐, Glastopf蜜罐它能夠模擬成千上萬的web漏洞，針對攻擊的不同攻擊手段來回應攻擊者，
然後從對目標Web應用程式的攻擊過程中收集資料。
它的目標是針對自動化漏洞掃描/利用工具，通過對漏洞利用方式進行歸類，針對某一類的利用方式返回對應的合理結果，以此實現低交互。
honeytrap：觀察針對TCP或UDP服務的攻擊，作為一個守護程式類比一些知名的服務，並能夠分析攻擊字串，執行相應的下載檔案指令。

mailoney：SMTP的蜜罐。
netdata：web端設備性能的即時監控工具。
portainer：web端docker容器管理工具。
rdpy：python搭建的遠程桌面蜜罐。
spiderfoot：web端的一個自動化爬蟲工具。
suricata & p0f：網路安全監控引擎和指紋識別系統。
vnclowpot：vnc服務的低交互蜜罐。
Wetty：web端的SSH控制台。
```
