# 🛠 **1️⃣ ANALYSE DE DISQUE (FILESYSTEM FORENSIC)**
Objectif : Trouver des fichiers supprimés, explorer les partitions, extraire des preuves.

---

## **💻 SUR LINUX**
### **📌 Outils à installer :**
```bash
sudo apt update && sudo apt install autopsy sleuthkit testdisk foremost
```

### **📂 EXEMPLE 1 : Explorer un disque suspect**
📌 **Situation** : On analyse une clé USB `/dev/sdb` suspecte.

#### **1️⃣ Lister les partitions du disque**
```bash
sudo fdisk -l /dev/sdb
```
👉 Affiche les partitions du disque.

#### **2️⃣ Monter la partition en lecture seule**
```bash
sudo mount -o ro /dev/sdb1 /mnt/usb
```
👉 On monte la clé USB en lecture seule pour ne pas altérer les preuves.

#### **3️⃣ Explorer les fichiers du disque**
```bash
ls -al /mnt/usb
```
👉 Affiche les fichiers cachés.

#### **4️⃣ Identifier le type de fichier suspect**
```bash
file /mnt/usb/mystery.file
```
👉 Permet de savoir s’il s’agit d’un fichier exécutable, un document, etc.

#### **5️⃣ Vérifier les métadonnées d’un fichier**
```bash
stat /mnt/usb/document.pdf
```
👉 Montre les dates de création, modification, accès.

---

### **📂 EXEMPLE 2 : Récupérer des fichiers supprimés**
📌 **Situation** : Un fichier a été supprimé du disque `/dev/sdb1`.

#### **1️⃣ Scanner et récupérer les fichiers supprimés avec foremost**
```bash
sudo foremost -i /dev/sdb1 -o /mnt/recovery/
```
👉 Foremost analyse la partition et récupère les fichiers supprimés dans `/mnt/recovery/`.

---

## **🖥️ SUR WINDOWS**
### **📌 Outils à installer :**
- **Autopsy** ([Téléchargement](https://www.autopsy.com/))
- **FTK Imager** ([Téléchargement](https://accessdata.com/product-download))
- **TestDisk** ([Téléchargement](https://www.cgsecurity.org/wiki/TestDisk_Download))

### **📂 EXEMPLE 1 : Explorer un disque suspect**
📌 **Situation** : Un disque USB suspect est branché.

#### **1️⃣ Ouvrir FTK Imager et analyser un disque**
1. **Lancer FTK Imager**
2. **Cliquer sur "File" → "Add Evidence Item" → "Physical Drive"**
3. Sélectionner le disque suspect (`E:\` par exemple)
4. Explorer les fichiers et les exporter pour analyse.

#### **2️⃣ Lister les fichiers supprimés avec Autopsy**
1. **Ouvrir Autopsy**
2. **Créer un nouveau cas** (`Create New Case`)
3. **Ajouter une image disque ou un disque physique**
4. **Lancer une analyse et regarder les "Deleted Files"**
