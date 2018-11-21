# XAMPP

### 下載與安裝XAMPP網頁伺服器架站工具
```
http://elesson.tc.edu.tw/md221/course/view.php?id=234
https://www.pcsetting.com/devtools/54?page=0%2C1
https://briian.com/18718/
```
```
Step 1：連結至XAMPP正體中文官方網站下載頁面
下載免安裝的XAMPP版本，
所以會點選如下圖所示的『更多下載』，來選擇其他的XAMPP版本。

當然如果你想要將XAMPP安裝至電腦，那也可以直接在此頁選擇與下載你要的XAMPP版本，並執行安裝程式將XAMPP架站軟體安裝至你的電腦。

Step 2：請依你電腦系統的環境，下載相對應XAMPP架站工具，
       如是使用Windows OS，就選擇『XAMPP Windows』

Step 3：XAMPP軟體版本號的命名方式，是依照PHP的版本

如果要PHP 7.0.1的環境，那就選擇7.0.1的XAMPP版本。
請依照你自己所使用的架站軟體要求的PHP版本，來選擇你要的XAMPP版本
如想要安裝Drupal 8，而Drupal 8最低需求的PHP版本為5.5.9，
那可以選擇XAMPP所提供的5.5、5.6及7.0以上的版本。

Step 4：XAMPP跟其他架站工具不同的就是，他除了提供安裝版本外，還多了免安裝的版本，這對於想要學習和開發網站的開發人員來說方便了很多，因為你可以直接把XAMPP檔案直接複製進USB或上傳至雲端空間，如果在其他地方使用不同的電腦時，只要再重新執行XAMPP的『setup_xampp』批次檔來更新路徑，不需要在重新架設環境與設定一堆有的沒得，而就可以在不同電腦上繼續開發你的網站了。以下筆者列出比較常用的XAMPP版本格式：

xampp-win32-x.x.xx-x-VCxx.zip→免安裝版本，此免安裝版本保留了安裝版本該有的工具，
例如說：如果你要架設FileZilla FTP伺服器或者是Mercury郵件伺服器，那你就要下載此版本。

xampp-portable-win32-x.x.xx-x-VCxx.zip→免安裝版本，此免安裝版本為瘦身版，
因為此版本移除，如：FileZilla FTP伺服器與Mercury郵件伺服器等等的工具，所以XAMPP檔案體積也比較小。此版本也是筆者本教學所使用的版本。

xampp-win32-x.x.xx-x-VCxx-installer.exe→安裝檔版本，
如果你要將XAMPP安裝至電腦，可以下載此版本。

```
```
https://des13.com/joomla/61-joomla/425-xampp-joomla

1.XAMPP預設的MySQL資料庫的最大權限root帳號沒有設定密碼
因此可以進入網址「localhost/security/xamppsecurity.php」進行密碼設定。

2.XAMPP的預設網站根目錄是在根目錄的「htdocs」目錄中，Joomla!接下來需要解壓縮在這裡面。

3.XAMPP的Apache設定檔在根目錄的「apache\conf\httpd.conf」檔案。

4.XAMPP的PHP設定檔是在根目錄的「php\php.ini」檔案。
```
```
設定XAMPP

1.安裝完畢之後會跳出XAMPP_Control_Panel視窗，按點Apache右邊的「Start」按鈕，
和MySQL右邊的「Start」按鈕，Apache和MySQL就可以啟動了。
```


### 更改XAMPP預設的文字編輯器及更改phpMyAdmin的認證模式。
```
Step 1：XAMPP預設使用的文字編輯器是Windows內建的記事本，如果使用者沒有更改至其他文字編輯器，直接使用Windows內建記事本編輯XAMPP設定檔時，會發現到文字都擠在一堆，造成編輯上的不便。通常筆者習慣在安裝完成XAMPP時，都會馬上更改XAMPP預設的文字編輯器，點選如下圖所示的『Config』，並點選Editor的圖形『資料夾』，在你電腦本機中選擇你習慣使用的文字編輯器，選擇好後，點選『開啟』。如果你電腦上沒有文字編輯器，筆者可以推薦你使用好用的文字編輯器Notepad++。關於Notepad++的教學，可以查看此篇Notepad++ 免費文字編輯器設定及使用教學。
```

### phpMyAdmin認證模式
```
phpMyAdmin認證模式有3種，開啟phpMyAdmin的config.inc.php檔可以看到
預設的認證模式為『config』，config為最不安全的認證模式，筆者建議更改為『cookie』或『http』，

3種不同的認證模式：

config→此值為預設的認證模式，是將資料庫的使用者名稱及密碼直接輸入在config.inc.php檔裡，
    日後登入phpMyAdmin無需重新輸入帳號及密碼，就可以直接管理資料庫，為最不安全的認證模式。

cookie→使用資料庫做認證，只要瀏覽器支援cookie功能就可以使用，此認證方式為最常見到的認證模式。

http→除了使用資料庫做認證外，還使用了http的認證模式，此認證方式的安全性也最高。

```

### 資料庫
```
Step 1：開始建立資料庫
可以點選如下圖所示的『Admin』管理資料庫（或者在瀏覽器網址列輸入『http://localhost/phpmyadmin』）
，點選後會以你剛剛設定的認證模式來開啟網頁，
，在phpMyAdmin的介面中，要輸入你的『使用者名稱』及『密碼』，
但因為第一次使用，只需要輸入使用者名稱就好，預設的使用者名稱為『root』，密碼為空，
輸入好後直接點擊『執行』。

Step 2：在phpMyAdmin資料庫管理介面中你會看到一個警告，內容大概是因為管理者帳號root沒有設定密碼，建議你設定密碼來提高資料庫的安全，點選如下圖所示的『修改密碼』，會跳出一個視窗，選擇『密碼』，並輸入兩次你要的密碼，輸入完成後，點選『執行』。另外，你可以在資料庫管理介面中看到資料庫伺服器與網頁伺服器等等的資訊，如在資料庫伺服器的資訊中，可以看到你用的伺服器類別名稱

Step 3：接下來要開始建立新的資料庫，點選如下圖所示的『資料庫』，輸入你新資料庫的名稱，編碼與排序方面，選擇你自己所需要的編碼格式，一般常用的編碼格式為utf8_general_ci或者是utf8_unicode_ci，關於這兩個編碼格式的差異，可以查看維基百科utf8_unicode_ci和utf8_general_ci區別，如下圖所示筆者選擇了『utf8_general_ci』，選擇好後，點擊『建立』。

**現在很多CMS或其他的架站軟體幾乎都已經開始支援『utf8mb4_general_ci』或『utf8mb4_unicode_ci』編碼格式。『utf8mb4』和『utf8』兩者差異為前者『utf8mb4』一個字元可以儲存4個位元組（4-byte），而後者『utf8』一個字元僅能儲存3個位元組（3-byte）。當然筆者是比較建議選『utf8mb4』編碼，因為這樣好處就是可以讓你的MySQL可以儲存Emoji表情符號或其他的會用到4個位元組的特殊符號。假如你要選擇『utf8mb4』編碼，而且只是要架設中英文的網站，那一樣建議選擇『utf8mb4_general_ci』編碼格式，因為『utf8mb4_general_ci』會比『utf8mb4_unicode_ci』來說速度會快一些。否則，假如是要架設多國語言網站（如：德語、法語及俄語等等），那才需要選擇『utf8mb4_unicode_ci』。
```

```
自架網站 固定IP 網域規劃與設定，架站必學
https://wuangus.cc/domain/
```
# WordPress
```
https://zi.media/@kocpc/post/N4M7NH
https://zi.media/@wuangus/post/SgC28b

用 Bitnami 套件快速架設 WordPress
如果你今天想要試試在XAMPP環境下快速架設 WordPress，它除了能讓你自己下載 WordPress 主程式後，
架設在剛鋼架好的伺服器環境內以外，還可以透過 Bitnami 配合XAMPP製作的 WordPress 懶人安裝包，
將 WordPress 刷刷的安裝進去。

XAMPP跟 Bitnami 彼此間有合作，以 Windows 平台來說，Bitnami 會將一些著名的 CMS 程式，
比如說 WordPress、Joomla 打包成安裝檔，安裝過程中會詢問Xampp的程式位置，
然後安裝程序會接著問網站的一些設定，像是信箱、登入帳號密碼等：
```
### Drupal 8 
```
Drupal 8 好用的 CMS 架站軟體安裝設定與使用教學
https://www.pcsetting.com/devtools/60
```
### Discuz!論壇
```
只要10分鐘，快速架站Discuz!論壇教學
https://zi.media/@wuangus/post/Yu25AP
```
### Joomala

在XAMPP下安裝Joomla！https://des13.com/joomlatech/joomla-file/425-xampp-joomla.html?start=1

### 設定MySQL
```
1.在瀏覽器的網址輸入「localhost/phpmyadmin」，以進入資料庫登入畫面，輸入使用者名稱、密碼，選擇執行進入。
2.選擇使用者
3.選擇新增使用者
4.設定帳號，主機選擇本地，設定密碼，並勾選（建立與使用者同名的資料庫並授予所有權限），全域權限點選「全選」，最後點右下角執行。
```
### 下載Joomla!
```
1.進入台灣Joomla社群網站「www.joomla.org.tw」，下載主程式和繁中語言包。
2.將主程式解壓縮到XAMPP根目錄的htdocs目錄中（htdocs為網頁根目錄），並將資料夾名稱改成簡單一點。
```
### 安裝Joomla!
```
1.在瀏覽器的網址輸入「localhost/joomla」，會看見Joomla的安裝畫面，選擇繁體中文後按右上角的下一步。
2.注意紅色框框部分必須都為「是」，才能順利安裝，確認後按下一步。
3.授權規定，不猶豫直接下一步。
4.設定Joomla的帳號、密碼，資料庫名稱輸入剛剛設定好的資料庫「hello」，按下一步。
5.這裡直接按下一步。
6.設定網站名稱，輸入Email帳號、Joomla的帳號及密碼，按下「安裝範例資料」，然後下一步。
7.最後按下「移除安裝資料夾」就大功告成了!
```
### 安裝Joomla！繁體中文語言包
```
1.在瀏覽器的網址「localhost/joomla/administrator」，進入Joomla後台登入畫面，輸入帳號、密碼後，按下Log in。
2.進入後台->Extensions->Extension Manager
3.選擇檔案，找到下載好的Joomla繁中語言包壓縮檔，按下上傳與安裝。
4.Extensions->Language Manager
5.Installed-Site->將中文（繁體-台灣）設成預設
6.Installed-Administrator->將中文（繁體-台灣）設成預設
7.大功告成!!!
```
### moodle

```
Moodle 3.0 Tutorial for Beginners - Introduction
https://www.youtube.com/watch?v=HEZ-fYYr6zM
```
```
Using Moodle to Create Competency Based Education
https://www.youtube.com/watch?v=otPRjbfoF_E
```
```
Moodle 數位教學平台訓練課程教材(教師用)
https://www.youtube.com/watch?v=vEjD0D0Q-lc
```

```
考選部國考題目pdf 匯入moodle測驗卷
https://www.youtube.com/watch?v=qtvNSItvUmA
```

```
數位學習平台-Moodle管理
https://www.youtube.com/watch?v=dC5OlpOgh54
```
```
MOODLE安裝教學_數位學習

```
```
http://maylike.kh.edu.tw/teach/moodle/index.html

```
```
Using Moodle 3: A Comprehensive Tutorial for Teachers
https://www.youtube.com/watch?v=ONvcFK-97Dw
```
```
Using Moodle to Create Competency Based Education
https://www.youtube.com/watch?v=otPRjbfoF_E
```

