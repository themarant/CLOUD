# II.3. Setup réseau
## A. Intro
![](https://media.tenor.com/8QUWgWQU9ZYAAAAM/networking-you-gotta-networking.gif)
## B. Création du Virtual Network
![](https://media.tenor.com/2XNnziYIiFEAAAAM/network-nft-build-your-network.gif)
## C. Préparer le bridge réseau
🌞 Créer et configurer le bridge Linux
~~~
[root@kvm1 opt]# sudo systemctl status vxlan
● vxlan.service - Setup VXLAN interface for ONE
     Loaded: loaded (/etc/systemd/system/vxlan.service; enabled; preset: disabled)
     Active: active (exited) since Sun 2025-03-23 12:33:53 CET; 10s ago
~~~
~~~
[oneadmin@kvm1 ~]$ ip a show vxlan_bridge
4: vxlan_bridge: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UNKNOWN group default qlen 1000
    link/ether be:03:9c:d6:15:57 brd ff:ff:ff:ff:ff:ff
    inet 10.220.220.201/24 scope global vxlan_bridge
       valid_lft forever preferred_lft forever
    inet6 fe80::bc03:9cff:fed6:1557/64 scope link
       valid_lft forever preferred_lft forever
~~~
