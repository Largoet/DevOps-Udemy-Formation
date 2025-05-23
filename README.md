Journal de Bord - Formation DevOps (Udemy)

Auteur : Thibaut Prunet Période : Mai 2025Objectif : Noter et structurer toutes les étapes clés de mon apprentissage DevOps afin d'en garder une trace claire..

📅 16-17 Mai 2025

✅ Installation de Chocolatey

Installation de Chocolatey en mode administrateur depuis PowerShell.

🚀 Installation de logiciels via Chocolatey

Commandes exécutées dans PowerShell (admin) :

choco install virtualbox --version=7.1.4 -y
choco install vagrant --version=2.4.3 -y
choco install git -y
choco install corretto17jdk -y
choco install maven -y
choco install awscli -y
choco install intellijidea-community -y
choco install vscode -y
choco install sublimetext3 -y

Tous les outils ont été installés sans erreur apparente.

🔑 Créations de comptes

Docker Hub : Création d'un compte personnel

SonarQube : Préparation de l'analyse statique de code

OVHcloud : Achat d'un nom de domaine : kintocloud.fr

☁️ Premiers pas sur AWS (Free Tier)

Création d'un compte AWS (free tier)

Création d'un utilisateur IAM nommé itadmin

Mise en place des bonnes pratiques :

Activation du MFA (Multi-Factor Authentication) pour le compte root avec Google Authenticator

Sauvegarde des clés root dans Proton Pass

Déconnexion du compte root et connexion via itadmin (avec obligation de changer le mot de passe à la première connexion)

Mise en place d'une alerte de facturation pour éviter les dépassements

Génération d'un certificat SSL/TLS sur AWS

Application de ce certificat au nom de domaine acheté chez OVHcloud

🧠 Remarque personnelle

J'ai fait pas mal de manipulations sur AWS, et certaines sont encore un peu floues. Il faudra que je revoie calmement les étapes IAM, la gestion des certificats et la liaison avec un domaine externe  pour clarifier tout ça.

📅 20-22 Mai 2025

🧰 Virtualisation – Premiers pas avec les machines virtuelles

✅ Étude des hyperviseurs
Compréhension des différences entre :

    Hyperviseur de type 1 (bare-metal) : s’exécute directement sur le matériel.

    Hyperviseur de type 2 (hosted) : s’exécute sur un système d’exploitation existant (ex. : VirtualBox).

✅ Installation et prise en main d’Oracle VirtualBox

    Installation de VirtualBox via Chocolatey.

    Lancement de l’interface, création de deux VMs :

        CentOS

        Ubuntu

    Paramétrages :

        Définition du nombre de cœurs CPU et de la mémoire vive.

        Définition du disque dur virtuel.

💿 Installation de CentOS

    Téléchargement de l’image ISO officielle.

    Lancement de l’installation manuelle :

        Définition du mot de passe root.

        Sélection du disque pour l’installation.

        Configuration de base (langue, fuseau horaire, etc.).

🌐 Configuration réseau – Mode Bridge

    Découverte du mode "Bridged Adapter" dans l’onglet Network > Adapter 2.

    Sélection de l’adaptateur réseau correspondant à ma connexion.

    Objectif : donner à la VM une adresse IP locale propre, visible sur le réseau.

🔎 Vérification IP

    Utilisation de la commande ip a dans la VM (équivalent de ipconfig sous Windows) pour confirmer la connectivité réseau.
📅 20 Mai 2025

🔍 Analyse réseau – VM CentOS

✅ Commande exécutée :

ip addr show

📄 Résultat analysé :
Interface enp0s3 (interface NAT par défaut VirtualBox)

    Adresse MAC : 08:00:27:38:1c:cb

    Adresse IPv4 : 10.0.2.15/24

        Fournie par VirtualBox pour simuler un accès Internet.

        Plage : 10.0.2.0/24 (passerelle probable : 10.0.2.1)

    Adresses IPv6 :

        Globale dynamique : 2400:...:38:1ccb/64

        Link-local : fe80::...:38:1ccb/64

Interface enp0s8 (interface configurée en mode Bridged Adapter)

    Adresse MAC : 08:00:27:79:c9:68

    Adresse IPv4 : 192.168.1.185/24

        IP obtenue directement depuis ma box Internet (réseau local).

        Confirme que le mode bridge est fonctionnel.

    Adresses IPv6 :

        Globale : 2001:861:3a03:b0a0::27ff:fe79:c968/64

        Link-local : fe80::27ff:fe79:c968/64


🔐 Connexion SSH – Validation de l’environnement CentOS

✅ Connexion réussie à la VM CentOS via Git Bash :

ssh centosuser@192.168.1.185

💡 Authentification :

    Connexion établie en saisissant le mot de passe de l’utilisateur centosuser.

🔎 Vérification du nom d’hôte :

hostname

    Résultat : centosvm


🎉 Conclusion :

    La connexion distante fonctionne parfaitement.

    L’utilisateur centosuser est actif et autorisé à se connecter via SSH.

    La machine répond bien aux commandes de base depuis un terminal distant.

➡️ Étape suivante : Réaliser la même procédure avec la VM Ubuntu.
