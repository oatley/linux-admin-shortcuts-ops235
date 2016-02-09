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
##### How does it work?
Uses virsh dumpxml vmname to get the vm's mac address. Then performs an arp command and finds the ip address using the mac.

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
##### How does it work?
It's just a wrapper for ssh, which uses vm domains instead of hostnames, and uses virsh-ip to get the ip addresses.

###Usage: run-virt-manager
- This is only used if you connect to remote computers over ssh with X Forwarding. Gives the proper authentication to run virt-manager remotely.

##### How does it work?
The virt-manager command cannot be run as normal user and requires root access. As a graphical application it's unlikely that you will get it to run as root remotely. So it uses a normal user's XAuthority file to authenticate with the X Server and sudo to up the user's permission.
