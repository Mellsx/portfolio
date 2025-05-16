# Création d'un controleur de domaine sous Windows Server 2019, avec les services AD DS, DNS, DHCP

- [Installation des rôles AD DS et DNS](#installation%20des%20rôles%20AD%20DS%20et%20DNS)
- [Configuration de l'Active Directory](#configuration%20de%20l'active%20directory)
- [Configuration du DNS](#Configuration%20du%20DNS)
- [Installation du rôle DHCP](#Installation%20du%20rôle%20DHCP)
- [Configuration DHCP](#Configuration%20DHCP)

## Installation des rôles AD DS et DNS
Pour attribuer le rôle de contrôleur de domaine au serveur, Ouvrez le « Gestionnaire de Serveur », cliquez sur le menu « Gérer », puis « Ajouter des rôles et fonctionnalités »

![img](https://github.com/Mellsx/portfolio/blob/main/src/E5-portfolio/img/1.png)
![image](./img/1.png)

Dans la section « Type d’installation », sélectionnez « Installation basée sur un rôle ou une fonctionnalité »
![image](./img/2.png)

Sélectionnez le serveur actuel dans le pool de serveurs
![image](./img/3.png)

Choisissez les rôles que tiendra le serveur, soit « Service AD DS » et "Service DNS"
![image](./img/4.png)

Passez les pages grâce au bouton « Suivant », jusqu’à la page de Confirmation.
Cliquez sur le bouton « Installer » pour lancer l’installation des services choisis.  
Une fois l’installation terminé, fermer la fenêtre. 

## Configuration de l'Active Directory
Dans le Gestionnaire de serveur, Cliquez sur le drapeau, puis sur « Promouvoir ce serveur en contrôleur de domaine »
![image](./img/5.png)

Dans configuration de déploiement, prenez l’option « Ajouter une nouvelle forêt » et saisissez le nom du domaine à créer
![image](./img/6.png)

Mettre un nouveau mot de passe pour le mode de restauration des services d’annuaires
![image](./img/7.png)

Dans « Options DNS », ne pas cocher « Créer une délégation DNS »

Dans options supplémentaires, le nom de domaine NetBIOS est saisi automatiquement
![image](./img/8.png)

Aucune modification pour les chemins d’accès
![image](./img/9.png)

Après l’installation, le redémarrage se fera automatiquement.

## Configuration du DNS
Dans le gestionnaire de serveur, aller dans la section DNS.
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_18_20.png)

Faites un clique droit sur la ligne du serveur, et cliquez sur "Gestionnaire DNS"
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_19_18.png)

Dans le serveur, faites un clique droit sur le dossier "Zone de recherche inversée" et sélectionnez "Nouvelle zone"
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_22_00.png)

Cliquez sur suivant
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_22_21.png)

Sélectionnez "zone principale" et cochez "Enregistrer dans la zone Active Directory", puis cliquez sur suivant
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_23_31.png)

Sélectionnez l'étendue des DNS exécutés dans ce domaine, puis cliquez sur suivant
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_24_06.png)

Sélectionnez la "zone de recherche inversée IPv4", puis cliquez sur suivant
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_24_13.png)

Saisir les 3 premiers nombres communs aux adresses IPv4 du réseau, puis cliquez sur suivant
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_24_45.png)

Autorisez toutes les mises à jours et cliquez sur suivant
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_26_08.png)

Cliquez sur "Terminer"
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_26_20.png)

Dans le serveur, dans le dossier Zones de recherche directe, cliquez sur le sous dossier du nom de domaine
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_27_23.png)

Faire un double-clique sur le fichier portant le nom du serveur
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_27_39.png)

Cochez "Mettre à jour l'enregistrement de pointeur (PTR)", et cliquez sur Appliquer puis Fermer
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_27_48.png)

## Installation du rôle DHCP
Dans le gestionnaire de serveur, cliquez sur Ajouter des rôles et des fonctionnalités
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_30_15.png)

Cliquez sur suivant jusqu'à la page "rôle du serveur"
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_30_24.png)
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_30_29.png)
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_30_36.png)

Cochez le rôle "Serveur DHCP"
![img](./img/VirtualBox_StudiSRV01_05_01_2025_15_31_10.png)

Cliquez sur suivant jusqu'à la page "Confirmation"
Cliquez sur "Installer" et fermer la fenêtre
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2017-20-09.png)

## Configuration DHCP
Dans le gestionnaire de serveur, cliquez sur le drapeau, puis sur "Terminer la configuration DHCP"
![image](./img/apture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2017-20-33.png)

Cliquez sur "Suivant"
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-33-20.png)

Cliquez sur "Valider"
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-33-27.png)

Cliquez sur "Fermer"
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-33-31.png)

Dans le Gestionnaire de serveur, aller dans la section DHCP, faites un clique droit sur le serveur et choissisez "Gestionnaire DHCP"
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-34-43.png)

Dans la section du serveur, faites un clique droit sur "IPv4", et choisisez "Nouvelle étendue"
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-35_19.png)

Cliquez sur suivant
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-35-22.png)

Saisissez le nom de l'étendue que vous voulez créer, puis cliquez sur suivant
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-35-34.png)

Inscrire les adresses IP de début et de fin de la plage d'adresse à distribuer, adapter le masque sous réseau à la taille de la plage donnée, puis cliquez sur suivant.
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-36_43.png)

Cliquez sur suivant
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-36-46.png)

Saisissez la durée limites d'atribution d'une adresse IP à une machine,puis cliquez sur suivant
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-36-52.png)

Ajouter l'adresse du routeur du réseau
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-37-08.png)

Cliquez sur "Suivant" jusqu'à la page de fin, où vous cliquerez sur "Terminer"
![image](./img/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-05%2015-38-08.png)


