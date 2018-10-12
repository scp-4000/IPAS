
```

```

列出所有連接埠： $ netstat -a

列出所有 TCP 連接埠： $ netstat -at

列出所有 UDP 連接埠： $ netstat -au

列出所有連線的 IP:  $ netstat -l

列出所有 TCP 連線的 IP: $ netstat -lt

列出所有 UDP 連線的 IP: $ netstat -lu
列出所有 UNIX LISTENING 連接埠:

$ netstat -lx
顯示以通訊協定分類的統計資訊，預設會以 TCP, UDP, IMCP 及 IP 分類：

$ netstat -s
顯示 TCP 的統計資訊：
$ netstat -st

顯示 UDP 的統計資訊：

$ netstat -su
顯示 Kernel IP routing

$ netstat -r
顯示網路卡的資訊

$ netstat -i
列出有監聽連接埠的程式，以下以 http 為例：

$ netstat -ap | grep http
