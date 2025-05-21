## Télécharger l'iso de PfSense

Aller sur le site https://www.pfsense.org/

Aller dans l'onglet Download

Dans la section "Latest Stable Version", cliquer sur Download, vous serez redirigé vers le shop Netgate, sur l'article Netgate installer.

Dans la liste "Installation Image", sélectionnez "AMD64 ISO IPM/Virtual Machine", Puis cliquez sur "Add to cart".

Dans la popup qui s'est ouverte en bas de l'écran, cliquer suz "Enter cart", puis sur "Checkout".

Remplissez vos coordonées et validez.

## Installation de PfSense

Lors de la création de la VM, choisissez le type BSD et la version FreeBSD (64-bit).

Une fois la VM créée, aller dans ses paramètres de configuration. Choisissez l'onglet réseau. Activer la première interface réseau en accès par pont. Activez la deuxième interface réseau en réseau interne. Validez les changements, puis lancez la VM.

Sur la page des copyright, cliquer sur "Accept".

Ensuite, sélectionner "Install   Install pfSense" et cliquer sur "OK".

Pour séléctionner l'interface WAN, sélectionner celle que vous avez connecté en accès par pont (ici la première option). 

Ensuite sélectioner "Continue"  pour passer le setup.

Pour séléctionner l'interface LAN, sélectionner celle que vous avez connecté en réseau interne (ici la seconde option). Cliquer sur "Continue" pour passer le setup.

Confirmer l'assignation des interface en cliquant sur "Continue"

Pour lancer l'installation, cliquez sur "Install CE"

Vérifier que le système de fichier est en ZFS et le schéma de partitionnement en GPT, puis valider en cliquant sur "OK".

Cliquer sur OK pour confirmer le parametrage de redondance RAID et le disque d'installation.

Puis confirmez la destruction des données du disque d'installation en clquant sur "Yes"

Choisissez ensuite la version a installer (ici, la 2.7.2)

Rebooter le système et penser à débrancher le disque iso de votre vm

Pour modifier l'adresse IP du réseau interne, Choisissez l'option 2.

Choisissez ensuite le numéro de l'interface correspondant au LAN (ici 2)

A la proposition de configurer l'adresse IPv4 du LAN par DHCP, répondez "n" pour non.

Saisissez l'adresse IPv4 du VLAN, ici 192.170.1.1

Choississez ensuite le masque de sous-réseau, ici 24 pour 255.255.255.0

Ne pas saisir de passerelle

Choisissez non pour l'IPv6 par DHCP, et ne saisissez pas d'adresse

Refuser l'activation du DHCP pour le LAN

Choisissez n à la dernière question sur le HTTP

Maintenant, connecter une machine client sur votre réseau interne pour configurer le pare feu avec l'interface graphique.
Aller dans le navigateur et saisissez l'IP du parefeu (ici 192.170.1.1) pour vous connecter à l'interface graphique du pare-feu.

