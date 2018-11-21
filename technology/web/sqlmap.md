
### sqlmap選項
```
  目標:至少要選中一個參數
    -u URL, --url=URL   目標為 URL (例如. "http://www.site.com/vuln.php?id=1")
    -g GOOGLEDORK       將穀歌dork的結果作為目標url
  請求:
    這些選項可用於指定如何連接到目標URL
    --data=DATA         資料字元串通過POST發送
    --cookie=COOKIE     HTTP Cookie的值
    --random-agent      隨機選擇 HTTP User-Agent 頭的值
    --proxy=PROXY       使用代理去連接目標URL
    --tor               使用匿名網路
    --check-tor         檢查Tor是否正確使用
  注入:
    這些選項可用於指定要測試哪些參數，提供自訂注入負載和可選篡改腳本
    -p TESTPARAMETER    可測試的參數
    --dbms=DBMS         將後端DBMS強制到此值
  檢測:
    這些選項可用於定制檢測階段
    --level=LEVEL       執行的測試級別(1-5, 默認 1)
    --risk=RISK         執行測試的風險 (1-3, 默認 1)
  技術:
    這些選項可用於調整特定SQL注入的測試的技術
    --technique=TECH    SQL注入技術選擇 (默認 "BEUSTQ")
  枚舉:
    T這些選項可用於枚舉後端資料庫管理系統的資訊、結構和資料表。此外，還可以運行自己的SQL語句
    -a, --all           檢索全部
    -b, --banner        檢索 banner
    --current-user      檢索當前用戶
    --current-db        檢索當前資料庫
    --passwords         列出使用者密碼的hash值
    --tables            列出表
    --columns           列出欄位
    --schema            列出DBMS schema
    --dump              Dump DBMS資料庫表的條目
    --dump-all          Dump 所有DBMS資料庫表的條目
    -D DB               指定資料庫
    -T TBL              指定表
    -C COL              指定欄位
  作業系統訪問:
    這些選項可用於訪問後端資料庫管理系統底層作業系統
    --os-shell          提示為互動式作業系統shell
    --os-pwn            提示為OOB外殼，Meterpreter或VNC
  通用:
    這些選項可用於設置一些通用的工作參數
    --batch             永遠不要要求用戶輸入，使用默認行為
    --flush-session     刷新當前目標的會話檔
  雜項:
    --sqlmap-shell      提示輸入互動式sqlmap shell
    --wizard            初學者的簡單嚮導介面
```
