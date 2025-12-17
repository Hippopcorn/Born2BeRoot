*This project has been created as part of the 42 curriculum by evarache.*

# Description

This project aimed to create my own virtual machine on VirtualBox. I chose to install the latest version of Debian, which is a Linux operating system. The advantages of Debian are that it is stable, free, open-source, and consumes few system resources.
I set up every partition of the layout. Then I set up a SSH service running on port 4242.
The hostname of the VM is evarache42 and I created a user named evarache.
A script called monitoring.sh is executing every 10 minutes with crontab and display some information on all terminals (architecture of operating system, RAM, storage, processors, last reboot, number of users...) I installed WordPress which work with lighttpd, MariaDB and PHP.
Apt (Advanced Package Tool) is the package manager that handles the installation and removal of software.


# Instructions

Open the VM corresponding to the signature.txt.

To connect to the VM from our machine, use the command :
```ssh user_name@localhost -p 4241```

If you want to create a new user, you can use 
```sudo adduser user_name``` To create a group, use :
```sudo addgroup group_name```
To add a user to a group : ```sudo adduser <user_name> <group_name>```

## Policy
The policy of sudo is located in this file ```etc/sudoers.d/sudo_config```
You have several rules to create a password, located in this file : ```/etc/login.defs```


## Services

A website with WordPress is reacheable in the port 3000 : 
```localhost:3000```

Netdata is reacheable on the port 1372 :
```localhost:1372```

# Ressources

https://www.debian.org/index.fr.html

https://wordpress.com/fr/

https://www.lighttpd.net/

https://mariadb.org/

https://www.php.net/

https://www.netdata.cloud/