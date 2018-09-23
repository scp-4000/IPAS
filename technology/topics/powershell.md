# PowerShell

>* https://zh.wikipedia.org/wiki/Windows_PowerShell
```
PowerShell（包括Windows PowerShell and PowerShell Core）是微軟公司開發的任務自動化和組態管理框架，
由.NET Framework和.NET Core是構建的命令列介面殼層相關手稿語言組成，
最初僅Windows元件，後於2016年8月18日開源並跨平台支援。

在PowerShell中，管理任務通常由cmdlets（發音為command-lets）執行，這是執行特定操作的專用.NET類。
可以將cmdlet集合至指令碼、可執行檔（一般是獨立應用程式）中，或通過常規.NET類（或WMI / COM物件）例項化。
通過存取不同資料儲存中的資料由PowerShell執行，如檔案總管或登錄檔。
```
# PowerShell cmdlet專屬指令
```
cmdlet（唸法command-let）是Windows PowerShell 中，用來執行特定功能的專屬指令。
這些專屬指令的格式都是用連字號（-）來連結一對動詞與名詞，而且名詞通常都是單數

指令格式：動詞-名詞
         get-help

要查詢 Windows PowerShell 線上說明的 cmdlet 就可使用：get-help

常見的動詞有 get、set、add、remove 等等。
DOS 指令不區分字母的大小寫，
同樣地，Windows PowerShell 的 cmdlet 也不會區分字母的大小寫！
```
# 常用指令


https://www.jianshu.com/p/ea9cd9ecb494

入門級別

　　1. 像檔案系統那樣操作Windows Registry——cd hkcu:

　　2. 在檔裡遞回地搜索某個字串——dir –r | select string "searchforthis" 
　　
　　3. 使用記憶體找到五個進程——ps | sort –p ws | select –last 5

　　4. 迴圈（停止，然後重啟）一個服務，如DHCP——Restart-Service DHCP

　　5. 在資料夾裡列出所有條目——Get-ChildItem – Force

　　6. 遞迴一系列的目錄或資料夾——Get-ChildItem –Force c:\directory –Recurse

　　7. 在目錄裡移除所有檔而不需要單個移除——Remove-Item C:\tobedeleted –Recurse

　　8. 重啟當前電腦——(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(2)

　　收集資訊

　　9. 獲取計算機組成或模型資訊——Get-WmiObject -Class Win32_ComputerSystem

　　10. 獲取當前電腦的BIOS資訊——Get-WmiObject -Class Win32_BIOS -ComputerName .

　　11. 列出所安裝的修復程式（如QFE或Windows Update檔）——Get-WmiObject -Class Win32_QuickFixEngineering -ComputerName .

　　12. 獲取當前登錄電腦的使用者的用戶名—— Get-WmiObject -Class Win32_ComputerSystem -Property UserName -ComputerName .

　　13. 獲取當前電腦所安裝的應用的名字——Get-WmiObject -Class Win32_Product -ComputerName . | Format-Wide -Column 1

　　14. 獲取分配給當前電腦的IP位址——Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=TRUE -ComputerName . | Format-Table -Property IPAddress

　　15. 獲取當前機器詳細的IP配置報導——Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=TRUE -ComputerName . | Select-Object -Property [a-z]* -ExcludeProperty IPX*,WINS*

　　16. 找到當前電腦上使用DHCP啟用的網路卡——Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=true" -ComputerName .

　　17. 在當前電腦上的所有網路介面卡上啟用DHCP——Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=true -ComputerName . | ForEach-Object -Process {$_.EnableDHCP()}

　　軟體管理

　　18. 在遠端電腦上安裝MSI包——(Get-WMIObject -ComputerName TARGETMACHINE -List | Where-Object -FilterScript {$_.Name -eq "Win32_Product"}).Install(\\MACHINEWHEREMSIRESIDES\path\package.msi)

　　19. 使用基於MSI的應用升級包升級所安裝的應用——(Get-WmiObject -Class Win32_Product -ComputerName . -Filter "Name='name_of_app_to_be_upgraded'").Upgrade(\\MACHINEWHEREMSIRESIDES\path\upgrade_package.msi)

　　20. 從當前電腦移除MSI包——(Get-WmiObject -Class Win32_Product -Filter "Name='product_to_remove'" -ComputerName . ).Uninstall()

　　機器管理

　　21. 一分鐘後遠端關閉另一台機器——Start-Sleep 60; Restart-Computer –Force –ComputerName TARGETMACHINE

　　22. 添加印表機——(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection(\\printerserver\hplaser3)

　　23. 移除印表機——(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\printerserver\hplaser3 ")

　　24. 進入PowerShell會話——invoke-command -computername machine1, machine2 -filepath c:\Script\script.ps1


# 微軟網站

https://docs.microsoft.com/zh-tw/powershell/scripting/getting-started/cookbooks/performing-networking-tasks?view=powershell-6

### 列出電腦的 IP 位址
```
若要取得本機電腦上所有使用中的 IP 位址，請使用下列命令︰

Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true -ComputerName . | Format-Table -Property IPAddress

```

# 編寫 Windows PowerShell 腳本

https://ithelp.ithome.com.tw/articles/10028320

https://docs.microsoft.com/zh-tw/powershell/scripting/getting-started/getting-started-with-windows-powershell?view=powershell-6

# 進階研讀:
```
Active Directory 環境的PowerShell 活用指南  Active Directory with PowerShell
作者： Uma Yellapragada    譯者： 王偉任 博碩出版社：  出版日期：2015/11/30
```
```
使用 PowerShell 管理使用者帳戶及電腦帳戶。
使用 PowerShell 管理群組成員、刪除群組成員、大量建立使用者帳戶及群組。
使用 PowerShell 以快速且高效率的方式，查詢在 Active Directory 環境中的使用者、電腦、群組……等物件的詳細資訊。
使用 PowerShell 設定及管理網域、組織、站台、子網路、樹系。
PowerShell 的進階管理技巧，例如，升級/降級網域控制站、檢查 Active Directory 複寫機制、建立更細緻的密碼原則、FSMO 五大角色的轉移/取回……等詳細資訊。
使用 PowerShell 管理 DNS 客戶端，以及 DNS 伺服器如建立／修改／刪除 DNS 記錄。
使用 PowerShell 設定及管理 DFS-N 及 DFS-R 運作環境。
```
```
分散式檔案系統 (DFS)
https://en.wikipedia.org/wiki/Distributed_File_System_(Microsoft)

[DFS 命名空間(DFS-N)DFS Namespaces]和 [DFS 複寫(DFS-R)]概觀
https://msdn.microsoft.com/zh-tw/library/jj127250(v=ws.11).aspx

https://docs.microsoft.com/zh-tw/windows-server/storage/dfs-namespaces/dfs-overview
```
```
01 讓我們開始吧
02 管理使用者及電腦物件
03 了解 Active Directory 群組及成員關係
04 設定群組原則（GPO）
05 管理網域、組織、站台、子網路
06 使用 PowerShell 進階管理 AD
07 使用 PowerShell 管理 DFS-N 及 DFS-R
08 使用 PowerShell 管理 Active Directory DNS
09 進一步學習其它指令碼及相關資源
```
