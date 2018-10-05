
Use Low Orbit Ion Cannon (LOIC) to test the Snort

http://pages.mtu.edu/~xinlwang/itseed/labs/intrusion_detection_intro2Snort_LOIC.pdf

### snort運作模式:(三種模式)

https://s3.amazonaws.com/snort-org-site/production/document_files/files/000/000/129/original/snort_manual.pdf

>* Sniffer mode:傾(竊)聽模式
```
   simply reads the packets off of the network and displays them for you in a continuous stream on the console (screen).
   
   ./snort -v
   
   ./snort -vd
   
   ./snort -vde

```
>* Packet Logger mode: 封包紀錄而已logs the packets to disk.
```
./snort -dev -l ./log

./snort -dev -l ./log -h 192.168.1.0/24

./snort -l ./log -b

./snort -l ./log -b

./snort -dvr packet.log icmp
```
>* Network Intrusion Detection System (NIDS) mode:網路入侵偵測模式
```
performs detection and analysis on network traffic. 
This is the most complex and configurable mode.

./snort -dev -l ./log -h 192.168.1.0/24 -c snort.conf

./snort -d -h 192.168.1.0/24 -l ./log -c snort.conf

```

### Top five free enterprise network IDS/IPS tools[listed by Techtarget (2016)]: 
```
 Security Onion
 OSSEC
 Open WIPS-NG
 Suricata
 Bro IDS
```
snort

NIST SP800-94
Karen Scarfone, Peter Mell, 2007a, Guide to Intrusion Detection and Prevention Systems
(IDPS) [referred 22.02.2016]. Available in www-format: 
https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-94.pdf


https://s3.amazonaws.com/snort-org-site/production/document_files/files/000/000/129/original/snort_manual.pdf


