# 🌐 **4️⃣ ANALYSE RÉSEAU (PCAP FILES)**
Objectif : Trouver des communications malveillantes, extraire des mots de passe.

---

## **💻 SUR LINUX**
### **📌 Outils à installer :**
```bash
sudo apt install wireshark tshark
```

### **📂 EXEMPLE : Trouver des credentials en clair**
📌 **Situation** : Un utilisateur s’est connecté à un site.

#### **1️⃣ Ouvrir Wireshark et filtrer le trafic HTTP**
```
http.request.method == "POST"
```
👉 Recherche une requête de login contenant un mot de passe en clair.

---

## **🖥️ SUR WINDOWS**
### **📌 Outils à installer :**
- **Wireshark** ([Téléchargement](https://www.wireshark.org/))

### **📂 EXEMPLE : Analyser un PCAP**
📌 **Situation** : On a capturé du trafic suspect.

1. **Ouvrir Wireshark et charger le fichier PCAP**
2. **Appliquer un filtre "http"**
3. **Chercher des identifiants dans les requêtes POST**
