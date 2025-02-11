```
第壹章  資訊洩露 1
1.1  主機資訊 1
1.1.1  子功能變數名稱信息 2
1.1.2  埠資訊 5
1.1.3  功能變數名稱註冊資訊 10
1.1.4  網站後臺地址 12

1.2  源碼洩露 14
1.2.1  Git源碼洩露 15
1.2.2  SVN源碼洩露 17
1.2.3  .DS_Store文件洩露 18
1.2.4  網站備份壓縮檔 20
1.2.5  WEB-INF/web.xml洩露 21
1.2.6  防禦方案 24
1.3  帳戶弱口令 24
1.3.1  漏洞成因 24
1.3.2  漏洞危害 25
1.3.3  漏洞案例 26
1.3.4  防範方法 29

第2章  常規漏洞 31
2.1  SQL注入 31
2.1.1  注入方式 32
2.1.2  漏洞的3種類型 39
2.1.3  檢測方法 41
2.1.4  防範方法 43
2.1.5  代碼審查 45
2.1.6  小結 47

2.2  XSS跨站 47
2.2.1  XSS漏洞類型 48
2.2.2  漏洞危害 51
2.2.3  防範方法 54
2.2.4  操作實踐 56
2.2.5  代碼審查 58
2.2.6  小結 59

2.3  代碼注入與命令執行 59
2.3.1  漏洞類型 60
2.3.2  漏洞案例 62
2.3.3  防禦方法 65
2.3.4  命令執行 65
2.3.5  小結 67

2.4  CSRF跨站請求偽造 67
2.4.1  原理分析 67
2.4.2  漏洞案例 68
2.4.3  操作實踐 72
2.4.4  防禦方法 73
2.4.5  防禦代碼示例 74
2.4.6  小結 75

2.5  檔包含 76
2.5.1  漏洞成因 76
2.5.2  本地檔包含 76
2.5.3  遠程檔包含 79
2.5.4  測試方法 82
2.5.5  使用PHP封裝協定 83
2.5.6  小結 84

2.6  檔上傳漏洞 85
2.6.1  利用方式 85
2.6.2  上傳檢測 86
2.6.3  解析漏洞 87
2.6.6  小結 92

第3章  業務邏輯安全 93
3.1  驗證碼安全 93
3.1.1  圖片驗證碼 94
3.1.2  數字暴力破解 98
3.1.3  空驗證碼突破 99
3.1.4  繞過測試 101
3.1.5  憑證返回 102
3.1.6  小結 103

3.2  密碼找回 103
3.2.1  敏感資訊洩露 104
3.2.2  郵箱弱token 105
3.2.3  驗證的有效性 106
3.2.4  註冊覆蓋 107
3.2.5  小結 109

3.3  介面盜用 109
3.3.1  API盜用 109
3.3.2  短信轟炸 111

3.4  帳戶越權 116
3.4.1  未授權訪問 116
3.4.2  水準越權 118
3.4.3  垂直越權 120
3.4.4  小結 121

3.5  支付漏洞 121
3.5.1  支付流程分析 122
3.5.2  金額資料篡改 123
3.5.3  商品數量篡改 125
3.5.4  運費金額修改 127
3.5.5  小結 128

3.6  SSRF服務端請求偽造 129
3.6.1  漏洞成因 129
3.6.2  漏洞案例 131
3.6.3  總結 134

第4章  LANMP安全配置 135
4.1  PHP安全配置 135
4.2  PHP安全擴展 139

4.2.1  taint簡介 139
4.2.2  安裝taint 140
4.2.3  測試驗證 141
4.2.4  小結 144

4.3  Apache安全配置 144
4.3.1  遮罩版本資訊 144
4.3.2  目錄許可權隔離 145
4.3.3  關閉預設主機 145
4.3.4  低許可權運行 145
4.3.5  防止用戶自訂設置 145
4.3.6  禁止顯示目錄 146

4.4  Nginx安全配置 148
4.4.1  配置防禦 148
4.4.2  防止許可權擴大 149
4.4.3  WAF擴展 150
4.4.4  Nginx解析漏洞 152

4.5  Redis配置 154
4.5.1  漏洞成因 154
4.5.2  漏洞案例 156
4.5.3  小結 157

4.6  MySQL安全配置 157
4.6.1  許可權安全 157
4.6.2  網路配置 162
4.6.3  MySQL日誌 163
4.6.4  主機配置 164
4.6.5  啟動選項 165

第5章  認證與加密 167
5.1  資料加密與簽名 167
5.1.1  對稱加密與非對稱加密 167
5.1.2  數位簽章 169
5.1.3  數位憑證 170

5.2  HTTPS安全 171
5.2.1  HTTPS簡介 171
5.2.2  HTTPS被攻擊的方式 173
5.2.3  常見誤區 174
5.3  密碼加密策略 175
5.3.1  密碼存儲 176
5.3.2  密碼傳輸 178
5.3.3  漏洞案例 178
5.3.4  總結 180

第6章  其他Web安全主題 181
6.1  DDoS攻擊 181
6.1.1  DDoS分類 182
6.1.2  應對方案 183
6.1.3  漏洞案例 184
6.1.4  小結 186

6.2  CMS通用漏洞 186
6.2.1  漏洞簡介 186
6.2.2  等級劃分 187
6.2.3  漏洞案例 188
6.2.4  防禦方法 191

6.3  網頁掛馬 192
6.3.1  掛馬類型 193
6.3.2  掛馬檢測 19
6.3.3  小結 196



6.4  Burp Suite 196
6.4.1  攔截資料包 197
6.4.2  修改資料包 198
6.4.3  頁面連結抓取 199
6.4.4  自動化挖掘 201
6.4.5  暴力破解 201

6.5  SQLMap 203
6.5.1  查看資料庫帳戶 205
6.5.2  查看資料庫中的所有帳戶 206
6.5.3  獲取所有資料庫名稱 207
6.5.4  獲取資料庫表名稱 208
6.5.5  查看表結構 209
6.5.6  匯出數據 210
```
