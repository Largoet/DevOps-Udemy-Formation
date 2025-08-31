# 🌐 Fiche mémoire – Modèles OSI & TCP/IP

## 🔑 Modèle OSI (7 couches)

| N° | Couche OSI         | Rôle principal | Protocoles / Exemples |
|----|--------------------|---------------|------------------------|
| 7  | **Application** ✅ | Interface utilisateur | HTTP, SMTP (mail), FTP, DNS |
| 6  | Présentation       | Mise en forme, chiffrement, compression | SSL/TLS, ASCII, JPEG |
| 5  | Session            | Organisation des échanges | NetBIOS, RPC |
| 4  | **Transport** ✅   | Fiabilité de transmission | TCP (fiable), UDP (rapide) |
| 3  | **Réseau** ✅      | Acheminement des paquets | IP, ICMP |
| 2  | **Liaison** ✅     | Communication locale, adresses MAC | Ethernet, PPP, ARP |
| 1  | **Physique** ✅    | Transmission brute | Câbles, Wi-Fi, fibre |

👉 **À retenir par cœur** : ordre des 7 couches + 1 exemple de protocole par couche.

---

## 🔑 Modèle TCP/IP (4 couches)

| Couche TCP/IP          | Rôle | Protocoles / Exemples |
|-------------------------|------|------------------------|
| **Application** ✅      | Services aux utilisateurs | HTTP, DNS, DHCP, SMTP, SSH |
| **Transport** ✅        | Segmentation et fiabilité | TCP, UDP |
| **Internet** ✅         | Adressage et routage | IP, ICMP |
| **Accès Réseau** ✅     | Transmission locale | Ethernet, Wi-Fi, MAC |

👉 TCP/IP simplifie OSI : il regroupe ses 7 couches en 4.

---

## ⚙️ Encapsulation / Décapsulation

- **Encapsulation** : chaque couche ajoute un en-tête au paquet.  
- **Décapsulation** : chaque couche lit puis enlève son en-tête.  

**PDU (Protocol Data Unit) :**
- Application → **Message**  
- Transport → **Segment** (TCP) / Datagram (UDP)  
- Internet → **Paquet**  
- Liaison → **Trame**  
- Physique → **Bits**

✅ **À retenir** : *Message → Segment → Paquet → Trame → Bits*

---

## 📌 Rôle des équipements

- **Switch (couche 2)** ✅ : utilise les **adresses MAC**, relie les machines d’un LAN.  
- **Routeur (couche 3)** ✅ : utilise les **adresses IP**, relie plusieurs réseaux (LAN ↔ Internet).

---

## 🧠 Moyens mnémotechniques

- **En anglais (7 → 1)** : *All People Seem To Need Data Processing*  
- **En français (7 → 1)** : *Avec Préférence, Ses Travaux Restent Dans la Poche*  
