## 🔑 DNS (Domain Name System)

### Rôle
- Quand on veut accéder à Internet, on tape un **nom de domaine**.  
- L’ordinateur a besoin d’une **adresse IP** pour contacter le bon serveur.  
- Le **DNS** est le système qui traduit les noms de domaine en adresses IP.  

👉 Sans DNS, il faudrait mémoriser toutes les adresses IP des sites.  

---

### Hiérarchie DNS
Exemple : `fr.wikipedia.org`

- `.` : domaine racine  
- `.org` : domaine de premier niveau (TLD – Top Level Domain)  
- `wikipedia` : domaine de second niveau  
- `fr` : sous-domaine  

---

### Fonctionnement
1. **Le navigateur** veut accéder à `fr.wikipedia.org`.  
2. Il interroge un **serveur DNS récursif** (souvent fourni par le FAI).  
   - On peut aussi utiliser des DNS publics (ex : Google DNS, Cloudflare).  
3. Si le serveur récursif n’a pas la réponse, il interroge :  
   - le **serveur racine** → indique quels serveurs gèrent `.org`.  
   - le **serveur DNS du TLD `.org`** → indique quels serveurs gèrent `wikipedia.org`.  
   - le **serveur DNS de `wikipedia.org`** → fournit l’adresse IP exacte.  
4. L’adresse IP est renvoyée au navigateur, qui peut alors contacter le serveur.  

---

### Exemple simplifié du processus
- Tu tapes `fr.wikipedia.org`.  
- Le serveur récursif demande aux **racines** → “qui gère .org ?”  
- Le serveur `.org` répond → “voici les serveurs pour wikipedia.org”  
- Le serveur `wikipedia.org` fournit → “l’IP est 91.198.174.192”  
- Le navigateur peut alors se connecter directement à l’IP.  

---

## 📌 À connaître par cœur (DNS)
- Port **53** (UDP/TCP).  
- Rôle : traduction nom ↔ IP.  
- Structure hiérarchique : Racine → TLD (.fr, .org…) → Domaine de second niveau → Sous-domaine.  
- Types de serveurs : **récursif** (FAI, Google DNS…) et **auteuritatif** (donne la vraie IP).  
