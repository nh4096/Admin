
Find cmdlets in PowerShell core modules that has `computername` parameter and not have `session` parameter
```
PS C:\> get-command -Module Microsoft.PowerShell.* | where {$_.parameters.keys -contains "computername" -and $_.parameters.keys -notcontains "session"}
```