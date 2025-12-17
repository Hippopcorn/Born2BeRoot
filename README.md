*This project has been created as part of the 42 curriculum by evarache.*

# Description

This project aimed to create my own virtual machine on VirtualBox. 
I chose to install Debian and set up every partition of the layout. Then I set up a SSH service running on port 4242.
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
Then, to allow a user to connect with SSH, open this file ```/etc/ssh/sshd_config``` and add the user on the line AllowUsers. Ex : AllowUsers user1 user2

If you want to change the hostname Change the hostname, you can change it in the files ```/etc/hostname``` and ```/etc/hosts``` and then use ```sudo reboot```
If you want to change a password, you can use ```sudo passwd root``` for the root password or ```sudo passwd user``` for an user password.


## Policy
The policy of sudo is located in this file ```etc/sudoers.d/sudo_config```
You have several rules to create a password, located in this file : ```/etc/login.defs```


## Script
A script named monitoring.sh is running every 10 minutes. If you want to interrupt it, you must modify crontab with ```sudo crontab -u root -e```


## Services

WordPress is reacheable in the port 3000 : 
```localhost:3000```

Netdata is reacheable on the port 1372 :
```localhost:1372```

# Project description

I chose to install the latest version of Debian, which is a Linux operating system. The advantages of Debian are that it is stable, free, open-source, and consumes few system resources.
I am using AppArmor because it is the native security system for Debian. It is based on file paths, which makes the creation of security profiles more intuitive.
I chose UFW because it is the default tool on Debian. Its syntax is simple and intuitive, allowing for the quick configuration of a robust security policy: blocking everything by default and only opening the necessary ports (SSH 4242, HTTP 80, etc.).
I chose VirtualBox because it offers excellent performance and a comprehensive set of features. It provides advanced networking configurations and robust snapshot management, both of which are essential for testing security policies during development.

**WordPress** is the most popular Content Management System globally, enabling the development of dynamic web applications.
PHP-FPM processes the WordPress scripts. MariaDB stores and serves the site's data. For the web service, I use Lighttpd, a secure and lightweight web server 
designed for high-performance environments with low memory footprint.

**Netdata** is a real-time monitoring tool. It is configured to monitor CPU and RAM usage, analyze the performance of LVM partitions and
alert in the event of anormal system load.


# Ressources

https://www.debian.org/index.fr.html

https://wordpress.com/fr/

https://www.lighttpd.net/

https://mariadb.org/

https://www.php.net/

https://www.netdata.cloud/