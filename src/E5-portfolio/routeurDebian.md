Schéma de la situation

![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-04-08%2019-07-46.png)

2 réseaux NAT

Vitaux - IPv4 : 10.0.160.0/24

Direction - IPv4 : 10.3.40.0/24

---
VM1 - Vitaux - Windows 10

![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-03-44.png)
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-05-03.png)

VM2 - Direction - Windows 10

![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-03-37.png)
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-05-45.png)

VM3 - Routeur - VyOS

![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-03-56.png)
```
config
set interfaces ethernet eth0 address 10.3.40.1/24
set interfaces ethernet eth1 address 10.0.160.1/24
commit
save
```

![image](./img/Pasted%20image%2020250324203211.png)


![image](./img/Pasted%20image%2020250324203414.png)

![image](./img/Pasted%20image%2020250324203605.png)

![image](./img/Pasted%20image%2020250324203850.png)

![image](./img/Pasted%20image%2020250324203956.png)

![image](./img/Pasted%20image%2020250324204139.png)

Routeur - règles NAT
```
set nat source rule 10 outbound-interface name eth0
set nat source rule 10 source address 10.0.160.0/24
set nat source rule 10 translation adresse masquerade

set nat source rule 20 outbound-interface name eth1
set nat source rule 20 source address 10.3.40.0/24
set nat source rule 20 translation adresse masquerade
```

Changement de la typologie des réseaux: 
  Réseau NAT -> Réseau Interne


Communication du client vers Routeur OK

Communication du routeur vers client FAIL

Problème de pare-feu génant les communications

Changement du routeur : 
VyOS -> Debian

Création d'une machine avec un OS Debian pour servir de routeur

![image](./img/Pasted%20image%2020250401183614.png)

Dans le terminal :
```
ip route add 10.3.40.0/24 via 10.3.40.1
ip route add 10.0.160.0/24 via 10.0.160.1
```

ping de 10.0.160.2 vers 10.3.40.2 fonctionne et vice-versa
