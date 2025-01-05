# Création d'un controleur de domaine sous Windows Server 2019
## Mise en place du service ADDS

Pour attribuer le rôle de contrôleur de domaine au serveur, Ouvrez le « Gestionnaire de Serveur », cliquez sur le menu « Gérer », puis « Ajouter des rôles et fonctionnalités »
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/1.png)

Dans la section « Type d’installation », sélectionnez « Installation basée sur un rôle ou une fonctionnalité »
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/2.png)

Sélectionnez le serveur actuel dans le pool de serveurs
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/3.png)

Choisissez les rôles que tiendra le serveur, soit « Service AD DS » et "Service DNS"
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/4.png)

Passez les pages grâce au bouton « Suivant », jusqu’à la page de Confirmation.
Cliquez sur le bouton « Installer » pour lancer l’installation des services choisis.  
Une fois l’installation terminé, fermer la fenêtre. 

Dans le Gestionnaire de serveur, Cliquez sur le drapeau, puis sur « Promouvoir ce serveur en contrôleur de domaine »
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/5.png)

Dans configuration de déploiement, prenez l’option « Ajouter une nouvelle forêt » et saisissez le nom du domaine à créer
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/6.png)

Mettre un nouveau mot de passe pour le mode de restauration des services d’annuaires
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/7.png)

Dans « Options DNS », ne pas cocher « Créer une délégation DNS »

Dans options supplémentaires, le nom de domaine NetBIOS est saisi automatiquement
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/8.png)

Aucune modification pour les chemins d’accès
![image](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/9.png)

Après l’installation, le redémarrage se fera automatiquement.

Dans le gestionnaire de serveur, aller dans la section DNS.
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_18_20.png)

Faites un clique droit sur la ligne du serveur, et cliquez sur "Gestionnaire DNS"
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_19_18.png)

Dans le serveur, faites un clique droit sur le dossier "Zone de recherche inversée" et sélectionnez "Nouvelle zone"
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_22_00.png)

Cliquez sur suivant
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_22_21.png)

Sélectionnez "zone principale" et cochez "Enregistrer dans la zone Active Directory", puis cliquez sur suivant
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_23_31.png)

Sélectionnez l'étendue des DNS exécutés dans ce domaine, puis cliquez sur suivant
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_24_06.png)

Sélectionnez la "zone de recherche inversée IPv4"
![img](https://github.com/Mellsx/portfolio/blob/main/src/DomainControler/VirtualBox_StudiSRV01_05_01_2025_15_24_13.png)




