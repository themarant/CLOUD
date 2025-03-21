# II.1. Setup Frontend
## A. Database
🌞 Installer un serveur MySQL
~~~
[root@frontend ~]# wget https://dev.mysql.com/get/mysql80-community-release-el9-5.noarch.rpm

[root@frontend ~]# sudo rpm -ivh mysql80-community-release-el9-5.noarch.rpm
~~~
~~~
[root@frontend ~]# sudo dnf install -y mysql-community-server
~~~
🌞 Démarrer le serveur MySQL
~~~
[root@frontend ~]# systemctl status mysqld
● mysqld.service - MySQL Server
     Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; preset: disabled)
     Active: active (running) since Fri 2025-03-21 10:49:38 CET; 19s ago
~~~
🌞 Setup MySQL
~~~
[root@frontend ~]# sudo grep 'temporary password' /var/log/mysqld.log
2025-03-21T09:49:29.115783Z 6 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: dilyKkK?A0uk

mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'Azertyuiop123!';
Query OK, 0 rows affected (0.03 sec)

mysql> CREATE USER 'oneadmin' IDENTIFIED BY 'Azertyuiop123!';
Query OK, 0 rows affected (0.05 sec)

mysql> CREATE DATABASE opennebula;
Query OK, 1 row affected (0.03 sec)

mysql> GRANT ALL PRIVILEGES ON opennebula.* TO 'oneadmin';
Query OK, 0 rows affected (0.03 sec)

mysql> SET GLOBAL TRANSACTION ISOLATION LEVEL READ COMMITTED;
Query OK, 0 rows affected (0.00 sec)
~~~
## B. OpenNebula
🌞 Ajouter les dépôts Open Nebula
~~~
[root@frontend ~]# sudo cat /etc/yum.repos.d/opennebula.repo
[opennebula]
name=OpenNebula Community Edition
baseurl=https://downloads.opennebula.io/repo/6.8/RedHat/$releasever/$basearch
enabled=1
gpgkey=https://downloads.opennebula.io/repo/repo2.key
gpgcheck=1
repo_gpgcheck=0

[root@frontend ~]# sudo dnf makecache -y
MySQL 8.0 Community Server                                             16 kB/s | 2.6 kB     00:00
MySQL Connectors Community                                             24 kB/s | 2.6 kB     00:00
MySQL Tools Community                                                  19 kB/s | 2.6 kB     00:00
OpenNebula Community Edition                                          637 kB/s | 675 kB     00:01
Rocky Linux 9 - BaseOS                                                5.0 kB/s | 4.1 kB     00:00
Rocky Linux 9 - AppStream                                              10 kB/s | 4.5 kB     00:00
Rocky Linux 9 - Extras                                                5.1 kB/s | 2.9 kB     00:00
Metadata cache created.
~~~
🌞 Installer OpenNebula
~~~
[root@frontend ~]# sudo dnf install opennebula opennebula-sunstone opennebula-fireedge
~~~
🌞 Créer un user pour se log sur la WebUI OpenNebula
~~~
[root@frontend ~]# sudo cat /var/lib/one/.one/one_auth
oneadmin:azertyuiop
marant:azertyuiop
~~~
🌞 Démarrer les services OpenNebula
~~~
[root@frontend ~]# sudo dns install opennebula
[root@frontend ~]# sudo systemctl status opennebula
● opennebula.service - OpenNebula Cloud Controller Daemon
     Loaded: loaded (/usr/lib/systemd/system/opennebula.service; disabled; preset: disabled)
     Active: active (running) since Fri 2025-03-21 11:44:11 CET; 13s ago

[root@frontend ~]# sudo dnf install opennebula-sunstone opennebula-fireedge
Last metadata expiration check: 0:27:55 ago on Fri Mar 21 11:16:55 2025.
Package opennebula-sunstone-6.10.0.1-1.el9.noarch is already installed.
Package opennebula-fireedge-6.10.0.1-1.el9.x86_64 is already installed.
Dependencies resolved.
Nothing to do.
Complete!

[root@frontend ~]# sudo systemctl enable opennebula
[root@frontend ~]# sudo systemctl enable opennebula-sunstone
[root@frontend ~]# sudo systemctl enable opennebula-fireedge
~~~
## C. Conf système
🌞 Ouverture firewall
~~~
[root@frontend ~]# sudo firewall-cmd --list-ports
22/tcp 2633/tcp 4124/tcp 9869/tcp 29876/tcp 4124/udp
~~~
## D. Test
![](https://media4.giphy.com/media/1uz4o9ZYqNDanMXVUR/giphy.webp?cid=790b7611uxbbkwp3ty5psq6ekjik91s1qlq1z8jzckixse79&ep=v1_gifs_search&rid=giphy.webp&ct=g)
