📘 Logbook Vagrant
🧠 Introduction

Vagrant est un outil d'automatisation de la création et de la gestion de machines virtuelles (VM). Il permet aux développeurs de configurer des environnements reproductibles de manière simple, à partir d’un seul fichier : Vagrantfile.

    💡 Sur Windows, il est recommandé d'utiliser Git Bash pour exécuter les commandes Vagrant. Cela permet une meilleure compatibilité avec les commandes UNIX utilisées par Vagrant.

⚙️ Fonctionnement global

    Initialisation du projet :

        Créer un nouveau dossier pour ton projet.

        Exécuter vagrant init pour générer le fichier Vagrantfile.

    Provisioning :

        Le Vagrantfile contient la configuration de la VM (système, mémoire, réseau, etc.).

        Vagrant télécharge automatiquement une image de VM ("box") depuis un catalogue en ligne.

    👉 Les images sont disponibles ici :
    https://portal.cloud.hashicorp.com/vagrant/discover

    Lancement de la VM :

        La commande vagrant up télécharge, installe et démarre la VM.

        On peut ensuite s’y connecter avec vagrant ssh.

    Interaction et gestion :

        Possibilité d’automatiser le provisioning via des scripts shell, ou des outils comme Ansible ou Docker.

    Arrêt et suppression :

        vagrant halt : éteint la VM.

        vagrant destroy : supprime totalement la VM et ses ressources.

📦 Boxes utilisées

Tu as créé deux machines virtuelles à partir des boxes suivantes :

    ✅ Ubuntu Jammy (22.04) :

config.vm.box = "ubuntu/jammy64"

✅ CentOS Stream 9 :

    config.vm.box = "centos/stream9"

🧾 Commandes principales (à exécuter dans Git Bash)
Commande	Description
vagrant init	Initialise un nouveau projet Vagrant (génère le Vagrantfile)
vagrant up	Lance et configure la VM
vagrant ssh	Accès SSH à la VM
vagrant halt	Éteint la VM
vagrant reload	Redémarre la VM avec relecture du Vagrantfile
vagrant destroy	Supprime complètement la VM
vagrant status	Affiche l'état actuel de la VM dans le dossier courant
vagrant global-status	Affiche l'état de toutes les VMs Vagrant sur le système
vagrant provision	Exécute le provisioning défini
vagrant box list	Liste les images de VM téléchargées
vagrant box add	Télécharge une nouvelle image
vagrant box remove	Supprime une image de VM
