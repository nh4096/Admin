### Users and groups

List of groups `/etc/group`.

Create a user with sudo priviledge `sudo useradd <user> -m -G wheel; passwd <user>`.

Reserved users and groups `/usr/share/doc/setup*/uidgid`.

Default dotfiles `/etc/skel/*`.

Add existing user to existing groups `usermod -aG <group1>,<group2> <user>`.

Apply `id` on all users, `for user in $(cat /etc/passwd | cut -d ':' -f 1); do id $user; done`.

### Extras

Generate and view N bytes of random data `cat /dev/urandom | hexdump -C -n <N>`.

### Locales

```
localectl status
localectl list-locales
localectl list-keymaps
/etc/locale.conf
```

### Date and time

```
systemctl status systemd-timedated
timedatectl list-timezones
```


### Storage

```
# check root mount point
mount | grep -w /

# disk usage
df -TH

# list size of top-level directories
du -sh *

# top-level directories sorted by size
du -s * | sort -n

# df-like function
du -h --max-depth=1 /

# find large files
find . -type f -size +100M -exec ls -lsh {} \; 2>&1 > LARGE_FILES
```

### Kernel maintainance

```
# List installed kernels
rpm -q kernel

# Check current kernel
uname -r

# Remove
sudo rpm -v -e kernel-3.10.0-693.2.2.el7.x86_64
```

