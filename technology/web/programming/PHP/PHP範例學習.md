
### 範例程式1: PHP101_1.php
>* 直接將 PHP 程式嵌入 HTML 網頁
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>天王龍的第一個PHP程式</title>
  </head>
  <body>
    <?php
      echo("Hello Dragon!");
      phpinfo();
    ?>
  </body>
</html>
```

### 範例程式: PHP101_.php
>* 將 PHP 程式放在外部檔案 然後再include近來

showme.inc
```
<?php
    echo("Hello Dragon!");
    phpinfo();
?>
```
```
<!doctype html> 
<html>
  <head>
    <meta charset="utf-8">
    <title>天王龍的第一個PHP程式</title>
  </head>
  <body>
    <?php
      include_once("showme.inc");
    ?>
  </body>
</html>
```

### 範例程式2: PHP101_2.php
>* 
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>我的第一個PHP程式</title>
  </head>
  <body>
    <?php
      echo("<h1><b><i>Hello World!</i></b></h1>");
    ?>
  </body>
</html>
```




### 範例程式: PHP101_.php
>* 
```
<!doctype html>
<html>
	<head>
	  <meta charset="utf-8">
	</head>
  <body>
    <?php
      echo __FILE__;
      echo "<br>";
      echo __DIR__;
    ?>
  </body>
</html>
```


### 範例程式: PHP101_.php
>* 
```
<?php
  echo("Hello World!");
  phpinfo();
?>
```


### 範例程式: PHP101_.php
>* 
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>我的第一個PHP程式</title>
  </head>
  <body>
    <?php
      echo("<h1><b><i>Hello World!</i></b></h1>");
    ?>
  </body>
</html>
```


### 範例程式: PHP101_.php
>* 
```

```


### 範例程式: PHP101_.php
>* 
```

```


### 範例程式: PHP101_.php
>* 
```

```
