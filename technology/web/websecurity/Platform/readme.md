
```
PyREBox: a Python scriptable Reverse Engineering sandbox
Oct 11, 2018
```
```
[研究] Damn Vulnerable Web App (DVWA) 1.9 滲透測試平台安裝 (Windows 7)
http://shaurong.blogspot.com/2018/07/damn-vulnerable-web-app-dvwa-19-windows.html
 
[研究] OWASP Zed Attack Proxy (ZAP) v2.7.0 滲透測試、弱點掃描工具安裝與試用
http://shaurong.blogspot.com/2018/06/owasp-zed-attack-proxy-zap-v270.html

[研究] OWASP WebGoat 8.0、Webwolf 滲透測試安裝、啟動
http://shaurong.blogspot.com/2018/06/owasp-webgoat-80.html

[研究] bWAPP 2.2 bee-box v1.6.7 免費、網路漏洞滲透測試學習平台
http://shaurong.blogspot.com/2016/12/bwapp-22-bee-box-v167.html

[研究] OWASP WebGoatFor.Net 滲透測試練習平台安裝
http://shaurong.blogspot.com/2016/12/owasp-webgoatfornet.html

[研究] OWASP WebGoat 7.1 滲透測試學習平台安裝
http://shaurong.blogspot.com/2016/12/owasp-webgoat-71.html

```
### OWASP Mutillidae II
```
OWASP Mutillidae II 2.6.72 releases: OWASP Mutillidae II Web Pen-Test Practice Application
BY DO SON · PUBLISHED NOVEMBER 14, 2018 · UPDATED NOVEMBER 14, 2018

OWASP Mutillidae II is a free, open source, deliberately vulnerable web-application providing a target for the web-security enthusiast. Mutillidae can be installed on Linux and Windows using a LAMP, WAMP, and XAMMP. It is pre-installed on SamuraiWTF and OWASP BWA. The existing version can be updated on these platforms. With dozens of vulnerabilities and hints to help the user; this is an easy-to-use web hacking environment designed for labs, security enthusiast, classrooms, CTF, and vulnerability assessment tool targets. Mutillidae has been used in graduate security courses, corporate web sec training courses, and as an “assess the assessor” target for vulnerability assessment software.

Features
Has over 40 vulnerabilities and challenges. Contains at least one vulnerability for each of the OWASP Top Ten 2007, 2010 and 2013
Actually Vulnerable (User not asked to enter “magic” statement)
Mutillidae can be installed on Linux, Windows XP, and Windows 7 using XAMMP making it easy for users who do not want to install or administrate their own web server. Mutillidae is confirmed to work on XAMPP, WAMP, and LAMP.
Installs easily by dropping project files into the “htdocs” folder of XAMPP.
Will attempt to detect if the MySQL database is available for the user
Preinstalled on Rapid7 Metasploitable 2, Samurai Web Testing Framework (WTF), and OWASP Broken Web Apps (BWA)
Contains 2 levels of hints to help users get started
Includes bubble-hints to help point out vulnerable locations
Bubble-hints automatically give more information as hint level incremented
System can be restored to default with a single click of “Setup” button
User can switch between secure and insecure modes
Secure and insecure source code for each page stored in the same PHP file for easy comparison
Provides data capture page and stores captured data in database and file
Allows SSL to be enforced in order to practice SSL stripping
Used in graduate security courses, incorporate web sec training courses, 
     and as an “assess the assessor” target for vulnerability software

Mutillidae has been tested/attacked with Cenzic Hailstorm ARC, W3AF, SQLMAP, Samurai WTF, Backtrack, HP Web Inspect, Burp-Suite, NetSparker Community Edition, and other tools

Instructional Videos: http://www.youtube.com/user/webpwnized 
Updates tweeted to @webpwnized
Updated frequently
Project Whitepaper

Changelog v2.6.72
Added new vulnerability: LDAP injection
Added new page: conference-room-lookup.php
Added new page: ldap-injection-hint.inc
Added new page: ldap-config.inc
Updated vulerabilities.php
Renamed database-config.php to database-config.inc


Download:   git clone https://github.com/webpwnized/mutillidae.git
```
