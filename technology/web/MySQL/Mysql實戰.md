# 安裝

```
Learning MySQL and MariaDB
Heading in the right direction with MySQL and MariaDB
```
# 基本環境及基本指令
```
Linux ==> ps	aux	|	grep	mysql

Windows  ==> tasklist	/fi	"IMAGENAME	eq	mysqld"

mysqladmin	-p	version	status

mysqld	-remove

If	MySQL	is	running	on	your	server,	but	not	as	a	service,	you	can	enter	the	following
within	a	command	window	to	shut	it	down:

msyqladmin	-u	root	-p	shutdown

PATH=%PATH%;C:\Program	Data\MySQL\MySQL	Server	version\bin
export	PATH


mysqld	--install
net	start	mysql
```

# 設定Post-Installation

```
Linux ==>	/etc/my.cnf
Windows ==>   c:\windows\my.ini	or	c:\my.cnf.	
```
### change	the	password	for	the	root	user	in	MySQL

```
mysqladmin	-u	root	-p	flush-privileges	password	"new_pwd"

mysql	-u	root	-p	-e	"SELECT	User,Host	FROM	mysql.user;"


mysql	-u	root	-p	-e	"SET	PASSWORD	FOR	'root'@'127.0.0.1'	PASSWORD('new_pwd');"
mysql	-u	root	-p	-e	"SET	PASSWORD	FOR	'root'@'localhost'	PASSWORD('new_pwd');"
mysql	-u	root	-p	-e	"DROP	USER	'root'@'%';"
mysql	-u	root	-p	-e	"DROP	USER	''@'localhost';"
```

# 我的第一堂Mysql
```
Connecting	to	the	Server ==> mysql	-u 使用者名稱	-p

mysql>

MariaDB	[(none)]>>

help

help	contents

help	Data	Manipulation

help	SHOW	DATABASES

```

### 資料庫操作 Databases
```
how	to	create	databases
add	data	to	them
run	queries	to find	interesting	relationships.	


SHOW	DATABASES;

The	test	database	is	initially	empty;	it	contains	no	tables.	

CREATE TABLE test.books	(book_id INT,	title TEXT,	status INT);

SHOW TABLES FROM test;

USE test;
SHOW	TABLES;
DESCRIBE	books;

INSERT INTO books VALUES(100,	'Heart	of	Darkness',	0);
INSERT INTO books VALUES(101,	'The	Catcher	of	the	Rye',	1);
INSERT INTO books VALUES(102,	'My	Antonia',	0);


SELECT	*	FROM	books;

SELECT	*	FROM	books	WHERE	status	=	1;

SELECT	*	FROM	books	WHERE	status	=	0	\G


UPDATE	books	SET	status	=	1	WHERE	book_id	=	102;

SELECT	*	FROM	books	WHERE	status	=	1;

UPDATE	books	SET	status	=	0	WHERE	book_id	=	101;
SELECT	*	FROM	books	WHERE	status	=	0;

UPDATE books
SET title	=	'The	Catcher	in	the	Rye',	status	=	1
WHERE book_id	=	101;

```
第二個範例
```
CREATE TABLE status_names	(status_id INT,	status_name CHAR(8));
INSERT INTO status_names VALUES(0,	'Inactive'),	(1,'Active');

SELECT	*	FROM	status_names;

SELECT	book_id,	title,	status_name
FROM	books	JOIN	status_names
WHERE	status	=	status_id;

```

