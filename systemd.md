### Commands

List all services 
```
systemctl -at service
```

List running services 
```
systemctl -t service --state=running
```

List enabled services 
```
systemctl list-unit-files -t service --state=enabled
```

Print unit definition 
```
systemctl cat <foo>.service
```

Reload manager 
```
systemctl daemon-reload
```

Print logs from a service 
```
journalctl -u <foo>.service
```

View system boot log 
```
journalctl -xb
```

### Files

Service definitions
+ Built-in `/usr/lib/systemd/system/*.service`. 
+ User-defined `/etc/systemd/system/*.service`.
