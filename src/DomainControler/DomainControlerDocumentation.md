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
