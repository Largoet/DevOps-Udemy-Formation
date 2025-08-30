# 📘 Logbook Linux — Guide unifié CentOS/RHEL & Ubuntu/Debian

## 🧠 Introduction

Ce logbook regroupe les commandes Linux essentielles rencontrées lors des exercices (fichiers 1 → 13). Il couvre à la fois **CentOS/RHEL** et **Ubuntu/Debian**, avec les différences importantes. Il est structuré par thématique pour servir de référence rapide.

---

## 🔹 Navigation & gestion des fichiers

```bash
pwd              # afficher le chemin courant
ls               # lister les fichiers
ls -l            # affichage détaillé
ls -a            # inclut fichiers cachés
cd <répertoire>  # changer de dossier
touch fichier.txt # créer un fichier vide
mkdir dossier    # créer un répertoire
mkdir -p chemin/vers/dossier  # créer un arbre complet
rm fichier       # supprimer un fichier
rm -r dossier    # supprimer un dossier
cp source dest   # copier un fichier
cp -r dossier1 dossier2  # copie récursive
mv source dest   # déplacer/renommer
cat fichier      # afficher contenu
head -n 10 fichier   # afficher les 10 premières lignes
tail -n 10 fichier   # afficher les 10 dernières lignes
tail -f fichier      # suivre un fichier en temps réel
wc -l fichier        # compter lignes
find /etc -name host*   # rechercher un fichier
locate motclef         # recherche via index (mlocate)
```

---

## 🔹 Informations système

```bash
whoami        # utilisateur courant
id user       # infos UID, GID, groupes
uptime        # durée depuis le dernier boot
free -m       # mémoire disponible
df -h         # espace disque
uname -a      # infos kernel
cat /etc/os-release   # infos OS
ps aux        # processus en cours (BSD style)
ps -ef        # processus (System V style)
top           # suivi dynamique
htop          # version améliorée si installée
```

---

## 🔹 Utilisateurs & groupes

### CentOS/RHEL

```bash
useradd nom          # créer un utilisateur
passwd nom           # définir mot de passe
usermod -aG groupe user  # ajouter au groupe
groupadd groupe      # créer un groupe
groupdel groupe      # supprimer un groupe
userdel user         # supprimer un user
userdel -r user      # supprimer un user + home
```

### Ubuntu/Debian

```bash
adduser nom          # recommandé (home + shell + mdp)
deluser nom          # supprimer un user
deluser --remove-home nom   # suppression complète
# Alternative bas niveau :
useradd -m -s /bin/bash nom
```

---

## 🔹 Permissions & droits

```bash
ls -ld fichier          # voir les droits
chmod 754 fichier       # modifier droits numériques
chmod +x script.sh      # ajouter exécution
chown user:group fichier # changer propriétaire

chmod g+w dossier       # ajouter écriture au groupe
chmod o-r dossier       # retirer lecture aux autres
```

---

## 🔹 Super utilisateur (sudo)

```bash
sudo commande       # exécuter en admin
visudo              # éditer sudoers
```

> ⚠️ Alternative sûre : créer un fichier dans `/etc/sudoers.d/`

```bash
# Définir vim comme éditeur par défaut
export EDITOR=vim
export VISUAL=vim
```

(à mettre dans `~/.bashrc` pour être permanent)

---

## 🔹 Gestion des paquets

### CentOS/RHEL (yum/dnf)

```bash
dnf install paquet
dnf remove paquet
dnf update -y       # maj des paquets installés
dnf upgrade         # maj plus complète
dnf search motclef  # rechercher un paquet
dnf list installed  # liste paquets installés
dnf history         # voir historique
dnf history undo <id>   # annuler transaction
dnf history redo <id>   # rejouer transaction

# RPM
yum install paquet.rpm
rpm -ivh fichier.rpm   # installer un rpm
rpm -qa                # liste paquets
rpm -e paquet          # suppression
```

### Ubuntu/Debian (apt/dpkg)

```bash
apt update             # met à jour l’index des dépôts
apt upgrade            # installe nouvelles versions
apt install paquet
apt remove paquet      # supprime mais garde la conf
apt purge paquet       # supprime paquet + conf
apt autoremove         # supprime dépendances inutiles
apt search motclef     # recherche paquet

# dpkg
dpkg -i paquet.deb     # installer
dpkg -l                # lister
dpkg -r paquet         # supprimer
```

---

## 🔹 Services (systemd)

```bash
systemctl start service
systemctl stop service
systemctl restart service
systemctl reload service
systemctl status service
systemctl enable service
systemctl disable service
systemctl is-active service
systemctl is-enabled service
journalctl -u service [-f]
```

**Noms différents :**

* Apache : `httpd` (CentOS) / `apache2` (Ubuntu)
* SSH : `sshd` (CentOS) / `ssh` (Ubuntu)

---

## 🔹 Processus

```bash
ps aux | grep nom        # chercher un processus
kill <PID>               # terminer (TERM)
kill -9 <PID>            # tuer de force (KILL)
pkill nom_processus      # tuer par nom

# Exemple : tuer tous les httpd
ps -ef | grep httpd | awk '{print $2}' | xargs kill -9
```

---

## 🔹 Archivage & compression

### tar

```bash
tar -cvf archive.tar fichiers/
tar -xvf archive.tar
tar -tzvf archive.tar.gz     # lister contenu gzip
tar -czvf archive.tar.gz dossier/   # créer gzip
tar -xjvf archive.tar.bz2    # extraire bzip2
tar -xJvf archive.tar.xz     # extraire xz
```

### zip/unzip

```bash
zip archive.zip fichier1 fichier2
zip -r archive.zip dossier/
unzip archive.zip
unzip -l archive.zip         # lister contenu
```

---

## 🔹 Réseau

```bash
ip addr show       # interfaces réseau
ping adresse       # tester connectivité
traceroute hote    # tracer la route
ssh user@ip        # connexion distante
curl url           # requête http(s)
wget url           # téléchargement
```

---

## 🔹 Logs & monitoring

### CentOS/RHEL

```bash
/var/log/messages
/var/log/secure
```

### Ubuntu/Debian

```bash
/var/log/syslog
/var/log/auth.log
```

### Commandes utiles

```bash
tail -f /var/log/messages | grep vagrant
last    # connexions récentes
who     # utilisateurs connectés
lsof -u user   # fichiers ouverts par un user
```

---

## 🔹 Différences clés CentOS vs Ubuntu

* **Famille** : Red Hat (CentOS/RHEL) vs Debian (Ubuntu)
* **Gestion paquets** : `dnf/yum` vs `apt/dpkg`
* **Apache** : `httpd` vs `apache2`
* **SSH** : `sshd` vs `ssh`
* **Logs système** : `/var/log/messages` vs `/var/log/syslog`
* **Users** : `useradd` vs `adduser`
* **Éditeur par défaut** : `vim` (CentOS) vs `nano` (Ubuntu)

> 💡 Même noyau Linux, mais philosophies différentes : CentOS vise la **stabilité long terme**, Ubuntu est plus **à jour et répandu côté cloud et postes de travail**.
