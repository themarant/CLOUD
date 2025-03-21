# II.2. Noeuds KVM
## A. KVM
- installation `kvm1.one`
🌞 Ajouter des dépôts supplémentaires
~~~
[root@kvm1 yum.repos.d]# ls
opennebula.repo  rocky-addons.repo  rocky-devel.repo  rocky-extras.repo  rocky.repo
~~~
~~~
[root@kvm1 marant]# sudo systemctl status mysqld
● mysqld.service - MySQL Server
     Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; preset: disabled)
     Active: active (running) since Fri 2025-03-21 16:21:29 CET; 5min ago
~~~
~~~
[root@kvm1 yum.repos.d]# dnf install -y epel-release
Last metadata expiration check: 0:02:26 ago on Fri Mar 21 13:15:47 2025.
Dependencies resolved.
======================================================================================================
 Package                     Architecture          Version                Repository             Size
======================================================================================================
Installing:
 epel-release                noarch                9-7.el9                extras                 19 k
~~~
🌞 Installer les libs MySQL
~~~
[root@kvm1 yum.repos.d]# ls
mysql-community.repo 
~~~
🌞 Installer KVM
~~~
[root@kvm1 marant]# dnf install opennebula-node-kvm
Last metadata expiration check: 0:05:45 ago on Fri Mar 21 16:29:00 2025.
Package opennebula-node-kvm-6.10.0.1-1.el9.noarch is already installed.
Dependencies resolved.
Nothing to do.
Complete!
~~~
🌞 Démarrer le service libvirtd
~~~
[root@kvm1 marant]# sudo systemctl status libvirtd
● libvirtd.service - libvirt legacy monolithic daemon
     Loaded: loaded (/usr/lib/systemd/system/libvirtd.service; enabled; preset: disabled)
     Active: active (running) since Fri 2025-03-21 16:36:21 CET; 11s ago
~~~
- installation `kvm2.one`
🌞 Ajouter des dépôts supplémentaires
~~~
[root@kvm2 yum.repos.d]# ls
opennebula.repo  rocky-addons.repo  rocky-devel.repo 
~~~
~~~
[root@kvm2 marant]# sudo systemctl status mysqld
● mysqld.service - MySQL Server
     Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; preset: disabled)
     Active: active (running) since Fri 2025-03-21 17:56:24 CET; 5s ago
~~~
~~~
[root@kvm2 yum.repos.d]# dnf install -y epel-release
Bad id for repo: root@frontend ~, byte = @ 4
Last metadata expiration check: 0:06:58 ago on Fri Mar 21 17:53:43 2025.
Dependencies resolved.
======================================================================================================
 Package                     Architecture          Version                Repository             Size
======================================================================================================
Installing:
 epel-release 
~~~
🌞 Installer les libs MySQL
~~~
[root@kvm2 yum.repos.d]# ls
mysql-community.repo 
~~~
🌞 Installer KVM
~~~
[root@kvm2 yum.repos.d]# dnf install opennebula-node-kvm
Bad id for repo: root@frontend ~, byte = @ 4
Last metadata expiration check: 0:05:02 ago on Fri Mar 21 18:01:56 2025.
Package opennebula-node-kvm-6.10.0.1-1.el9.noarch is already installed.
Dependencies resolved.
Nothing to do.
Complete!
~~~
🌞 Démarrer le service libvirtd
~~~
[root@kvm2 ~]# sudo systemctl status libvirtd
● libvirtd.service - libvirt legacy monolithic daemon
     Loaded: loaded (/usr/lib/systemd/system/libvirtd.service; enabled; preset: disabled)
     Active: active (running) since Fri 2025-03-21 18:18:03 CET; 10s ago
TriggeredBy: ● libvirtd.socket
~~~
## B. Système
🌞 Ouverture firewall
- `kvm1`
~~~
[root@kvm1 marant]# sudo firewall-cmd --list-ports
22/tcp 8472/udp
~~~
- `kvm2`
~~~
[root@kvm2 ~]# sudo firewall-cmd --list-ports
22/tcp 8472/udp
~~~
🌞 Handle SSH

![](https://media.tenor.com/HLWyRrmoKV0AAAAM/install-everything.gif)

- ssh-copy-id
~~~
[oneadmin@frontend .ssh]$ ssh-copy-id oneadmin@10.3.1.11
Number of key(s) added: 1

[oneadmin@frontend .ssh]$ ssh-copy-id oneadmin@10.3.1.12
Number of key(s) added: 1
~~~
- ssh-keyscan
~~~
[oneadmin@frontend ~]$ ssh oneadmin@10.3.1.11
Last login: Fri Mar 21 18:24:57 2025
[oneadmin@kvm1 ~]$

[oneadmin@frontend ~]$ ssh oneadmin@10.3.1.12
Last login: Fri Mar 21 18:24:34 2025
[oneadmin@kvm2 ~]$
~~~
