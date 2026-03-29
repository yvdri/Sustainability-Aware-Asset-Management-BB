# Guide GitHub — Travail en groupe 🚀
## Projet : Sustainability-Aware Asset Management | Groupe BB

---

## ⚡ RÉSUMÉ RAPIDE (à garder sous la main)

```
# 1ère fois — Début de session (cloner + créer sa branche)
git checkout main
git pull origin main
git checkout -b prenom/ma-tache

# Toutes les fois suivantes — Début de session (récupérer le main sur sa branche)
git checkout main       # ⚠️ Vérifier que le main fonctionne avant de continuer !
git checkout prenom/ma-tache
git pull origin main

# Pendant le travail
git branch              # Vérifier sur quelle branche on est

# Fin de session — Envoyer son travail
git status              # Voir les fichiers modifiés
git add .               # Préparer tous les fichiers
git commit -m "message" # Sauvegarder avec un message
git push origin prenom/ma-tache   # Envoyer sa branche sur GitHub
# ➡️ Puis créer une Pull Request sur GitHub (voir section dédiée ci-dessous) !

# Après le merge
git checkout main
git pull origin main
```

---

## 📋 GUIDE COMPLET ÉTAPE PAR ÉTAPE

### 1. Cloner le repo (une seule fois, au tout début)

```bash
git clone https://github.com/yvdri/Sustainability-Aware-Asset-Management-BB.git
cd Sustainability-Aware-Asset-Management-BB
```

---

### 2. 🟢 DÉBUT DE SESSION

#### → 1ère fois sur ce projet (créer sa branche)

```bash
git checkout main
git pull origin main                    # Récupérer la dernière version du main
git checkout -b prenom/ma-tache         # Créer et aller sur ta branche personnelle
```

> **Exemples de noms de branche :** `alice/analyse-donnees`, `bob/visualisation`, `claire/rapport-final`

#### → Toutes les sessions suivantes (mettre à jour sa branche)

```bash
git checkout main                       # ⚠️ IMPORTANT : vérifier que le main fonctionne
                                        # Si le main est cassé et que tu continues,
                                        # tu vas écraser ta branche avec une version qui plante !
git checkout prenom/ma-tache            # Retourner sur ta branche
git pull origin main                    # Fusionner les dernières modifs du main dans ta branche
```

---

### 3. 🔨 PENDANT LE TRAVAIL

```bash
git branch                              # Vérifier sur quelle branche on est (la branche active a un *)
git status                              # Voir les fichiers modifiés à tout moment
git diff                                # Voir les changements en détail
```

> **Règle d'or :** Ne jamais travailler directement sur `main`. Toujours sur ta branche personnelle !

---

### 4. 🔴 FIN DE SESSION — Envoyer son travail

```bash
git status                              # Voir les fichiers modifiés
git add .                               # Préparer TOUS les fichiers modifiés
# OU pour ajouter des fichiers spécifiques :
git add nom_du_fichier.py

git commit -m "Description claire de ce que tu as fait"
# Exemples de bons messages :
# "Ajout de la fonction de calcul du ratio de Sharpe"
# "Correction bug dans le preprocessing des données"
# "Première version de la visualisation portefeuille"

git push origin prenom/ma-tache         # Envoyer sa branche sur GitHub
```

---

### 5. 🔀 CRÉER UNE PULL REQUEST (PR) SUR GITHUB

> ⚠️ **Cette étape se fait sur le site GitHub, pas dans le terminal !**

1. Va sur **github.com** → ton repository
2. GitHub affiche souvent une bannière jaune *"Compare & pull request"* → clique dessus
   - Sinon : onglet **"Pull requests"** → bouton vert **"New pull request"**
3. Vérifie que :
   - **base :** `main`
   - **compare :** `prenom/ma-tache`
4. Donne un **titre clair** à ta PR et une **description** de ce que tu as fait
5. Clique sur **"Create pull request"**
6. **Demande à un coéquipier de relire** (code review) avant de merger
7. Une fois approuvée → clique sur **"Merge pull request"** puis **"Confirm merge"**

---

### 6. ✅ APRÈS LE MERGE

```bash
git checkout main
git pull origin main                    # Récupérer le main mis à jour avec ton travail
```

> Tu peux ensuite créer une nouvelle branche pour ta prochaine tâche avec `git checkout -b prenom/nouvelle-tache`

---

## ⚠️ ERREURS FRÉQUENTES ET SOLUTIONS

| Problème | Solution |
|---|---|
| *"Je suis sur main par erreur"* | `git checkout prenom/ma-tache` |
| *"J'ai oublié de pull avant de travailler"* | `git pull origin main` sur ta branche |
| *"Conflit lors du pull"* | Ouvre les fichiers concernés, cherche `<<<<<<<`, résous manuellement, puis `git add .` et `git commit` |
| *"J'ai commité sur main par erreur"* | Préviens l'équipe, ne force pas le push |
| *"Mon push est refusé"* | Fais d'abord `git pull origin prenom/ma-tache` pour récupérer d'éventuels changements |

---

## 📐 RÈGLES DU GROUPE BB

- ✅ **Une branche par personne et par tâche** : `prenom/description-courte`
- ✅ **Des commits réguliers** avec des messages clairs en français ou anglais
- ✅ **Toujours passer par une Pull Request** pour merger dans main — jamais de push direct sur main
- ✅ **Relire le code des autres** avant d'approuver une PR
- ✅ **Communiquer** si tu travailles sur un fichier qu'un autre membre touche aussi

---

## 🗂️ STRUCTURE DU REPO

```
Sustainability-Aware-Asset-Management-BB/
│
├── README.md                   # Présentation du projet
├── github_workflow_BB.md       # Ce guide
├── data/                       # Données brutes et traitées
├── notebooks/                  # Jupyter notebooks d'analyse
├── src/                        # Code source Python
└── reports/                    # Rapports et visualisations
```

---

*Guide préparé pour le Groupe BB — Sustainability-Aware Asset Management*
