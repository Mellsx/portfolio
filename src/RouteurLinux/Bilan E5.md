
Config 1 : 

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-03-44.png)
![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-05-03.png)

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-03-37.png)
![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-05-45.png)

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Capture%20d%E2%80%99%C3%A9cran%20du%202025-03-24%2020-03-56.png)
```
config
set interfaces ethernet eth0 address 10.3.40.1/24
set interfaces ethernet eth1 address 10.0.160.1/24
commit
save
```

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Pasted%20image%2020250324203211.png)


![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Pasted%20image%2020250324203414.png)

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Pasted%20image%2020250324203605.png)

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Pasted%20image%2020250324203850.png)

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Pasted%20image%2020250324203956.png)

![image](https://github.com/Mellsx/portfolio/blob/main/src/RouteurLinux/Pasted%20image%2020250324204139.png)

Routeur - règles NAT
```
set nat source rule 10 outbound-interface name eth0
set nat source rule 10 source address 10.0.160.0/24
set nat source rule 10 translation adresse masquerade

set nat source rule 20 outbound-interface name eth1
set nat source rule 20 source address 10.3.40.0/24
set nat source rule 20 translation adresse masquerade
```
