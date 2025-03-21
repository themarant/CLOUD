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



![](https://media1.tenor.com/m/NnpkTGoGoWgAAAAd/shocked-reading.gif)
