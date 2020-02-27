### Windows programs

| Executable | Description |
| --- | --- |
| format.com | Format a disk |
| diskpart.exe | Diskpart |
| diskperf.exe | Disk performance counter |
| driverquery.exe | List drivers |
| icacls | ACL management |
| mount.exe | Mount NFS share|
| msconfig.exe | System configuration |
| msinfo32.exe | System information |
| mstsc.exe | Remote desktop client |
| rundll32.exe | |
| sc.exe | Service control manager |
| showmount.exe | NFS |
| shutdown.exe | Shutdown, reboot, logoff |
| systeminfo.exe | System info |
| tasklist.exe | List runing processes |
| taskkill.exe | Kill a process |
| umount.exe | Unmount NFS share|
| w32tm.exe | Time management |
| winrm.exe | Windows remote management |
| compmgmt.msc | computer management |
| devmgmt.msc | Device manager |
| diskmgmt.msc | Disk Management |
| fsmgmt.msc | Shared folders |
| gpedit.msc | Local group policy editor |
| lusrmgr.msc | Local users and groups |
| perfmon.msc | Performance Monitor |
| secpol.msc | Local security policy |
| services.msc | Services |
| taskschd.msc | Task scheduler |
| wf.msc | Windows defender firewall |

### Windows variables

| Variable | Value |
|---|---|
| %APPDATA% | C:\Users\UserName\AppData\Roaming |
| %HOMEDRIVE% | C: |
| %HOMEPATH% | \Users\UserName |
| %LOCALAPPDATA% | C:\Users\UserName\AppData\Local |
| %PROGRAMFILES% | C:\Programe Files |
| %SYSTEMROOT% | C:\Windows |
| %USERPROFILE% | C:\Users\UserName |
| %WINDIR% | C:\Windows |

### Icons

Icon DLLs
* `%SystemRoot%\System32\imageres.dll`
* `%SystemRoot%\System32\imagesp1.dll`
* `%SystemRoot%\System32\SHELL32.dll`

### How-to

#### Set default code page for cmd and powershell to UTF-8. 
Create registry entry
```
HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor\Autorun="chcp 65001"
```

#### Lock computer from command line
```
rundll32.exe user32.dll,LockWorkStation
```

#### Disable guest account
```
net user guest /active:no
```

#### Generate random password for user `foo`
```
net user foo /random
```
