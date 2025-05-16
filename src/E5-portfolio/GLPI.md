# Mise en place d’un service d’assistance aux utilisateurs du réseau grâce au logiciel GLPI
- [Préparation du serveur LAMP sous Debian](#pr%C3%A9paration-du-serveur-lamp-sous-debian)
- [Installation de GLPI](#installation-de-glpi)

## Préparation du serveur LAMP sous Debian
Tout d’abord, passez en root en tapant :
```
su
```

Vérifiez que votre système est à jour :
```
apt-get update && apt-get upgrade
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_47_46.png)


Installez ensuite tous les outils nécessaires pour obtenir un serveur web LAMP (Apache MySQL/MariaDB PHP) à l’aide de la commande :
```
apt install apache2 default-mysql-server php8.2 -y
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_49_36.png)

Activez Apache et MariaDB au démarrage :
```
systemctl enable apache2 mariadb
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_50_17.png)

Vérifiez que vous avez bien la dernière version de Perl :
```
apt install perl -y
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_51_00.png)

Installez toutes les dépendances requises pour faire fonctionner GLPI :
```
apt install php-ldap php-imap php-apcu php-xmlrpc php-cas php-mysqli php-mbstring php-curl php-gd php-simplexml php-xml php-intl php-zip php-bz2 -y
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_51_53.png)
Pour finir, rechargez Apache pour qu’il prenne en compte les modifications :
```
systemctl reload apache2
```

## Installation de GLPI

Pour la mise en place de GLPI, commencez par vous rendre dans le dossier tmp :
```
cd /tmp/
```

Ici, effectuez le téléchargement de GLPI :
```
wget https://github.com/glpi-project/glpi/releases/download/10.0.6/glpi-10.0.6.tgz
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_53_32.png)

Une fois fait, décompressez le dans le dossier HTML, dossier par défaut où placer ses pages ou interfaces web :
```
tar xzf glpi-10.0.6.tgz -C /var/www/html
```

Changez le propriétaire du dossier GLPI afin d’éviter des erreurs dues à des permissions insuffisantes :
```
chown -R www-data:www-data /var/www/html/glpi
```

Modifiez les droits d’accès à ce dossier pour la même raison :
```
chmod -R 775 /var/www/html/glpi
```
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_12_55_09.png)

Passons à la configuration de la base de données. Tout d’abord, lancez MariaDB en tant que root :
```
mysql -u root
```

Vous êtes maintenant dans le SGBD et allez créer votre base de données glpi à l’aide de commandes SQL, langage propre au SGBD :
```
create database glpi;
```

Créez un utilisateur pour glpi :
```
create user glpiuser@localhost identified by "Password";
```
Donnez-lui les droits d’accès à la base de données glpi :
```
grant all privileges on glpi.* to glpiuser@localhost;
```

Rechargez ses droits :
```
flush privileges;
```

Et enfin, quittez mariadb :
```
exit;	
```

Une fois toutes ces étapes réalisées, vous avez maintenant accès à l’installation de GLPI. Pour constater le bon fonctionnement de votre réalisation, ouvrez un navigateur web tel que Firefox et allez à l’adresse suivante : `http://localhost/glpi`


Sélectionnez la langue souhaitée, puis cliquez sur OK


Cliquez sur Continuer
![ModulesGLPI](https://github.com/Mellsx/portfolio/blob/main/src/glpi/inst-glpi-vm-lin-deb-part1-i36_1.png)

Dans l'espace texte sous Serveur SQL, saisir "localhost"

Saisir les identifiants de connexion à la base de donnée saisie dans les lignes de commande précedentes

Utilisateur SQL : glpiuser

Mot de passe SQL : Password
![connexionDB](https://github.com/Mellsx/portfolio/blob/main/src/glpi/inst-glpi-vm-lin-deb-part1-i37_1.png)


Sélectionner la base de donnée "glpi", puis cliquez sur "Continuer" jusqu'à l'étape 6
![ModulesGLPI](https://github.com/Mellsx/portfolio/blob/main/src/glpi/inst-glpi-vm-lin-deb-part1-i38_1.png)


Cliquez sur "Utiliser GLPI"
![Screenshot_root&update](https://github.com/Mellsx/portfolio/blob/main/src/glpi/VirtualBox_DebGLPI_03_01_2025_13_01_14.png)

Saisir les identifiants automatique du compte administrateur

Indentifiant : glpi

Mot de passe : glpi

![ModulesGLPI](https://github.com/Mellsx/portfolio/blob/main/src/glpi/inst-glpi-vm-lin-deb-part1-i41_1.png)


## Pour relier le serveur GLPI au réseau informatique déjà en place

Dans les paramètres de la vm servant de serveur glpi, désactiver l'interface réseau en accès par pont.
Paramétrer une nouvelle interface réseau en réseau interne qu'on nommera "Maintenance".

Dans les paramètres de la vm servant de routeur, ajouter une nouvelle interface réseau en réseau interne "Maintenance".

Dans le routeur, aller dans les paramètres réseau et configurer la nouvelle interface (celle qui n'a pas d'adresse IPv4) avec 
IP : 10.0.170.1
masque sous-réseaux : 255.255.255.0
passerelle : 10.170.0.1

Dans le terminal, se connecter en tant que root et saisir :
ip route add 10.0.170.0/24 via 10.0.170.1

Dans le serveur glpi, aller dans les paramètres réseaux et configurer l'adresse IPv4 de l'interface en manuel, avec :
IP : 10.0.170.2
masque sous-réseaux : 255.255.255.0
passerelle : 10.170.0.1

Pour tester que le serveur fonctionne correctement, il faut se connecter à l'interface glpi depuis la machine cliente sur le réseau "Direction".
Une fois la VM lancée, ouvrir le navigateur.
Dans la barre URL, saisir "10.0.170.2/glpi". Vous arriverez sur l'interface de connexion du site.
Pour vous connecter avec le compte d'un utilisateur classique :
nom d'utilisateur : normal
mot de passe : normal



Fil d'un ticket - test de fonctionnalité

Compte utilisateur : post-only/postonly
Compte technicien : tech/tech

Se connecter sur le compte utilisateur
Sur le panneau de menu à gauche, cliquer sur "Create a ticket"
Choisir le type de ticket, la catégorie (créés par l'administrateur) et l'urgence.
Saisir le titre et le message.
Cliquer sur "Submit message" pour soumettre le ticket.

Se connecter au compte technicien
Cliquer sur l'onglet "Global view" pour voir les tickets qui n'ont été attribué à personne.
Dans les menus, à droite des statuts, un nombre indique le nombre de ticket en attente pour chacun.
Une fois le ticket ouvert, pour répondre, cliquer sur "Answer", puis "Save" une fois le message écrit.
Dans le cas où le message répond à la demande de l'utilisateur, on peut passer le statut du ticket sur "Solved".
A l'utilisateur, ensuite de confirmer en approuvant la fermeture du ticket. Le statut passe alors en "Closed".
