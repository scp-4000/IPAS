###

```
http://www.codedata.com.tw/database/mysql-tutorial-getting-started

http://books.gotop.com.tw/v_AED002900
https://github.com/macdidi5/MySQLTutorial
```

```
1.資料庫概論與 MySQL 安裝
2.SELECT 基礎查詢
3.運算式與函式
4.JOIN 與 UNION 查詢
5.CRUD 與資料維護
6.字元集與資料庫
7.儲存引擎與資料型態
8.表格與索引
9.子查詢
10.Views

11.Prepared Statements
12.Stored Routines入門
13.Sotred Routines的變數與流程
14.Stored Routines進階
15.Triggers
16.資料庫資訊
17.錯誤處理與查詢

18.匯入與匯出資料
19.效率

```

### 下載與安裝MySQL資料庫
```
http://www.codedata.com.tw/database/mysql-tutorial-database-abc-mysql-installation/

下載MySQL資料庫
https://dev.mysql.com/downloads/windows/installer/

使用MySQL Workbench資料庫管理系統來
安裝world範例資料庫與與cmdev範例資料庫
```

### MySQL Workbench資料庫管理系統

```
MySQL提供的工具軟體，在這幾年有很大的進步，目前已經把所有常用的軟體整合在一起，稱為MySQL Workbench，裡面包含：
SQL Development：SQL開發工具，讓使用者輸入並執行SQL敘述
Database Design Modeling：資料庫設計與模型工具
Database Administration：資料庫管理工具
Database Migration：資料庫轉換工具
```

### world範例資料庫

建立world資料庫:https://github.com/macdidi5/MySQLTutorial/blob/master/resources/world.sql
```
DROP DATABASE IF EXISTS world;

CREATE DATABASE world CHARACTER SET big5;

USE world;
```

建立world資料庫的各種資料表
```
建立各種資料表:
步驟1:建立資料表的綱要(Schema)
步驟2:建立資料表的內容(Data資料)

City資料表
Country資料表
CountryLanguage資料表
```

City資料表
```
DROP TABLE IF EXISTS `City`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `City` (
  `ID` int(11) NOT NULL AUTO_INCREMENT,
  `Name` char(35) NOT NULL DEFAULT '',
  `CountryCode` char(3) NOT NULL DEFAULT '',
  `District` char(20) NOT NULL DEFAULT '',
  `Population` int(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`ID`)
) ENGINE=MyISAM AUTO_INCREMENT=4080;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `City`
--
-- ORDER BY:  `ID`

INSERT INTO `City` VALUES (1,'Kabul','AFG','Kabol',1780000);
INSERT INTO `City` VALUES (2,'Qandahar','AFG','Qandahar',237500);
INSERT INTO `City` VALUES (3,'Herat','AFG','Herat',186800);

```

Country資料表
```
--
-- Table structure for table `Country`
--

DROP TABLE IF EXISTS `Country`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `Country` (
  `Code` char(3) NOT NULL DEFAULT '',
  `Name` char(52) NOT NULL DEFAULT '',
  `Continent` enum('Asia','Europe','North America','Africa','Oceania','Antarctica','South America') NOT NULL DEFAULT 'Asia',
  `Region` char(26) NOT NULL DEFAULT '',
  `SurfaceArea` float(10,2) NOT NULL DEFAULT '0.00',
  `IndepYear` smallint(6) DEFAULT NULL,
  `Population` int(11) NOT NULL DEFAULT '0',
  `LifeExpectancy` float(3,1) DEFAULT NULL,
  `GNP` float(10,2) DEFAULT NULL,
  `GNPOld` float(10,2) DEFAULT NULL,
  `LocalName` char(45) NOT NULL DEFAULT '',
  `GovernmentForm` char(45) NOT NULL DEFAULT '',
  `HeadOfState` char(60) DEFAULT NULL,
  `Capital` int(11) DEFAULT NULL,
  `Code2` char(2) NOT NULL DEFAULT '',
  PRIMARY KEY (`Code`)
) ENGINE=MyISAM;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `Country`
--
-- ORDER BY:  `Code`

INSERT INTO `Country` VALUES ('ABW','Aruba','North America','Caribbean',193.00,NULL,103000,78.4,828.00,793.00,'Aruba','Nonmetropolitan Territory of The Netherlands','Beatrix',129,'AW');

```


CountryLanguage資料表
```
--
-- Table structure for table `CountryLanguage`
--

DROP TABLE IF EXISTS `CountryLanguage`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `CountryLanguage` (
  `CountryCode` char(3) NOT NULL DEFAULT '',
  `Language` char(30) NOT NULL DEFAULT '',
  `IsOfficial` enum('T','F') NOT NULL DEFAULT 'F',
  `Percentage` float(4,1) NOT NULL DEFAULT '0.0',
  PRIMARY KEY (`CountryCode`,`Language`)
) ENGINE=MyISAM;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `CountryLanguage`
--
-- ORDER BY:  `CountryCode`,`Language`

INSERT INTO `CountryLanguage` VALUES ('ABW','Dutch','T',5.3);
INSERT INTO `CountryLanguage` VALUES ('ABW','English','F',9.5);
INSERT INTO `CountryLanguage` VALUES ('ABW','Papiamento','F',76.7);
```


### cmdev範例資料庫
```
DROP DATABASE IF EXISTS cmdev;

CREATE DATABASE cmdev CHARACTER SET big5;

USE cmdev;

DROP TABLE IF EXISTS emp;

CREATE TABLE emp (
  empno INT NOT NULL,
  ename VARCHAR(16) NOT NULL,
  job VARCHAR(16),
  manager INT,
  hiredate DATE,
  salary float(7, 2),
  comm float(7,2),
  deptno INT,
  PRIMARY KEY (empno)
);

INSERT INTO emp VALUES (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20);
INSERT INTO emp VALUES (7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30);
INSERT INTO emp VALUES (7521,'WARD','SALESMAN',7698,'1981-02-22',1250, 500,30);
INSERT INTO emp VALUES (7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20);
INSERT INTO emp VALUES (7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30);
INSERT INTO emp VALUES (7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,NULL);
INSERT INTO emp VALUES (7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,10);
INSERT INTO emp VALUES (7788,'SCOTT','ANALYST',7566,'1987-04-19',3000,NULL,20);
INSERT INTO emp VALUES (7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,10);
INSERT INTO emp VALUES (7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,0,30);
INSERT INTO emp VALUES (7876,'ADAMS','CLERK',7788,'1987-05-23',1100,NULL,20);
INSERT INTO emp VALUES (7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,NULL);
INSERT INTO emp VALUES (7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20);
INSERT INTO emp VALUES (7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);

DROP TABLE IF EXISTS dept;

CREATE TABLE dept (
  deptno INT NOT NULL,
  dname VARCHAR(16) NOT NULL,
  location VARCHAR(16),
  PRIMARY KEY (deptno)
);

INSERT INTO dept VALUES (10,'ACCOUNTING','NEW YORK');
INSERT INTO dept VALUES (20,'RESEARCH','DALLAS');
INSERT INTO dept VALUES (30,'SALES','CHICAGO');
INSERT INTO dept VALUES (40,'OPERATIONS','BOSTON');
INSERT INTO dept VALUES (50,'IT','NEW YORK');

DROP TABLE IF EXISTS travel;

CREATE TABLE travel (
  empno INT NOT NULL,
  location VARCHAR(16) NOT NULL,
  counter INT NOT NULL,
  PRIMARY KEY (empno, location)
);

INSERT INTO travel VALUES (7369,'CHICAGO',1);
INSERT INTO travel VALUES (7499,'DALLAS',1);
INSERT INTO travel VALUES (7521,'DALLAS',2);
INSERT INTO travel VALUES (7566,'BOSTON',1);
INSERT INTO travel VALUES (7654,'NEW YORK',1);


CREATE TABLE integertable (
  n TINYINT, 
  n2 SMALLINT, 
  n3 MEDIUMINT, 
  n4 INT, 
  n5 BIGINT
);

CREATE TABLE floatingable (
  n FLOAT, 
  n2 DOUBLE, 
  n3 DECIMAL
);

CREATE TABLE numerictable (
  i  TINYINT UNSIGNED,
  i2 SMALLINT UNSIGNED,
  i3 MEDIUMINT UNSIGNED, 
  i4 INT, 
  i5 BIGINT UNSIGNED,
  f  FLOAT UNSIGNED,
  f2 DOUBLE,
  f3 DECIMAL UNSIGNED
);

CREATE TABLE numerictable2 (
  i  TINYINT(3),
  i2 SMALLINT(3),
  i3 MEDIUMINT(3), 
  i4 INT(3), 
  i5 BIGINT(3),
  f  FLOAT(5, 2),
  f2 DOUBLE(5, 2),
  f3 DECIMAL(5, 2)
);

CREATE TABLE numerictable3 (
  i  TINYINT(3) UNSIGNED ZEROFILL,
  i2 SMALLINT(4) UNSIGNED ZEROFILL,
  i3 MEDIUMINT(5) UNSIGNED ZEROFILL, 
  i4 INT(6) UNSIGNED ZEROFILL, 
  i5 BIGINT(7) UNSIGNED ZEROFILL,
  f  FLOAT(5, 2) UNSIGNED ZEROFILL,
  f2 DOUBLE(7, 3) UNSIGNED ZEROFILL,
  f3 DECIMAL(9, 5) UNSIGNED ZEROFILL
);

CREATE TABLE bittable (
  n BIT,
  n2 BIT(8),
  n3 BIT(64)
);

CREATE TABLE nonbinarytable (
  s CHAR(10),
  s2 VARCHAR(10)
);

CREATE TABLE nonbinarytable2 (
  s  VARCHAR(6) CHARACTER SET latin1,
  s2 VARCHAR(6) CHARACTER SET big5,
  s3 VARCHAR(6) CHARACTER SET utf8
);

-- INSERT INTO nonbinarytable2 VALUES ('abc', 'abc', 'abc');
-- INSERT INTO nonbinarytable2 VALUES ('abcdef', 'abcdef', 'abcdef');
-- INSERT INTO nonbinarytable2 VALUES ('abc', '一二三', '一二三');
-- INSERT INTO nonbinarytable2 VALUES ('abcdef', '一二三四五六', '一二三四五六');
-- INSERT INTO nonbinarytable2 VALUES ('abcdef', '一二三abc', '一二三abc');
INSERT INTO nonbinarytable2 VALUES ('abc', 'abc', 'abc');
INSERT INTO nonbinarytable2 VALUES ('abcdef', 'abcdef', 'abcdef');
INSERT INTO nonbinarytable2 VALUES ('abc', '@GT', '@GT');
INSERT INTO nonbinarytable2 VALUES ('abcdef', '@GTabc', '@GTabc');
INSERT INTO nonbinarytable2 VALUES ('abcdef', '@GT|', '@GT|');

CREATE TABLE nonbinarytable3 (
  n  int,
  s  VARCHAR(20) CHARACTER SET latin1 COLLATE latin1_general_ci,
  s2 VARCHAR(20) CHARACTER SET latin1 COLLATE latin1_general_cs
);

INSERT INTO nonbinarytable3
VALUES (1, 'aaa', 'aaa'),(2, 'AAA', 'AAA'),
       (3, 'bbb', 'bbb'),(4, 'BBB', 'BBB'),
       (5, 'abc', 'abc'),(6, 'ABC', 'ABC');


CREATE TABLE binarytable (
  b  BINARY(6),
  b2 VARBINARY(6)
);

INSERT INTO binarytable VALUES ('a', 'a');
INSERT INTO binarytable VALUES ('abc', 'abc');
INSERT INTO binarytable VALUES ('abcdef', 'abcdef');


CREATE TABLE enumtable (
  enumsize ENUM('XS', 'S', 'M', 'L', 'XL'),
  stringsize VARCHAR(2)
);

CREATE TABLE settable (
  workingday SET('MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT', 'SUN')
);

CREATE TABLE estable (
  enumsize  ENUM('XS', 'S', 'M', 'L', 'XL') CHARACTER SET latin1 COLLATE latin1_general_ci,
  enumsize2 ENUM('XS', 'S', 'M', 'L', 'XL') CHARACTER SET latin1 COLLATE latin1_general_cs,
  workingday  SET('MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT', 'SUN') CHARACTER SET latin1 COLLATE latin1_general_ci,
  workingday2 SET('MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT', 'SUN') CHARACTER SET latin1 COLLATE latin1_general_cs
);

INSERT INTO estable 
VALUES (1, 1, 21, 21),
       ('M','M','MON','MON'),
       ('M','M','mon','MON');

CREATE TABLE dttable (
  y4 YEAR(4),
  y2 YEAR(2),
  d  DATE,
  t  TIME,
  dt DATETIME,
  ts TIMESTAMP
);

DROP TABLE IF EXISTS deptlog;

CREATE TABLE deptlog (
  logno SERIAL,
  logdt TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  message VARCHAR(64)
);

DROP TABLE IF EXISTS emplog;

CREATE TABLE emplog (
  logno bigint(20) unsigned NOT NULL AUTO_INCREMENT,
  logdt timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  message varchar(64),
  PRIMARY KEY logno (logno)
);

CREATE TABLE debug (
  fint TINYINT NOT NULL,
  fdouble DOUBLE(5, 2),
  fchar VARCHAR(3),
  fdate DATE DEFAULT '2000-01-01',
  ftime TIME,
  fdatetime DATETIME,
  ftimestamp TIMESTAMP,
  fyear YEAR,
  fenum ENUM('A', 'B', 'C'),
  fset SET('X', 'Y', 'Z')
);

```

### 2.SELECT 基礎查詢

-2-1:執行下列SQL查詢指令並說明其結果:
```
USE world


SELECT 'My name is Simon Johnson', 35 * 12


SELECT * FROM city


SELECT * FROM cmdev.emp


SELECT * FROM city


SELECT ID, Name
FROM   city


SELECT Name, ID
FROM   city


SELECT ID, Name, District
FROM   city


SELECT ename, salary, salary * 12,
       (salary * 12) + (salary DIV 2)
FROM   cmdev.emp


SELECT ename, salary AS MonthSalary,
       salary * 12 AS AnnualSalary,
       (salary * 12) + (salary DIV 2) AnnualFullSalary
FROM   cmdev.emp


SELECT ename, salary * 12 AS 'Annual Salary'
FROM   cmdev.emp


SELECT ename, salary * 12 AS 'select'
FROM   cmdev.emp
```

3.運算式與函式
4.JOIN 與 UNION 查詢
5.CRUD 與資料維護
6.字元集與資料庫
7.儲存引擎與資料型態
8.表格與索引
9.子查詢
10.Views
