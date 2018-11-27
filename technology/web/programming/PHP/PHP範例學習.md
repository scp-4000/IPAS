
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


### 範例程式: 前端表單設計與後端處理

>* 前端表單設計  form.html
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
  </head>
  <body>
    <form method="post" action="confirm.php">
      姓&nbsp;&nbsp;&nbsp;名：<input type="text" name="UserName" size="40"><br>
      E-Mail：<input type="text" name="UserMail" size="40" value="username@mailserver"><br>
      年&nbsp;&nbsp;&nbsp;齡：
      <input type="radio" name="UserAge" value="Age1">未滿20歲
      <input type="radio" name="UserAge" value="Age2" checked>20~29
      <input type="radio" name="UserAge" value="Age3">30~39
      <input type="radio" name="UserAge" value="Age4">40~49
      <input type="radio" name="UserAge" value="Age5">50歲以上<br>
      您使用過哪些廠牌的手機？
      <input type="checkbox" name="UserPhone[]" value="hTC" checked>hTC
      <input type="checkbox" name="UserPhone[]" value="Apple">Apple
      <input type="checkbox" name="UserPhone[]" value="ASUS">ASUS
      <input type="checkbox" name="UserPhone[]" value="acer">acer<br>
      您使用手機時最常碰到哪些問題？<br>
      <textarea name="UserTrouble" cols="45" rows="4">上網速度不夠快</textarea><br>
      您使用過哪些電信業者的門號？(可複選)
      <select name="UserNumber[]" size="4" multiple>
        <option value="中華電信">中華電信
        <option value="台灣大哥大" selected>台灣大哥大
        <option value="遠傳">遠傳
        <option value="亞太電信">亞太電信
      </select><br>
      <input type="submit" value="提交">
      <input type="reset" value="重新輸入">
    </form>
  </body>
</html>

```
>* 後端表單處理  form.html
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
  </head>
  <body>
    <?php
      $Name = $_POST["UserName"];
      $Mail = $_POST["UserMail"];
      switch($_POST["UserAge"])
      {
        case "Age1":
          $Age = "未滿20歲";
          break;
        case "Age2":
          $Age = "20~29";
          break;
        case "Age3":
          $Age = "30~39";
          break;
        case "Age4":
          $Age = "40~49";
          break;
        case "Age5":
          $Age = "50歲以上";
      }
      $Phone = $_POST["UserPhone"];
      $Trouble = $_POST["UserTrouble"];
      $Number = $_POST["UserNumber"];
    ?>
    <p><i><?php echo $Name; ?></i>，您好！您輸入的資料如下：</p>
      電子郵件地址：<?php echo $Mail; ?><br>
      年齡：<?php echo $Age; ?><br>
      曾經使用過的手機廠牌：<?php foreach($Phone as $Value) echo $Value.'&nbsp;'; ?><br>
      使用手機時最常碰到的問題：<?php echo $Trouble; ?><br>
      使用過哪些電信業者的門號：<?php foreach($Number as $Value) echo $Value.'&nbsp;'; ?>
  </body>
</html>
```

### 範例程式:自訂的HTTP Header 與PHP內建的函式header() 
>* 前端表單  form2.html
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
  </head>
  <body>
    <form method="post" action="redirect.php">
      <select name="mySelect" size="1"> 
        <option value="https://tw.yahoo.com/">YAHOO!奇摩 
        <option value="http://www.yam.com/">蕃薯藤 
        <option value="https://www.google.com.tw/">Google
      </select>
      &nbsp;<input type="submit" value="GO!">
    </form>
  </body>
</html>
```
>* 後端表單處理  redirect.php
```
<?php
  $URL = $_POST['mySelect'];
  header("Location: $URL");
  exit(); 
?>
```
### 範例程式: 使用者與密碼認證
>* 
```
<?php
  header("Content-type: text/html; charset=utf-8");
  if (!isset($_SERVER['PHP_AUTH_USER']))
  {
    header('WWW-Authenticate: Basic realm="快樂網站"');
    echo "抱歉！您沒有輸入密碼！";
    exit();
  }
  else
  {
    echo "{$_SERVER['PHP_AUTH_USER']}您好！<br>";
    echo "您輸入的密碼為{$_SERVER['PHP_AUTH_PW']}！";
  }
  echo "抱歉！您沒有輸入密碼！";
?>
```

作業:
```
$_SERVER[]是甚麼?
$_SERVER['PHP_AUTH_USER']會傳回甚麼資料?
$_SERVER['PHP_AUTH_PW']會傳回甚麼資料?
isset()函式的功能?
WWW-Authenticate是甚麼? Basic vs Digest ?
```
```
HTTP基本認證 ==>  https://zh.wikipedia.org/wiki/HTTP%E5%9F%BA%E6%9C%AC%E8%AE%A4%E8%AF%81

在HTTP中，基本認證（Basic access authentication）
是一種用來允許網頁瀏覽器或其他用戶端程式在請求時提供使用者名稱和口令形式的身分憑證的一種登入驗證方式。

在傳送之前是以使用者名稱追加一個冒號然後串接上口令，並將得出的結果字串再用Base64演算法編碼。
例如，提供的使用者名稱是Aladdin、口令是open sesame，則拼接後的結果就是Aladdin:open sesame，然後再將其用Base64編碼，得到QWxhZGRpbjpvcGVuIHNlc2FtZQ==。
最終將Base64編碼的字串傳送出去，由接收者解碼得到一個由冒號分隔的使用者名稱和口令的字串。

雖然對使用者名稱和口令的Base64演算法編碼結果很難用肉眼辨識解碼，但它仍可以極為輕鬆地被電腦所解碼，就像其容易編碼一樣。
編碼這一步驟的目的並不是安全與隱私，而是為將使用者名稱和口令中的不相容的字元轉換為均與HTTP協定相容的字元集。

最初，基本認證是定義在HTTP 1.0規範（RFC 1945）中，後續的有關安全的資訊可以在HTTP 1.1規範（RFC 2616）和HTTP認證規範（RFC 2617）中找到
```
