# 
```
ip -4 a
```
#
```
wireshark &

```
# hping3
```
https://man.linuxde.net/hping3
https://man.linuxde.net/hping3
```
### hping3 syn flood攻擊
```
hping3 -S -p 80 --flood 10.0.2.8

```
###
```
http://www.ha97.com/4093.html

匹配（match）：符合指定的條件，比如指定的 IP 位址和埠。

丟棄（drop）：當一個包到達時，簡單地丟棄，不做其它任何處理。
接受（accept）：和丟棄相反，接受這個包，讓這個包通過。
拒絕（reject）：和丟棄相似，但它還會向發送這個包的源主機發送錯誤消息。這個錯誤消息可以指定，也可以自動產生。

目標（target）：指定的動作，說明如何處理一個包，比如：丟棄，接受，或拒絕。

跳轉（jump）：和目標類似，不過它指定的不是一個具體的動作，而是另一個鏈，表示要跳轉到那個鏈上。

規則（rule）：一個或多個匹配及其對應的目標。

鏈（chain）：每條鏈都包含有一系列的規則，這些規則會被依次應用到每個遍歷該鏈的資料包上。
            每個鏈都有各自專門的用途， 這一點我們下面會詳細討論。
表（table）：每個表包含有若干個不同的鏈，比如 filter 表默認包含有 INPUT，FORWARD，OUTPUT 三個鏈。
          iptables有四個表，分別是：raw，nat，mangle和filter，
          每個表都有自己專門的用處，比如最常用filter表就是專門用來做包過濾的，
          nat 表是專門用來做NAT的。

策略（policy）：我們在這裡提到的策略是指，對於 iptables 中某條鏈，當所有規則都匹配不成功時其默認的處理動作。

連接跟蹤（connection track）：又稱為動態過濾，
           可以根據指定連接的狀態進行一些適當的過濾，是一個很強大的功能，但同時也比較消耗記憶體資源。
```
### iptables的系統架構
```
https://help.ubuntu.com/community/Firewall

                      GUFW
                      UFW
                      iptables

Linux kernel =====   netfilter子模組 
```
### iptables的封包處理流程

### UFW:好用的iptables前端
```
Uncomplicated Firewall
不複雜的防火牆
指令不但好記，寫好的規則也淺顯易懂，不會像 iptables 的裹腳布又臭又長

https://noob.tw/ufw/

大部分的 Ubuntu 系統應該都已經裝好 ufw。
如果你是 Debian(Kali)，或是什麼特別瘦身版的 Ubuntu 的話，可以透過以下指令安裝：
sudo apt-get install ufw

設定防火牆預設規則
[1]如果你想要規則嚴一點，可以預設封鎖所有通訊埠，再選擇性打開幾個 port
[2]你也可以預設開放所有 port，然後再封鎖幾個 port

預設允許/封鎖的指令如下：
sudo ufw default allow # 預設允許
sudo ufw default deny # 預設封鎖
```
```

1. 啟用和停用防火牆
下面這一行指令會啟用防火牆功能，而且，之後的每次開機都會自動載入和啟用的，要注意的是，
如果沒有特別的設定的話，ufw 在啟用後，預設是會關閉所有的連入要求的哩 !

$ sudo ufw enable

如果要停用的話，則是用下面這一行，一旦停用後，也會同時停止在開機後自動載入的哩 !

$ sudo ufw disable


2. 允許和關閉連入
下面的第一行指令會讓所有的連入要求都通過，等於防火牆對別台電腦的連接要求都接受的意思，而第二行指令則是不允許任何的連入要求，至於要用那一種，就要看你是先全部都打開再各別設定要封鎖的服務還是全部都先關閉，然後，再依需要來個別開通囉 !

$ sudo ufw default allow
$ sudo ufw default deny


3. 新增防火牆規則
下面幾種是常用的規則新增方式，都可適用在 deny 和 allow 的操作上。

$ sudo ufw allow ssh  ( 使用服務名稱來允許連入，服務名稱請參考 /etc/services 檔案 )
$ sudo ufw allow  in 8080   ( 使用 Port 號來允許連入 )
$ sudo ufw deny out 4662  ( 使用 Port 號來拒絕連出到別台電腦的指定 Port 號 )
$ sudo ufw deny in 4662/udp ( 使用 Port 號來拒絕接受指定 Port 號的 UDP 連入要求 )


4. 刪除規則防火牆規則
要刪除現有的規則的話，會比較麻煩一點點，因為，為了要能精準的刪除指定規則，
所以，就需要明確的指出要刪除的規則的編號是多少，
因此，可以要先用下面的第一行的指令的來查詢規則的編號，然後，才能用第三行的指令方式來刪除規則哩 !

$ sudo ufw status numbered

$ sudo ufw delete 規則號碼


5. 啟用日誌記錄
如果想知道防火牆到底有沒有用或是規則有沒有達到效果的話，可以用下面的指令來啟用日誌功能，
在啟用後，ufw 會把記錄寫到 /var/log/ufw.log 日誌檔。

$ sudo ufw logging on

6. 檢視規則和狀態
除了前面提到的「status numbered」選項之外，
ufw 還提供有下面二種選項來供查看 ufw 的規則和狀態哩 !

sudo ufw status
sudo ufw status verbose
```

### GUFW:圖形介面的UFW
```
https://help.ubuntu.com/community/Gufw
```
```
sudo apt-get install gufw
```
```
The available options for rules are Allow, Deny, Reject, and Limit:
Gufw防火牆有4種政策：允許，否認，拒絕，限制。

[1]Allow允許：將允許訪問The system will allow entry traffic for a port.
[2]Deny否認：會否認訪問The system will deny entry traffic to a port.
[3]Reject拒絕：將否認訪問，並通知對方電腦已被拒絕The system will deny entry traffic to a port and will inform the requesting for connection system that it has been rejected.
[4]Limit限制：如果特定IP嘗試幾個連接，那麼否認其訪問。
The system will deny connections if an IP address has attempted 
to initiate 6 or more connections in the last 30 seconds.
```
### iptables指令與參數
```
快速阻擋一組IP(1.2.3.4/32)的所有連線：

$ iptables -A INPUT -s 1.2.3.4/32 -j DROP

常用參數：
--append   -A :(預設`INPUT`, `FORWARD`, `OUTPUT`)新增規則到某個規則鏈中，該規則將會成為規則鏈中的最後一條規則
--source   -s :IP soruce
--protocol -p :protocal
--dport       :目的Port，指服務Port (`--destination-port`)
--jump     -j :目標規則 (`ACCEPT`, `DROP`)

https://code.yidas.com/iptables-guide/
```
```
http://icodding.blogspot.com/2015/07/iptables.html

iptables [-t table] command [match] [-j target/jump]
-t 參數用來指定規則表
內建的規則表有三個，分別是：nat、mangle 和 filter
當未指定規則表時，則一律視為是 filter。

[1]nat 規則表
擁有 Prerouting 和 postrouting 兩個規則鏈
主要功能為進行一對一、一對多、多對多等網址轉譯工作（SNATDNAT）
由於轉譯工作的特性，需進行目的地網址轉譯的封包，就不需要進行來源網址轉譯，反之亦然，
因此為了提升改寫封包的率，在防火牆運作時，每個封包只會經過這個規則表一次。
如果我們把封包過濾的規則定義在這個數據表裡，將會造成無法對同一包進行多次比對，因此這個規則表除了作網址轉譯外，請不要做其它用途。
 
[2]mangle 規則表擁有 Prerouting、FORWARD 和 postrouting 三個規則鏈。
除了進行網址轉譯工作會改寫封包外，在某些特殊應用可能也必須去改寫封包（TTL、TOS）或者是設定 MARK（將封包作記號，以進行後續的過濾），
這時就必須將這些工作定義在 mangle 規則表中，由於使用率不高，我們不打算在這裡討論 mangle 的用法。
 
[3]filter 規則表
預設規則表
擁有 INPUT、FORWARD 和 OUTPUT 三個規則鏈，
這個規則表顧名思義是用來進行封包過濾的理動作（例如：DROP、 LOG、 ACCEPT 或 REJECT），我們會將基本規則都建立在此規則表中。
```
```
常用命令列表：http://icodding.blogspot.com/2015/07/iptables.html

命令 -A, --append
範例 iptables -A INPUT ...
說明 新增規則到某個規則鏈中，該規則將會成為規則鏈中的最後一條規則。

命令 -D, --delete
範例 iptables -D INPUT --dport 80 -j DROP
iptables -D INPUT 1
說明 從某個規則鏈中刪除一條規則，可以輸入完整規則，或直接指定規則編號加以刪除。

命令 -R, --replace
範例 iptables -R INPUT 1 -s 192.168.0.1 -j DROP
說明 取代現行規則，規則被取代後並不會改變順序。


命令 -I, --insert
範例 iptables -I INPUT 1 --dport 80 -j ACCEPT
說明 插入一條規則，原本該位置上的規則將會往後移動一個順位。


命令 -L, --list
範例 iptables -L INPUT
說明 列出某規則鏈中的所有規則。


命令 -F, --flush
範例 iptables -F INPUT
說明 刪除某規則鏈中的所有規則。


命令 -Z, --zero
範例 iptables -Z INPUT
說明 將封包計數器歸零。封包計數器是用來計算同一封包出現次數，是過濾阻斷式攻擊不可或缺的工具。


命令 -N, --new-chain
範例 iptables -N allowed
說明 定義新的規則鏈。


命令 -X, --delete-chain
範例 iptables -X allowed
說明 刪除某個規則鏈。


命令 -P, --policy
範例 iptables -P INPUT DROP
說明 定義過濾政策。 也就是未符合過濾條件之封包，預設的處理方式。


命令 -E, --rename-chain
範例 iptables -E allowed disallowed
說明 修改某自訂規則鏈的名稱。
```
```
IPTables 指令參數
處理 iptables 規則時常用到如下參數：
-h：help information。
-V：顯示 iptables 版本。
-I：將規則插入至最前面 or 加上號碼插入指定處。
-A：將規則插入至最後面。
-R：取代指定的規則 (加上規則號碼)。
-D：刪除指定的規則 (加上規則號碼)。
-F：刪除所有的規則。

處理 iptables 規則鏈(chain)時常用到如下參數
-N：建立新的規則鏈(chain)。
-X：刪除指定的規則鏈(chain)。
-E：更改指定的規則鏈(chain)名稱。
-P：變更指定規則鏈(chain)的政策 (ex. policy for DROP、REJECT、ACCEPT)。
-Z：將 iptables 計數器歸零。

查看目前 iptables 規則時常用到如下參數
-L：列出目前 iptables 規則 (會執行 DNS 位址解析)。
-n：不使用 DNS 解析直接以 IP 位址顯示。
-v：顯示目前 iptables 規則處理的封包數。
-x：顯示完整封包數 (例如，顯示 1151519，而不是 12M)

http://www.weithenn.org/2017/05/centos-68-journey-part10.html
```
# iptables實戰

### iptables實戰 1: 阻絕ICMP ping

```
不想讓所有人ping到你。

sudo iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
```


```
你有一連串討厭的人，不想和他們連線

那我們最好另外開一條chain來管理所有你討厭的人

sudo iptables -N BLACKLIST              # 在Filter這個預設table下開一條新的chain叫做BLACKLIST

sudo iptables -A BLACKLIST  -s 140.113.235.151 -d 你自己的IP -j REJECTED  # 加入兩個你討厭的人
sudo iptables -A BLACKLIST  -s 140.113.235.152 -d 你自己的IP -j REJECTED

sudo iptables -A INPUT -j BLACKLIST  # 讓所有進入的封包都要經過BLACKLIST chain進行比對
```





```

```


```

```
### 1. 限制每個IP連接HTTP最大並發50個連接數
```
iptables -A INPUT -p tcp --dport 80 -m connlimit --connlimit-above 50 -j REJECT
```
### 2. 限制每個IP同時最多100個連接數
```
iptables -I INPUT -p tcp --syn --dport 80 -m connlimit --connlimit-above 100 -j REJECT

or

iptables -I INPUT -p tcp --syn --dport 80 -m connlimit ! --connlimit-above 100 -j ACCEPT
```
### 3. 限制每組C Class IP同時最多100個連接數
```
iptables -I INPUT -p tcp --syn --dport 80 -m connlimit --connlimit-above 100 --connlimit-mask 24 -j REJECT
```
### 4. 限制每個IP同時5個80 port轉發，超過的丟棄
```
iptables -I FORWARD -p tcp --syn --dport 80 -m connlimit --connlimit-above 5 -j DROP
```
### 5. 每秒最多允許5個新連接封包數
```
iptables -A INPUT -p tcp --syn -m limit --limit 1/s --limit-burst 5 -j ACCEPT
```
### 6. 防止各種端口掃描
```
iptables -A INPUT -p tcp --tcp-flags SYN,ACK,FIN,RST SYN -m limit --limit 1/s -j ACCEPT
```
### 7. 只要是來自內網的 (192.168.100.0/24) 的封包通通接受
```
iptables -A INPUT -i eth1 -s 192.168.100.0/24 -j ACCEPT
```
### 8. 只要是來自 192.168.100.10 就接受
```
iptables -A INPUT -i eth1 -s 192.168.100.10 -j ACCEPT
```
### 9. 連線進入本機 port 21 的封包都抵擋掉
```
iptables -A INPUT -i eth0 -p tcp --dport 21 -j DROP
```
### 10. Ping of Death
```
iptables -A INPUT -p icmp --icmp-type echo_request -m limit --limit 1/s -j ACCEPT
```
### 11. NMAP FIN/URG/PSH
```
iptables -A INPUT -p tcp --tcp-flags ALL FIN,URG,PSH -j LOG --log-level warn

iptables -A INPUT -p tcp --tcp-flags ALL FIN,URG,PSH -j DROP
```
### 12. Xmas Tree
```
iptables -A INPUT -p tcp --tcp-flags ALL ALL -j LOG --log-level warn

iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP
```
### 13. Another Xmas Tree
```
iptables -A INPUT -p tcp --tcp-flags ALL SYN,RST,ACK,FIN,URG -j LOG --log-level warn

iptables -A INPUT -p tcp --tcp-flags ALL SYN,RST,ACK,FIN,URG -j DROP
```
### 14. Null Scan(possibly)
```
iptables -A INPUT -p tcp --tcp-flags ALL NONE -j LOG --log-level warn

iptables -A INPUT -p tcp --tcp-flags ALL NONE -j DROP
```
### 15. SYN/RST
```
iptables -A INPUT -p tcp --tcp-flags ALL SYN,RST SYN,RST -j LOG --log-level warn

iptables -A INPUT -p tcp --tcp-flags ALL SYN,RST SYN,RST -j DROP
```
### 16. SYN/FIN --Scan(possibly)
```
iptables -A INPUT -p tcp --tcp-flags ALL SYN,FIN SYN,FIN -j LOG --log-level warn

iptables -A INPUT -p tcp --tcp-flags ALL SYN,FIN SYN,FIN -j DROP
```
### 17. Prevent Sync Flood (New Chain:SYNFLOOD)
```
iptables -N SYNFLOOD

iptables -A SYNFLOOD -p tcp --syn -m limit --limit 1/s -j RETURN

iptables -A SYNFLOOD -p tcp -j LOG --log-level alert

iptables -A SYNFLOOD -p tcp -j REJECT --reject-with tcp-reset

iptables -A INPUT -p tcp -m state --state NEW -j SYNFLOOD
```
### 18. Prevent Ping Flood ATTACK (New Chain:PING)
```
iptables -N PING

iptables -A PING -p icmp --icmp-type echo-request -m limit --limit 1/s -j RETURN

iptables -A PING -p icmp -j LOG --log-level alert

iptables -A PING -p icmp -j REJECT

iptables -A INPUT -p icmp --icmp-type echo-request -m state --state NEW -j PING
```
