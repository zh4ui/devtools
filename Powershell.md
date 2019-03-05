# PowerShell


## Inovke Internet Explorer

```powershell
$IE = New-Object -ComObject InternetExplorer.Application
$IE.navigate2("www.bing.com")
#$IE.visible=$true
```

[Controlling Internet Explorer object from PowerShell](http://blogs.msdn.com/powershell/archive/2006/09/10/controlling-internet-explorer-object-from-powershell.aspx)

[How to open URL through powershell](https://social.technet.microsoft.com/Forums/ie/en-US/e54555bd-00bb-4ef9-9cb0-177644ba19e2/how-to-open-url-through-powershell?forum=winserverpowershell)

[Using Powershell to open internet explorer and login into sharepoint](https://stackoverflow.com/questions/22920602/using-powershell-to-open-internet-explorer-and-login-into-sharepoint)

[How to open Internet Explorer for the desktop from command line in Windows 8?](https://superuser.com/questions/529832/how-to-open-internet-explorer-for-the-desktop-from-command-line-in-windows-8)

[USING IE AUTOMATION IN POWERSHELL TO SIMPLIFY BROWSER BASED TASKS](HTTP://AGILERAMBLINGS.COM/2015/07/22/USING-IE-AUTOMATION-IN-POWERSHELL-TO-SIMPLIFY-TASKS/)


many ways to do that

```powershell
Start-Process -Path "url"

[System.Diagnostics.Process]::Start("url")

(New-Object -Com Shell.Application).Open("url")
```