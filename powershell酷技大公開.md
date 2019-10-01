# powershell

# 參考資料

```
(https://docs.microsoft.com/en-us/powershell/scripting/
```
```
參考書:Windows Server 2019 & PowerShell All-in-One For Dummies
Book 6: Working with Windows PowerShell . . . . . 501
CHAPTER 1:	 Introducing PowerShell . . . .  503
CHAPTER 2:	 Understanding the .NET Framework . . . . . . 535
CHAPTER 3:	 Working with Scripts and Cmdlets . . . . .  543
CHAPTER 4:	 Creating Your Own Scripts and Advanced Functions . . . . 551
CHAPTER 5:	 PowerShell Desired State Configuration . . . . 567
```
### 
```
名稱
    Get-Service
    
概要
    取得本機電腦或遠端電腦上的服務。
    
    
語法
    Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-Exclude <String[]>] [-Include <S
    tring[]>] [-RequiredServices] [<CommonParameters>]
    
    Get-Service [-ComputerName <String[]>] [-DependentServices] [-Exclude <String[]>] [-Include <String[]>] [-RequiredS
    ervices] -DisplayName <String[]> [<CommonParameters>]
    
    Get-Service [-ComputerName <String[]>] [-DependentServices] [-Exclude <String[]>] [-Include <String[]>] [-InputObje
    ct <ServiceController[]>] [-RequiredServices] [<CommonParameters>]
    
    
描述
    Get-Service Cmdlet 會取得本機電腦或遠端電腦上代表服務 (包括執行中和已停止的服務) 的物件。
    
    您可以藉由指定服務名稱或服務的顯示名稱，或是使用管道將服務物件傳送給 Get-Service，來指示 Get-Service 只取得特定的服務。
    

相關連結
    Online Version: http://go.microsoft.com/fwlink/p/?linkid=290503
    New-Service 
    Restart-Service 
    Resume-Service 
    Set-Service 
    Start-Service 
    Stop-Service 
    Suspend-Service 

註解
    若要查看範例，請輸入: "get-help Get-Service -examples".
    如需詳細資訊，請輸入: "get-help Get-Service -detailed".
    如需技術資訊，請輸入: "get-help Get-Service -full".
    如需線上說明，請輸入: "get-help Get-Service -online"

```

### Get-Command *-Service

```
CommandType     Name                                               ModuleName                                          
-----------     ----                                               ----------                                          
Cmdlet          Get-Service                                        Microsoft.PowerShell.Management                     
Cmdlet          New-Service                                        Microsoft.PowerShell.Management                     
Cmdlet          Restart-Service                                    Microsoft.PowerShell.Management                     
Cmdlet          Resume-Service                                     Microsoft.PowerShell.Management                     
Cmdlet          Set-Service                                        Microsoft.PowerShell.Management                     
Cmdlet          Start-Service                                      Microsoft.PowerShell.Management                     
Cmdlet          Stop-Service                                       Microsoft.PowerShell.Management                     
Cmdlet          Suspend-Service                                    Microsoft.PowerShell.Management  
```
```
Get-Command *-Service > D: test.txt
```
### Get-Command | Get-Member

```


```
### Get-Service | Where-Object {$_.Status -eq "Running"}


```


```

# PowerShell Gallery 

### 

```
Get-Process

```


### Exporting and importing CSV files

```
Get-Process | Export-Csv -Path D:\processes.csv

$Procs = Import-Csv -Path D:\processes.csv
```


### Exporting HTML/XML

```
Get-Process | ConvertTo-Html | Out-File D:\processes.html

```


### Sorting through objects

```
Get-Process | Sort-Object -Property CPU

```


### Filtering through objects

```
Get-Process | Sort-Object -Property CPU | Select-Object -Last 5

```


### 強化powershell安全性

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```


### 

```


```



