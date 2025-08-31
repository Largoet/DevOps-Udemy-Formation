# 🔌 Fiche mémoire – Ports & Protocoles

## 🔑 Rappel
- **Port** = numéro logique qui identifie une application ou un service sur une machine.  
- **Socket** = combinaison **IP + Port** (ex : 192.168.1.10:80).  
- Les ports permettent de savoir **vers quel service router l’information**.  

---

## 📊 Plages de ports
- **0 – 1023** : *Ports bien connus* (reserved / system) – utilisés par les services systèmes.  
- **1024 – 49151** : *Ports enregistrés* – attribués à des applications spécifiques (IANA).  
- **49152 – 65535** : *Ports dynamiques/éphémères* – attribués temporairement par le système lors des connexions.  

---

## 🌐 Ports & Protocoles à connaître par cœur ✅

| Port | Protocole | Usage |
|------|-----------|-------|
| **20/21** | FTP | Transfert de fichiers |
| **22** | SSH | Connexion sécurisée à distance |
| **25** | SMTP | Envoi de mails |
| **53** | DNS | Résolution de noms de domaine |
| **67/68** | DHCP | Attribution automatique d’IP et configuration réseau |
| **80** | HTTP | Web non sécurisé |
| **110** | POP3 | Récupération de mails |
| **143** | IMAP | Récupération de mails (plus moderne que POP3) |
| **443** | HTTPS | Web sécurisé (TLS/SSL) |

👉 Ceux-ci tombent **tout le temps** en examen ou entretien.  

---

## 🧩 Modèle OSI / TCP-IP
- Les **ports** sont utilisés par la **couche 4 (Transport)** du modèle OSI (TCP/UDP).  
- Exemple :  
  - Transport (TCP/UDP) = choisit le **port**.  
  - Réseau (IP) = choisit l’**adresse**.  
  - Ensemble IP + Port = **Socket**.  

---

## ⚡ Exemple concret
- Quand tu tapes **http://site.com** → ton navigateur se connecte à l’IP du serveur sur le **port 80** (HTTP).  
- Si c’est **https://site.com** → connexion sur le **port 443** (HTTPS).  
- En arrière-plan, ton système ouvre un **port éphémère** (dans la plage 49152–65535) pour établir la session.
