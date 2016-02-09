# linux-admin-shortcuts-ops235
A few random shell scripts for convenience

#Instructions:
- Copy all scripts to /usr/local/bin/
- Run scripts WITHOUT sudo, it will prompt for sudo password if needed, or run as root.

###Usage: virsh-ip hostname
- List the ip address using the VM domain name that virsh uses

###Usage: virsh-ssh username@hostname/hostname
- requires virsh-ip
- Use virsh domain names to ssh, do not need an ip address

###Usage: run-virt-manager
- This is only used if you connect to remote computers over ssh with X Forwarding. Gives the proper authentication to run virt-manager remotely.
