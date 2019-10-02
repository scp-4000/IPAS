#
```
Mastering Linux Security and Hardening
Donald A. Tevault
January 11, 2018

1Running Linux in a Virtual Environment
2Securing User Accounts
3Securing Your Server with a Firewall
4Encrypting and SSH Hardening
5Mastering Discretionary Access Control
6Access Control Lists and Shared Directory Management
7Implementing Mandatory Access Control with SELinux and AppArmor
8Scanning, Auditing, and Hardening
9Vulnerability Scanning and Intrusion Detection
10Security Tips and Tricks for the Busy Bee
```
### 5.Mastering Discretionary Access Control
```
Using chown to change ownership of files and directories
Using chmod to set permissions values on files and directories
Using SUID and SGID on regular files
The security implications of the SUID and SGID permissions
Using extended file attributes to protect sensitive files
```
### 6.Access Control Lists and Shared Directory Management
```
Creating an access control list for either a user or a group
Creating an inherited access control list for a directory
Removing a specific permission by using an ACL mask
Using the tar --acls option to prevent the loss of ACLs during a backup
Creating a user group and adding members to it
Creating a shared directory
Setting the SGID bit and the sticky bit on the shared directory
Using ACLs to access files in the shared directory
```
### 8.Scanning, Auditing, and Hardening
```
Installing and updating ClamAV and maldet
Scanning with ClamAV and maldet
SELinux considerations
Scanning for rootkits with Rootkit Hunter
Controlling the auditd daemon
Creating audit rules
Using ausearch and aureport
Applying OpenSCAP policies with oscap
Using SCAP Workbench
More about OpenSCAP profiles
Applying an OpenSCAP profile during system installation
```
### 9.Vulnerability Scanning and Intrusion Detection
```
Looking at Snort and Security Onion
Scanning and hardening with Lynis
Finding vulnerabilities with OpenVAS
Web server scanning with Nikto
```
