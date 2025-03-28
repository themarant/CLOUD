# TP3 : Self-hosted private cloud platform
## 0. Prérequis
- Création de 3 `Rocky`
![](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExa3BkZGZqbzZza2N0N284MmpuNGVmMnh2eWg3ZXQ2a2E3aDdtOGQ1diZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/DSnBnPOAEYvV2YcaX1/giphy.gif)
## I. Présentation du lab
### 1. Architecture
🌞 Allumez les VMs et effectuez la conf élémentaire :
- ping `kvm1.one` depuis `frontend.one`
~~~
[root@frontend network-scripts]# ping kvm1.one
PING kvm1.one (10.3.1.11) 56(84) bytes of data.
64 bytes from kvm1.one (10.3.1.11): icmp_seq=1 ttl=64 time=1.63 ms
64 bytes from kvm1.one (10.3.1.11): icmp_seq=2 ttl=64 time=1.29 ms
64 bytes from kvm1.one (10.3.1.11): icmp_seq=3 ttl=64 time=0.485 ms
~~~
- ping `kvm2.one` depuis `frontend.one`
~~~
root@frontend network-scripts]# ping kvm2.one
PING kvm2.one (10.3.1.12) 56(84) bytes of data.
64 bytes from kvm2.one (10.3.1.12): icmp_seq=1 ttl=64 time=1.52 ms
64 bytes from kvm2.one (10.3.1.12): icmp_seq=2 ttl=64 time=1.62 ms
64 bytes from kvm2.one (10.3.1.12): icmp_seq=3 ttl=64 time=1.47 ms
~~~
## II. Setup
### 1. Frontend
[Fontend setup](https://github.com/themarant/CLOUD/blob/main/TP3/Fontend/)

![](https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExZjA0bTFqdTM3MXVmamU2MGVva2RwNDE1dTQ2dWxkOXQ3NXlrOHZvZyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/76gaWZqxxLwGMhhAMp/giphy.webp)

### 2. Noeuds KVM
[Noeud setup](https://github.com/themarant/CLOUD/blob/main/TP3/Noeuds/SETUP.md)

![](https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExd3JlcnVobGFyMXRuYjFyMWN0YzZzcmdsbDh5NGpjYzdjNG92dzZsdiZlcD12MV9naWZzX3NlYXJjaCZjdD1n/j6MMHvVSIAzhAiP2IZ/200.webp)

### 3. Réseau

[Network setup](https://github.com/themarant/CLOUD/blob/main/TP3/Reseau/SETUP.md)

![](https://media1.tenor.com/m/NnpkTGoGoWgAAAAd/shocked-reading.gif)

## III. Utiliser la plateforme
## IV. Ajouter d'un noeud et VXLAN
### 1. Ajout d'un noeud
🌞 Setup de `kvm2.one`, à l'identique de `kvm1.one`

se referer à 2. Neouds KVM pour l'ip statique

se referer à 3. Réseau
### 2. VM sur le deuxième noeud
~~~
[oneadmin@frontend ~]$ ssh -J kvm2.one root@10.220.220.2
The authenticity of host '10.220.220.2 (<no hostip for proxy command>)' can't be established.
ED25519 key fingerprint is SHA256:1h3xhqpWsgqOBiWJcuOVoMiEBRdJfF5sy7K5Vb9EzRo.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.220.220.2' (ED25519) to the list of known hosts.
[root@localhost ~]# 
~~~
### 3. Connectivité entre les VMs
- depuis la vm sur `kvm1`
~~~
[root@localhost ~]# ping 10.220.220.2
PING 10.220.220.2 (10.220.220.2) 56(84) bytes of data.
64 bytes from 10.220.220.2: icmp_seq=1 ttl=64 time=8.92 ms
64 bytes from 10.220.220.2: icmp_seq=2 ttl=64 time=4.45 ms
64 bytes from 10.220.220.2: icmp_seq=3 ttl=64 time=1.70 ms
~~~
- depuis la vm sur `kvm2`
~~~
[root@localhost ~]# ping 10.220.220.1
PING 10.220.220.1 (10.220.220.1) 56(84) bytes of data.
64 bytes from 10.220.220.1: icmp_seq=1 ttl=64 time=1.97 ms
64 bytes from 10.220.220.1: icmp_seq=2 ttl=64 time=3.73 ms
64 bytes from 10.220.220.1: icmp_seq=3 ttl=64 time=4.17 ms
~~~
### 4. Inspection du trafic

[meo.pcap](https://github.com/themarant/CLOUD/blob/main/TP3/meo.pcap)

![](https://tenor.com/fr/view/finished-im-so-done-wipe-hands-spongebob-gif-13963789363351788284)
