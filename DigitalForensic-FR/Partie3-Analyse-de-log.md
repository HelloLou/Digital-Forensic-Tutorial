# 📜 **3️⃣ ANALYSE DES LOGS**
Objectif : Identifier des connexions suspectes, traces d'attaques.

---

## **💻 SUR LINUX**
### **📌 Outils à installer :**
```bash
sudo apt install plaso
```

### **📂 EXEMPLE : Repérer une connexion SSH suspecte**
📌 **Situation** : Quelqu’un s’est connecté en SSH.

#### **1️⃣ Lister les tentatives de connexion**
```bash
cat /var/log/auth.log | grep "sshd"
```
👉 Affiche les connexions SSH réussies et échouées.

#### **2️⃣ Identifier les échecs de connexion**
```bash
grep "Failed password" /var/log/auth.log
```
👉 Affiche les tentatives de brute force.

---

## **🖥️ SUR WINDOWS**
### **📌 Outils à installer :**
- **Event Viewer** (intégré à Windows)

### **📂 EXEMPLE : Trouver une connexion RDP suspecte**
📌 **Situation** : Quelqu’un s’est connecté via RDP.

#### **1️⃣ Ouvrir Event Viewer et rechercher**
```
Applications and Services Logs → Microsoft → Windows → TerminalServices-RemoteConnectionManager
```
Chercher :
- **Event ID 4624** : Authentification réussie.
- **Event ID 4625** : Échec de connexion.
