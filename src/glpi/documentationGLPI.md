# Préparation du serveur LAMP sous Debian
Tout d’abord, passez en root en tapant :
'''su'''

Vérifiez que votre système est à jour :
'''apt-get update && apt-get upgrade'''

Installez ensuite tous les outils nécessaires pour obtenir un serveur web LAMP (Apache MySQL/MariaDB PHP) à l’aide de la commande :

'''
apt install apache2 default-mysql-server php8.2 -y
'''

Activez Apache et MariaDB au démarrage :
'''systemctl enable apache2 mariadb'''

Vérifiez que vous avez bien la dernière version de Perl :
apt install perl -y

Installez toutes les dépendances requises pour faire fonctionner GLPI :
apt install php-ldap php-imap php-apcu php-xmlrpc php-cas php-mysqli php-mbstring php-curl php-gd php-simplexml php-xml php-intl php-zip php-bz2 -y

Pour finir, rechargez Apache pour qu’il prenne en compte les modifications :
systemctl reload apache2

# Installation de GLPI

Pour la mise en place de GLPI, commencez par vous rendre dans le dossier tmp :
CTRL+C pour copier, CTRL+V pour coller
1

cd /tmp/

cd /tmp/

Ici, effectuez le téléchargement de GLPI :
CTRL+C pour copier, CTRL+V pour coller
1

wget https://github.com/glpi-project/glpi/releases/download/10.0.6/glpi-10.0.6.tgz

wget https://github.com/glpi-project/glpi/releases/download/10.0.6/glpi-10.0.6.tgz

Une fois fait, décompressez le dans le dossier HTML, dossier par défaut où placer ses pages ou interfaces web :
CTRL+C pour copier, CTRL+V pour coller
1

tar xzf glpi-10.0.6.tgz -C /var/www/html

tar xzf glpi-10.0.6.tgz -C /var/www/html

Changez le propriétaire du dossier GLPI afin d’éviter des erreurs dues à des permissions insuffisantes :
CTRL+C pour copier, CTRL+V pour coller
1

chown -R www-data:www-data /var/www/html/glpi

chown -R www-data:www-data /var/www/html/glpi

Modifiez les droits d’accès à ce dossier pour la même raison :
CTRL+C pour copier, CTRL+V pour coller
1

chmod -R 775 /var/www/html/glpi

chmod -R 775 /var/www/html/glpi

Méthode
Configuration de la BDD

Passons à la configuration de la base de données. Tout d’abord, lancez MariaDB en tant que root :
CTRL+C pour copier, CTRL+V pour coller
1

mysql -u root

mysql -u root

Vous êtes maintenant dans le SGBD et allez créer votre base de données glpi à l’aide de commandes SQL, langage propre au SGBD :
CTRL+C pour copier, CTRL+V pour coller
1

create database glpi;

create database glpi;

Créez un utilisateur pour glpi :
CTRL+C pour copier, CTRL+V pour coller
1

create user glpiuser@localhost identified by "motdepassedevotrechoix";

create user glpiuser@localhost identified by "motdepassedevotrechoix";

Donnez-lui les droits d’accès à la base de données glpi :
CTRL+C pour copier, CTRL+V pour coller
1

grant all privileges on glpi.* to glpiuser@localhost;

grant all privileges on glpi.* to glpiuser@localhost;

Note : dans le cas d’une installation à distance, vous pouvez remplacer localhost par % afin d’autoriser toutes les connexions à distance, ou par l’adresse IPv4 de l’ordinateur distant pour plus de sécurité.

Rechargez ses droits :
CTRL+C pour copier, CTRL+V pour coller
1

flush privileges;

flush privileges;

Et enfin, quittez mariadb :
CTRL+C pour copier, CTRL+V pour coller
1

exit;	

exit;	

Une fois toutes ces étapes réalisées, vous avez maintenant accès à l’installation de GLPI. Pour constater le bon fonctionnement de votre réalisation, ouvrez un navigateur web tel que Firefox et allez à l’adresse suivante : http://localhost/glpi ou http://ADRESSEIP/glpi.
Installation de GLPI 
Créer un compte utilisateur
Créer un ticket
