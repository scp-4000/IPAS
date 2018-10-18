### 
```
https://zh.wikipedia.org/wiki/PHP
http://docs.php.net/manual/tw/index.php

```
### 資料型態(data Type)
```
PHP 支援下列八種資料型態(data Type)

[1]純量資料型態(data Type)  (scalar type) 
整數  (integer) 
浮點數  (float、double) 
布林  (boolean) 
字串  (string) 
[2]特殊資料型態(data Type)  (special type) 
NULL 
資源  (resource)

[3]複合資料型態(compound type) 
陣列  (array) 
物件  (object) 
```
```
字串是由字母、數字、文字、符號所組合而成
在 PHP 中可以使用下列 4 種方法來表示：
1. 單引號 ( ' )：在字串的前後加上單引號 ( ' )，所包含的內容即為字串。
2. 雙引號 ( " )：在字串的前後加上雙引號 ( " )，所包含的內容即為字串。
3. heredoc 語法結構：以「<<<」符號後加上識別名，分行後再加上字串內容，最後以新的一行加上識別名結尾，字串中的變數會被視為變數編譯。
4. nowdoc 語法結構：建置的方式與heredoc 相同，不同的是識別名要加上單引號 ( ' )，字串中的變數不會被編譯而直接輸出。
```

### PHP的流程控制
```
PHP的流程控制分成下列兩種類型：
[1]判斷結構 (decision structures)
if (if...、if...else...、if...elseif...)
switch

[2]迴圈結構 (loop structures)
for
foreach
while
do...while
```
