### Host names

There are *three* host names
* Static, defined in `/etc/hostname`
* Transient, maintained by kernel
* Pretty, for representation.

View hostnames `hostnamectl status`.

Change all three hostnames `hostnamectl set-hostname <FQDN>`.

### Config files

```
/etc/hosts
/etc/resolv.conf
/etc/sysconfig/network
/etc/sysconfig/network-scripts/ifcfg-<interface-name>
```
### Interface definitions

```
# Ubuntu
/etc/networks/interfaces

# Centos
/etc/sysconfig/network-scripts/ifcfg-ens33
```

### Commands

```
# list all ip addresses on this host
ip addr | grep inet | grep -v inet6 | gawk '{print $2}'
```

### netstat

```
# list listening tcp and udp ports, and pid/program
sudo netstat -ltup

netstat -i

netstat -ie # same as ifconfig

netstat -r # same as route

netstat -s

# list active connections
netstat -atun | grep ESTA
```
