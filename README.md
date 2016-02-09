# linux-admin-shortcuts-ops235
A few random shell scripts for convenience

#Instructions:
- Copy all scripts to /usr/local/bin/
- Run scripts WITHOUT sudo, it will prompt for sudo password if needed, or run as root.

###Usage: virsh-ip hostname
- List the ip address using the VM domain name that virsh uses
```
[username@c7host ~]$ virsh-ip centos3
[sudo] password for username: 
centos3:192.168.122.XX
```

###Usage: virsh-ssh username@hostname/hostname
- requires virsh-ip
- Use virsh domain names to ssh, do not need an ip address
```
[username@c7host ~]$ virsh-ssh ops235@centos3
[sudo] password for username: 
ops235@centos3
Running Command: ssh ops235@192.168.122.XX
[ops235@centos3 ~]$ 
```

###Usage: run-virt-manager
- This is only used if you connect to remote computers over ssh with X Forwarding. Gives the proper authentication to run virt-manager remotely.
