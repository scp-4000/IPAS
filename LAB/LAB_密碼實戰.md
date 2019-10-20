# Hash

```
import hashlib
md5hasher = hashlib.md5()
md5hasher.hexdigest()
'd41d8cd98f00b204e9800998ecf8
```
```
import hashlib
md5hasher = hashlib.md5(b'alice')
md5hasher.hexdigest()
```
```
import hashlib
hashlib.md5(b'alice').hexdigest()
hashlib.sha1(b'alice').hexdigest()
hashlib.sha256(b'alice').hexdigest()
```

# 作業


### 計算底下的MD5
```
b'alice' (again)
b'bob' (again)
b'balice'
b'cob'
b'a'
b'aa'
b'aaaaaaaaaa' (ten copies of the letter “a”)
b'a'*100000 (100,000 copies of the letter “a”)
```
### 上網去Google 查看看底下MD5的本文為何?
```
https://md5.gromweb.com/?md5=5f4dcc3b5aa765d61d8327deb882cf99
password
```
```
1. 5f4dcc3b5aa765d61d8327deb882cf99
2. d41d8cd98f00b204e9800998ecf8427e
3. 6384e2b2184bcbf58eccf10ca7a6563c
```
# 破密工具
```


```
### 密碼學

```
Cryptography with Python Tutorial

https://www.tutorialspoint.com/cryptography_with_python/index.htm
```
```

Practical-Cryptography
Encryption and Decryption Algorithms for various ciphers in Python:
http://www.allitebooks.org/practical-cryptography-in-python/
```
```
https://github.com/IronVenom/Practical-Cryptography


Encoding Schemes
Base64 ( with singular and double padding. )

Substitution Ciphers
Simple Substitution Cipher
Caesar Cipher
ROT13 Cipher
Atbash Cipher
Baconian Cipher
Cracking Ciphers: Cryptanalysis
Caesar Cipher
```
```

https://cryptobook.nakov.com/
https://github.com/nakov/Practical-Cryptography-for-Developers-Book

```
```
Practical Cryptography in Python
Learning Correct Cryptography by Example

https://www.apress.com/gp/book/9781484248997
http://www.allitebooks.org/practical-cryptography-in-python/
```
