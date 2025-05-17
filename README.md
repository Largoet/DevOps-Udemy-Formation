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
