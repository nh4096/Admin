Kernel modules location `/usr/lib/$(uname -r)`

Commands
```
# list loaded modules
lsmod

# information
modinfo <module>

# list configurations
modprobe -c

# load module
modprobe <module>

# unload module
modprobe -r <module>

```

Reference
+ [https://wiki.archlinux.org/index.php/Kernel_module]()