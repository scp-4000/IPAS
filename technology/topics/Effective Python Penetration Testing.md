### Effective Python Penetration Testing 有效的PYTHON滲透測試技術

https://www.packtpub.com/networking-and-servers/effective-python-penetration-testing

# 使用Python2

# 你會學到甚麼(What You Will Learn)
```
Write Scapy scripts to investigate network traffic
Get to know application fingerprinting techniques with Python
Understand the attack scripting techniques
Write fuzzing tools with pentesting requirements
Learn basic attack scripting methods
Utilize cryptographic toolkits in Python
Automate pentesting with Python tools and libraries
```
# 章節內容
```
1: PYTHON SCRIPTING ESSENTIALS
Setting up the scripting environment
Installing third-party libraries
Python language essentials


2: ANALYZING NETWORK TRAFFIC WITH SCAPY(超強的網站工具)
Sockets modules
Raw socket programming
Investigate network traffic with Scapy


3: APPLICATION FINGERPRINTING WITH PYTHON
Web scraping
Parsing HTML with lxml
OS fingerprinting
Get the EXIF data of an image
Web application fingerprinting


4: ATTACK SCRIPTING WITH PYTHON===使用PYTHON攻擊網站
Injections
Broken authentication
Cross-site scripting (XSS)
Insecure direct object references
Security misconfiguration
Sensitive data exposure
Missing function level access control
CSRF attacks
Using components with known vulnerabilities
Unvalidated redirects and forwards


5: FUZZING(模糊測試) AND BRUTE-FORCING(暴力攻擊)
Fuzzing
Classification of fuzzers
Fuzzing and brute-forcing passwords
Dictionary attack
SSH brute-forcing
SMTP brute-forcing
Brute-forcing directories and file locations
Brute-force cracking password protected ZIP files


6: DEBUGGING AND REVERSE ENGINEERING
Reverse engineering
Portable executable analysis
Listing all imported and exported symbols
Disassembling with Capstone
PEfile with Capstone
Debugging
Using PyDBG


7: CRYPTO, HASH, AND CONVERSION FUNCTIONS 加密 解密
Cryptographic algorithms
Hash functions


8: KEYLOGGING鍵盤側錄 AND SCREEN GRABBING螢幕側錄
Keyloggers
Keyloggers with pyhook
Screen grabbing


9: ATTACK AUTOMATION自動化攻擊技術
Paramiko
python-nmap
W3af REST API
Metasploit scripting with MSGRPC
ClamAV antivirus with Python
OWASP ZAP from Python
Accessing Nessus 6 API with Python

10: LOOKING FORWARD更多PYTHON寫成的工具
Pentestly
Twisted
Nscan
sqlmap
CapTipper
Immunity Debugger
pytbull
ghost.py
peepdf
```

# 第三章:Application Fingerprinting with Python
```
Web scraping
Parsing HTML with lxml
OS fingerprinting
Get the EXIF data of an image
Web application fingerprinting
```
### 常用模組
```
Use urllib/urllib2 to create an HTTP request that will fetch the webpage, and using BeautifulSoup to parse the HTML
To parse an entire website we can use Scrapy, which helps to create web spiders
Use requests module to fetch and lxml to parse
```
### 使用urllib模組:headers.py
```
import urllib
url = urllib.urlopen("http://packtpub.com/")
response_headers = url.info()
#print response_headers
#print response_headers.keys()
print response_headers['server']
```

### 使用requests模組
```
import requests
response = requests.get("http://packtpub.com", parms)

# Response
print response.status_code # Response Code
print response.headers # Response Headers
print response.content # Response Content

# Request
print response.request.headers # Headers we sent
```
### 使用BeautifulSoup模組: Parsing HTML using BeautifulSoup

butifulSoapExamples.py
```
from bs4 import BeautifulSoup
import re

parse = BeautifulSoup('<html><head><title>Title of the page</title></head><body><p id="para1" align="center">This is a paragraph<b>one</b><a href="http://example1.com">Example Link 1</a> </p><p id="para2">This is a paragraph<b>two</b><a href="http://example.2com">Example Link 2</a></p></body></html>')

print parse.prettify()
```
### 使用lxml模組: Parsing HTML with lxml
```
#!/bin/python
#Importing modules
from lxml import html
import requests
import itertools

response = requests.get('http://packtpub.com/')
tree = html.fromstring(response.content)
#Create the list of Books:
books = tree.xpath('//div[@class="book-block-title"]/text()')


print books
```


