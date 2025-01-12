# Création de machines virtuelles sur VirtualBox
- [Création d'une machine virtuelle](#creation%20d'une%20machine%20virtuelle)
- [Création d'un réseau](#creation%20d'un%réseau%20virtuel)
- [Installation de Windows Server 2019](#installation%20de%20Windows%20server%202019)
- [Installation de Debian](#installation%20de%20Debian)

## Création d'une machine virtuelle
## Création d'un réseau virtuel

## Installation de Windows Server 2019

Choisir les formatages liés à votre région, et cliquer sur "Suivant".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_34_03.png)

Cliquer sur "Installer maintenant".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_34_07.png)

Sélectionner le système d'exploitation avec la mention "Standard Evaluation (expérience de bureau)"
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_34_53.png)

Accepter les termes du contrat en cochant la case pour pouvoir cliquer sur "Suivant".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_35_13.png)

Si vous êtes sur une machine virtuelle, choissisez l'installation personnalisé.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_35_22.png)

Cliquer sur "Nouveau".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_35_30.png)

Cliquer sur "Appliquer".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_35_37.png)

Une fois les partitions créées, cliquer sur "Suivant"
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_35_50.png)

Choisir le mot de passe du compte administrateur, puis cliquer sur "Terminer" pour redémarrer la machine.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_40_53.png)

Une fois redémarrée, saisissez le mot de passe du compte administrateur pour vous connecter.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_WinServInstall_12_01_2025_08_41_12.png)


## Installation de Debian

Choisir l'"instalation graphique".

![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_41_43.png)

Sélectionner la langue "French - Français".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_41_58.png)

Choisir le pays "France".

![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_42_01.png)

Choisir la langue du clavier "Français".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_42_04.png)

Appuyer sur "Continuer".

![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_01_15.png)

Sélectionner "Configurer vous-même le réseau"
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_01_28.png)

Saisir une adresse IPv4 correspondant au réseau virtuel auquel la machine est branché.
Dans notre cas l'adresse réseau était 10.0.2.0/24, l'adresse saisie est donc 10.0.2.5/24

![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_02_07.png)

Laisser l'adresse de passerelle saisie automatiquement et cliquer sur "Continuer".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_02_57.png)

Laisser l'adresse des serveurs de nom saisie automatiquement et cliquer sur "Continuer".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_03_02.png)

Saisir le nom de la machine (ici, debInstall) et cliquer sur "Continuer".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_03_17.png)

Saisir le nom du domaine auquel appartient la machine (ici studiLab.local).
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_03_47.png)

Choisir un mot de passe pour le compte super administrateur "root".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_04_27.png)

Saisir le nom de l'utilisateur de la machine.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_04_35.png)

Saisir l'identifiant associé à l'utilisateur.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_04_39.png)

Saisir le mot de passe associé au compte de l'utilisateur.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_46_48.png)

Choisir la méthode de partitionnement utilisant "un disque entier".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_48_00.png)

Choisir le seul disque présent pour le partitionnement.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_48_05.png)

Choisir le schéma recommandé "Tout dans un seul disque".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_48_10.png)

Choisir "Terminer le partitionnement et appliquer les changements".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_48_17.png)

Confirmer l'application des changements sur les disques en sélectionnants "Oui".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_48_21.png)

Indiquer "Non", il n'y a pas d'autre supports d'installation à analyser.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_50_04.png)

Choisir le miroir pour l'installation des paquets de Debian.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_06_59.png)

Si vous avez un Proxy en place, il faut inscrire ses paramètres ici.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_07_03.png)

Choisir si vous souhaitez participer à l'étude statistique sur l'utilisation des paquets.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_50_35.png)

Garder la sélection de logiciels automatique et cliquer sur "Continuer".
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_09_18.png)

Choisir "Oui" à l'installation du programme de démarrage GRUB sur le disque principale.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_50_35.png)

Sélectionner le seul périphérique disponible, pour l'installation de GRUB
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_51_37.png)

Cliquer sur "Continuer" pour terminer l'installation et redémarrer la machine
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebInstall_12_01_2025_08_52_32.png)

Une fois le redémarrage fini, cliquer sur l'identifiant du compte créé.
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_20_07.png)

Saisir le mot de passe associé, choisi précedemment
![img](https://github.com/Mellsx/portfolio/blob/main/src/vmInstall/VirtualBox_DebINstallGraph_12_01_2025_09_20_19.png)






