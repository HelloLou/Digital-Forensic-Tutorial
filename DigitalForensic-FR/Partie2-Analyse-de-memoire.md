# 🧠 **2️⃣ ANALYSE DE MÉMOIRE (RAM FORENSIC)**
Objectif : Retrouver des processus actifs, mots de passe en mémoire, fichiers injectés.

---

## **💻 SUR LINUX**
### **📌 Outils à installer :**
```bash
sudo apt install volatility
```

### **📂 EXEMPLE : Analyser une image mémoire dumpée**
📌 **Situation** : On a fait un dump de la RAM (`memory.raw`).

#### **1️⃣ Identifier le profil du système**
```bash
volatility -f memory.raw imageinfo
```
👉 Permet de savoir quel OS était utilisé.

#### **2️⃣ Lister les processus actifs**
```bash
volatility -f memory.raw --profile=LinuxUbuntu pslist
```
👉 Affiche tous les processus actifs au moment du dump.

#### **3️⃣ Retrouver des mots de passe en mémoire**
```bash
volatility -f memory.raw --profile=LinuxUbuntu strings | grep "password"
```
👉 Recherche des mots de passe en clair.

---

## **🖥️ SUR WINDOWS**
### **📌 Outils à installer :**
- **DumpIt** ([Téléchargement](https://download.magnetforensics.com))
- **Volatility** ([Téléchargement](https://github.com/volatilityfoundation/volatility))

### **📂 EXEMPLE : Analyser une image mémoire dumpée**
📌 **Situation** : On suspecte un malware en RAM.

#### **1️⃣ Faire un dump de la mémoire**
```powershell
DumpIt.exe
```
👉 Produit un fichier `memory.dmp`.

#### **2️⃣ Identifier les processus suspects**
```bash
volatility -f memory.dmp --profile=Win7SP1x64 pslist
```
👉 Affiche les processus actifs.

#### **3️⃣ Extraire un fichier en mémoire**
```bash
volatility -f memory.dmp --profile=Win7SP1x64 filescan | grep ".exe"
```
👉 Cherche un exécutable malveillant.
