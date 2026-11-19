# 🔐 Password Cracking Labs — john the Ripper((Jtr)& NetworkWalks Tools

> Week 3 | Project Modules 1 & 2
> Source: [Networkwalks Academy](https://www.networkwalks.com)

Ce dépôt contient deux labos pratiques sur le craquage de mots de passe appliqué à un fichier PDF protégé (`My Locked PDF1.pdf`), réalisés dans le cadre du cours Cybersecurity & Ethical Hacking.

L'objectif pédagogique est de comprendre :
- La différence entre **chiffrement** (réversible) et **hachage** (fonction à sens unique).
- Comment un hash est extrait d'un fichier protégé.
- Comment une attaque par dictionnaire retrouve un mot de passe à partir de son hash.
- Pourquoi un mot de passe faible est vulnérable.

---


---

## 🧩 Module 1 — Password Cracking with John the Ripper (JTR)

**Outils :** John the Ripper (JTR) + Johnny (interface graphique)

### Étapes résumées

| Étape | Action |
|---|---|
| 1 | Installer John the Ripper (Windows) ou utiliser la version pré-installée sous Kali Linux |
| 2 | Installer Johnny (GUI) — facultatif sous Kali |
| 3 | Extraire le hash du PDF : <br>• **Windows** → via [onlinehashcrack.com](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)
| 5 | Charger le hash dans Johnny ou lancer `john hash1.txt` |
| 6 | Démarrer l'attaque et attendre le résultat |
| 7 | Afficher le mot de passe trouvé : `john --show hash1.txt` |
| 8 | Ouvrir le PDF avec le mot de passe récupéré |

### ⚠️ Erreur fréquente
Ne **jamais** ouvrir directement le fichier `.pdf` dans Johnny — il faut d'abord extraire le hash avec `pdf2john.py` (ou l'outil web) et charger uniquement le fichier `hash1.txt` contenant le hash au format `$pdf$...`.


## 🧩 Module 2 — Password Cracking with Networkwalks Tools

**Outils :** [Hash Calculator](https://networkwalks.com/hash-calculator/) et [Password Cracker](https://networkwalks.com/password-cracker/) — 100 % en ligne, aucune installation requise.

### Étapes résumées

| Étape | Action |
|---|---|
| 1 | Télécharger `My Locked PDF1.pdf` |
| 2 | Ouvrir le **Hash Calculator**, onglet "PDF" |
| 3 | Téléverser le PDF → le hash `$pdf$...` est généré localement (calcul côté navigateur, aucun fichier envoyé sur un serveur) |
| 4 | Copier le hash complet |
| 5 | Ouvrir le **Password Cracker** |
| 6 | Coller le hash dans le champ prévu |
| 7 | Lancer l'attaque avec la liste intégrée (100 mots de passe) |
| 8 | Récupérer le mot de passe affiché |
| 9 | Ouvrir le PDF avec ce mot de passe |

**Résultat attendu :** `password1`

### Avantage
Fonctionne de façon identique sous Windows, Kali Linux ou macOS, puisque tout se déroule dans le navigateur.

---

## 📊 Comparatif des deux méthodes

| Critère | JTR / Johnny | Networkwalks Tools |
|---|---|---|
| Installation requise | Oui (Windows) / Non (Kali) | Non |
| Interface | CLI ou GUI (Johnny) | Web |
| Extraction du hash | `pdf2john.py` ou site externe | Hash Calculator (local, navigateur) |
| Liste de mots de passe | `rockyou.txt` ou personnalisée | Liste intégrée (100 mots) ou upload `.txt` |
| Usage pro / terrain | ✅ Outil standard de l'industrie | 🎓 Outil pédagogique |

---

## 🔑 Notions clés

- **Hash** : empreinte unique et non réversible générée à partir d'un mot de passe. On ne "déchiffre" pas un hash, on teste des candidats jusqu'à obtenir le même hash.
- **Attaque par dictionnaire** : teste une liste de mots de passe probables (ex: `rockyou.txt`, liste intégrée).
- **Attaque brute-force / incremental** : teste toutes les combinaisons possibles — plus lent, mais exhaustif.
- **Pourquoi c'est important** : un mot de passe court ou commun (`password1`, `123456`) peut être cassé en quelques secondes à minutes, ce qui justifie l'usage de mots de passe longs, complexes et uniques.

---

## 📚 Références

- [John the Ripper — site officiel](https://www.openwall.com/john/)
- [Johnny GUI](https://openwall.info/wiki/john/johnny)
- [Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/)
- [Networkwalks Password Cracker](https://networkwalks.com/password-cracker/)
- [Networkwalks Academy](https://www.networkwalks.com)

---

## ⚖️ Disclaimer

Ce travail est réalisé dans un cadre **strictement pédagogique et éthique** (Ethical Hacking / CEH training), sur un fichier PDF fourni volontairement pour l'exercice. Le craquage de mots de passe sur des systèmes ou fichiers appartenant à des tiers sans autorisation explicite est illégal.

---

*Formation : Cybersecurity & Ethical Hacking — Networkwalks Academy*
*Contact : info@networkwalks.com*
