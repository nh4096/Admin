#### Commands

List zones 
```
firewall-cmd --get-zones
```

Get details of default zone 
```
firewall-cmd --list-all
```

Get details of all zones 
```
firewall-cmd --list-all-zones
```

```
firewall-cmd --get-default-zone
```

```
firewall-cmd --get-active-zone
```

List services 
```
firewall-cmd --get-services
```

Get service details 
```
firewall-cmd --info-service=<service>
```

Service definitions
+ Predefined `/usr/lib/firewalld/services/<service>.xml`. 
+ User defined `/etc/firewalld/services/<service>.xml`.

Add a service 
```
firewall-cmd --add-service=<service>
```

Add a port 
```
firewall-cmd --add-port=443/tcp
```

Reload
```
firewall-cmd --reload
```

Cast runtime setting to permanent
```
firewall-cmd --runtime-to-permanent
```

Emergency 
```
firewall-cmd --panic-on
```

