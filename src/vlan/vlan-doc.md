# Ségmentation logique d'un réseau sur CISCO Packet Tracer
## Création d'un réseau
Placer deux machines de d'accès utilisateur (ici un desktop et un laptop) et un commutateur (switch)

Relier chacune des machines end point au switch

![img](https://github.com/Mellsx/portfolio/blob/main/src/vlan/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-12%2018-59-49.png)

Dans le desktop : 
- configurer l'adresse IPv4 (192.168.10.10)
- saisir le masque de sous-réseau (255.255.255.0)
![img](https://github.com/Mellsx/portfolio/blob/main/src/vlan/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-12%2019-02-52.png)

Dans le laptop : 
- configurer l'adresse IPv4 (192.168.20.10)
- saisir le masque de sous-réseau (255.255.255.0)
![img](https://github.com/Mellsx/portfolio/blob/main/src/vlan/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-12%2019-04-29.png)

Dans le switch :
- Allumer chaque interface physique (fa0/1; fa0/2) 
```
Switch >enable (ou « en »)
Switch #conf t (ou configure terminal)
Switch(config) #int fa0/1
Switch(config-if) #no shut (ou no shutdown)
Switch(config-if) #int fa0/2
Switch(config-if) #no shut
Switch(config-if) # exit
```
![img](https://github.com/Mellsx/portfolio/blob/main/src/vlan/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-12%2019-07-38.png)

## Création des VLAN
Associer le Desktop (fa0/1 du switch) au VLAN 10
```
Switch(config) #vlan 10 (pour le VLAN du PC)
Switch(config-vlan) #int fa0/1
Switch(config-if) #switchport mode access
Switch(config-if) #switchport access vlan 10
```
![img](https://github.com/Mellsx/portfolio/blob/main/src/vlan/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-12%2019-21-16.png)

Associer le Laptop (fa0/2 du switch) au VLAN 20
```
Switch(config-if) #vlan 20 (pour le VLAN du PC)
Switch(config-vlan) #int fa0/2
Switch(config-if) #switchport mode access
Switch(config-if) #switchport access vlan 20
```
![img](https://github.com/Mellsx/portfolio/blob/main/src/vlan/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-12%2019-22-31.png)

Vérifier la création des deux VLAN avec la commande
```
Switch(config-if) #do show vlan
```
