🌐 Fiche mémoire – VLAN
🔑 LAN vs VLAN

LAN (Local Area Network) : réseau local géographiquement limité (maison, école, entreprise).

Toutes les machines communiquent dans le même domaine de diffusion (broadcast domain).

VLAN (Virtual LAN) : segmentation logique d’un même LAN en plusieurs sous-réseaux virtuels.

Exemple :

VLAN 10 → chercheurs

VLAN 20 → commerciaux

Chaque VLAN = son propre broadcast domain.

🧩 Pourquoi utiliser des VLAN ?

Performance → réduit les diffusions inutiles (broadcast).

Sécurité → isole les groupes (comme des compartiments d’informations).

Flexibilité → un même switch peut héberger plusieurs réseaux logiques.

Économie → pas besoin d’acheter un switch physique pour chaque département.

⚙️ Mise en place

Switch (commutateur) → permet de connecter plusieurs machines.

Ports d’accès (Access Ports) → assignés à un VLAN précis.

Exemple : port 1–10 = VLAN 10, port 11–20 = VLAN 20.

🔗 Trunk Link

Un lien trunk est une connexion entre switches ou switch ↔ routeur.

Objectif : transporter plusieurs VLAN sur une seule liaison physique.

Fonctionnement : chaque trame Ethernet est taguée avec un VLAN ID (802.1Q tag).

Ainsi, le switch récepteur sait à quel VLAN appartient la trame.

👉 Sans trunk, les VLAN resteraient confinés à un seul switch.

🌍 Inter-VLAN Routing

Problème : les VLAN sont isolés → impossible pour VLAN 10 de communiquer avec VLAN 20.

Solution : routage inter-VLAN, réalisé par :

un routeur (couche 3 OSI), ou

un switch de niveau 3 (Layer 3 Switch).

📌 Exemple visuel
