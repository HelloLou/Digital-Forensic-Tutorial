## **Introduction**

## 📌 **Qu’est-ce que le Digital Forensic ?**

Le forensic, c’est l’art de **retracer ce qui s’est passé sur un système informatique** après un incident (attaque, fraude, vol de données, etc.). C’est un peu comme une enquête policière numérique.

Ton but en forensic :

1. **Récupérer des preuves** (logs, fichiers supprimés, traces réseau, mémoire vive, etc.).
2. **Analyser ces preuves** pour comprendre ce qui s’est passé.
3. **Rédiger un rapport clair et précis** (très important pour les enquêtes officielles).

---

## 🔥 **Les Bases du Forensic (sans t’endormir 😴)**

On va découper en plusieurs catégories pour aller à l’essentiel.

### 1️⃣ **Analyse de Disque et Récupération de Fichiers**

- **Outils** : `Autopsy`, `Sleuth Kit`, `FTK Imager`, `testdisk`
- **Ce que tu cherches** :
    - Fichiers supprimés (récupération avec Foremost)
    - Métadonnées des fichiers (dates, propriétaire, modifications)
    - Partition suspecte ou cachée

### 2️⃣ **Analyse de la Mémoire Vive (RAM)**

- **Outils** : `Volatility` (le plus utilisé)
- **Ce que tu cherches** :
    - Processus en cours au moment du dump
    - Connexions réseau ouvertes
    - Mots de passe en clair dans la mémoire
    - Fichiers et malwares injectés dans la mémoire

### 3️⃣ **Analyse des Logs et Événements Windows/Linux**

- **Outils** : `Event Viewer` (Windows), `log2timeline`, `Plaso`, `grep`
- **Ce que tu cherches** :
    - Connexions suspectes (`failed login`, `RDP session`, `SSH bruteforce`)
    - Suppression de logs (signe de compromission)
    - Exécution de commandes malveillantes

### 4️⃣ **Analyse Réseau et Fichiers PCAP**

- **Outils** : `Wireshark`, `NetworkMiner`
- **Ce que tu cherches** :
    - Communication avec un serveur externe suspect
    - Téléchargement de malwares
    - Extraction de mots de passe en clair (`HTTP`, `FTP`, `Telnet`)
 
### 5️⃣ **Exemple rapport Digital Forensic**

- **PDF** : `Rapport Digital Forensic`


---

## 🏆 **Comment S’entrainer Rapidement ?**

👉 **TryHackMe** : Room **"Intro to Digital Forensics"**, "Windows Event Logs" 👉 **CyberDefenders.org** : Des **CTF forensic gratuits** très réalistes 👉 **DFIR.training** : Base de données d’outils et ressources forensic
