La société HEALTH NORTH fait partie des leaders européens sur les prélèvements médicaux pour les particuliers.

Fondé en 1987 avec l’ouverture de trois laboratoires diagnostiques et d’imagerie au Danemark, le groupe s’est rapidement développé en appliquant une stratégie d’acquisition de laboratoires partenaires de qualité sur l’ensemble du continent européen.

Cette année, Health NORTH fusionne avec la grande entreprise d’hospitalisation privée, présente en Suède, en Norvège, en Finlande, en France et au Royaume-Uni. Grâce à cette fusion, la structure devient alors le leader incontesté des services diagnostiques et d’hospitalisation en Europe.

Health NORTH exploite son expertise en médecine de laboratoire, en imagerie et en pathologie pour fournir des réponses aux questions diagnostiques dans toutes les disciplines médicales. Notre catalogue de services couvre tous les aspects du diagnostic, notamment dans les domaines suivants :
- Chirurgie ambulatoire;
- Hospitalisation;
- Imagerie médicale;
- Médecine reproductive et génétique;
- Cytopathologie et biologie médicale;
- Tests spécialisés.

La biologie médicale est une composante importante du système de santé. Elle concourt au
diagnostic, au dépistage, à l’évaluation des risques, au suivi des patients, etc.
Quelques chiffres :
- Nombre d’employés : 12 000 €
- Nombre de médecins : 5000
- Nombre de cliniques : 300
- Nombre d’imagerie : 1200
- Chiffre d’affaires : plus de 50 milliards (annuel)
- Nombre d’analyse : 8 millions/an

Suite à la fusion, North HEALTH se doit de travailler sur la refonte des systèmes d’information de ses cliniques et laboratoires français.

Actuellement, on distingue sur le territoire Français, plusieurs types :
- Les laboratoires de prélèvement
- Les centres d’analyse où les prélèvements sont analysés
- Les cliniques

Il y a un engagement afin de fournir un résultat d’analyse sous :
- 24h pour une analyse standard
- 72h pour une analyse complexe

# Les grandes lignes du SI
L’organisation de North HEALTH est découpée en plusieurs scopes :
- SI Interne : permettant l’accès aux services des cliniques et laboratoires (connexion sur les postes, accès aux réseaux, partage de fichiers, applications métiers de suivi de patient, de facturation, de réservation de bloc opératoire, d’affectation de chirurgien, etc.), mais également les services de gestion du système d’information de l’entreprise.
- SI Externe : permettant aux patients de prendre la réservation de leurs examens, chambres et services connexes et permettant aux professionnelles de santé d’accéder au dossier patient.

# Présentation des missions :
En tant que technicien système réseau, Mr Vasquez (dsi) vous missionne sur la refonte de
l’architecture système et réseau de la clinique de Guadeloupe. Votre responsable a pu découper le projet en différentes missions afin de planifier la mise en production. Voici les missions identifiées par Mr Vasquez :
- Mission 1 : mise en place de l’architecture réseau de base
- Mission 2 : mise en place des services vitaux
- Mission 3 : mise en place de la documentation
- Mission 4 : mise en place des services annexes
- Mission 5 : mise en place de la haute disponibilité des services principaux

Les 5 missions sont dépendantes les unes des autres, et nécessitent le bon fonctionnement des services précédents. Un brief plus précis est disponible dans chacune des missions.

# Mission 1 : Mise en place de l'architecture réseau de base

Identifiez les dernières adresses IP de chaque réseau et remplissez la colonne
passerelle par défaut.

| Num | ID Vlan | Nom                    | Réseau        | Passerelle par défaut | Description                                                                                                                 |
| --- | ------- | ---------------------- | ------------- | --------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 1   | 69      | Poubelle               | 10.69.0.0/24  | 10.69.0.1             | Toutes les interfaces non utilisées des commutateurs sont dans ce vlan                                                      |
| 2   | 99      | Natif                  | 10.99.0.0/24  | 10.99.0.1             | Prévu pour les trames non tagué                                                                                             |
| 3   | 100     | Management des actifs  | 10.100.0.0/24 | 10.100.0.1            | Les commutateurs et équipements de routage ont une IP dans ce réseau.<br>Ce réseau permettra l’accès en SSH sur les actifs. |
| 4   | 110     | Hyperviseur            | 10.110.0.0/24 | 10.110.0.1            | Hyperviseur (esx, hyperv, proxmox, kvm, …)                                                                                  |
| 5   | 120     | Reverse Proxy          | 10.120.0.0/24 | 10.120.0.1            | Serveur de load balancing                                                                                                   |
| 6   | 130     | Web                    | 10.130.0.0/24 | 10.130.0.1            | Serveurs web                                                                                                                |
| 7   | 140     | BDD                    | 10.140.0.0/24 | 10.140.0.1            | Serveurs de base de données.                                                                                                |
| 8   | 150     | VOIP                   | 10.150.0.0/24 | 10.150.0.1            | Service de téléphonie IP                                                                                                    |
| 9   | 160     | Service vitaux         | 10.160.0.0/24 | 10.160.0.1            | Active Directory, DHCP, DNS, Partage de fichier, GPO, serveur de backup.                                                    |
| 10  | 170     | Service de maintenance | 10.170.0.0/24 | 10.170.0.1            | Serveur de Supervision, serveur de log (sai), serveur ITSM (gestion d’incident),<br>déploiement                             |
| 11  | 180     | Bastion                | 10.180.0.0/24 | 10.180.0.1            | Service de centralisation des managements équipements                                                                       |
| 12  | 300     | Service Informatique   | 10.3.0.0/24   | 10.3.0.1              | Utilisateurs                                                                                                                |
| 13  | 301     | Service Infirmier      | 10.3.10.0/24  | 10.3.10.1             | Utilisateurs                                                                                                                |
| 14  | 302     | Service Chirurgie      | 10.3.20.0/24  | 10.3.20.1             | Utilisateurs                                                                                                                |
| 15  | 303     | Service Laboratoire    | 10.3.30.0/24  | 10.3.30.1             | Utilisateurs                                                                                                                |
| 16  | 304     | Service Direction      | 10.3.40.0/24  | 10.3.40.1             | Utilisateurs                                                                                                                |
| 17  | 400     | Wifi Service           | 10.4.0.0/23   | 10.4.0.1              | Utilisateurs                                                                                                                |
| 18  | 401     | Wifi Patient           | 10.4.10.0/23  | 10.4.10.1             | Utilisateurs                                                                                                                |

Reproduisez le schéma en exploitant au choix une architecture physique ou
virtuelle

schema de la structure à créer
![[Pasted image 20250216185058.png]]

Utilisation de virtual box pour simuler la création d'un réseau

Dans les barres de menu en haut de la fenêtre, cliquez sur l'icone "New", pour créer un nouveau fichier.
![[Pasted image 20250216185329.png]]

Pour choisir le routeur, aller dans le menu des machines en bas à gauche. Dans la première ligne choisissez "Network devices", puis, dans la deuxième ligne choisissez "Routers".
![[Pasted image 20250216185805.png]]

Cliquez sur le routeur de votre choix (ici PT-Router), et faite glisser dans la zone principale.



Pour choisir les switchs, aller dans le menu des machines en bas à gauche. Dans la première ligne choisissez "Network devices", puis, dans la deuxième ligne choisissez "Routers".

Pour choisir le routeur, aller dans le menu des machines en bas à gauche. Dans la première ligne choisissez "Network devices", puis, dans la deuxième ligne choisissez "Routers".