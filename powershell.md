Get number of cmdlets in each `microsoft.powershell` modules
```
get-command -module microsoft.powershell.* | Group-Object -Property module | ft -Property count,name
```

### Random generator

Sampling *without* replacement
```
'a','b','c' | Get-Random -Count 8
c
b
a
```

Sampling *with* replacement
```
1..8 | % {'a','b','c' | Get-Random}
c
a
b
a
b
a
c
c
```