# tshark
```
Wireshark Network Security
A succinct guide to securely administer your network using Wireshark
Piyush Verma Packt publishing
```

### To look at all the options that are available with tshark
```
tshark –h
```

### Starting the capture
```
To look at the available interfaces, we can run the following command:

tshark –D

```

```
select the interface you want to use and start capturing the traffic on that
interface (in this case, 2) by running the following command:

tshark –i 2


To stop manually, press the combination of Ctrl + C

To stop automatically, use –a option with a condition
tshark –i 2 –a duration:10
```


### use capture filters with tshark( –f option)
```
tshark –i 2 –f "port bootpc" –w DHCP_Only.pcap
```


###  use display filters with tshark( –R option)
```
tshark -2 –R "http.request.method==GET" –r HTTP_Traffic.pcap –w HTTP_Get.pcap

讀入HTTP_Traffic.pcap
使用http.request.method==GET display filter過濾出滿足條件的封包
將過濾後的封包寫入到HTTP_Get.pcap檔案
```


### Saving the capture to a file
```
tshark –i 2 –w FirstCapture.pcap
```



### 
```

```



### 
```

```



### 
```

```



