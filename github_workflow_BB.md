# Guide GitHub — Travail en groupe
## Projet : Sustainability-Aware Asset Management | Groupe BB

---

## RÈGLE ABSOLUE — Les données ne se poussent JAMAIS sur GitHub

Les dossiers `Data/` et `Data_2026/` contiennent des fichiers Excel volumineux.
Ils sont ignorés automatiquement grâce au fichier `.gitignore` — **ne le supprime jamais**.
Chaque membre du groupe garde ses données en local sur sa machine.

---

## RÉSUMÉ RAPIDE (à garder sous la main)

```bash
# 1ère fois — Début de session (cloner + créer sa branche)
git checkout main
git pull origin main
git checkout -b prenom/ma-tache

# Toutes les fois suivantes — Début de session (récupérer le main sur sa branche)
git checkout main       # Vérifier que le main fonctionne avant de continuer
git checkout prenom/ma-tache
git pull origin main

# Pendant le travail
git branch              # Vérifier sur quelle branche on est

# Fin de session — Envoyer son travail
git status                        # Voir les fichiers modifiés
git add *.ipynb *.md         # Ajouter notebooks, scripts et docs — PAS les données
git commit -m "message clair"
git push origin prenom/ma-tache   # Envoyer sa branche sur GitHub
# Puis créer une Pull Request sur GitHub (voir section dédiée ci-dessous)

# Après le merge
git checkout main
git pull origin main
```

---

## GUIDE COMPLET ÉTAPE PAR ÉTAPE

### 1. Cloner le repo (une seule fois, au tout début)

```bash
git clone https://github.com/yvdri/Sustainability-Aware-Asset-Management-BB.git
cd Sustainability-Aware-Asset-Management-BB
```

> Après le clone, place manuellement le dossier `Data_2026/` dans le repo en local.
> Il ne sera jamais envoyé sur GitHub (protégé par `.gitignore`).

---

### 2. DÉBUT DE SESSION

#### 1ère fois sur ce projet (créer sa branche)

```bash
git checkout main
git pull origin main                    # Récupérer la dernière version du main
git checkout -b prenom/ma-tache         # Créer et aller sur ta branche personnelle
```

> Exemples de noms de branche : `rijad/data-cleaning`, `matthieu/optimisation`, `aymen/carbon-portfolio`

#### Toutes les sessions suivantes (mettre à jour sa branche)

```bash
git checkout main                       # Vérifier que le main fonctionne
git checkout prenom/ma-tache            # Retourner sur ta branche
git pull origin main                    # Fusionner les dernières modifs du main dans ta branche
```

---

### 3. PENDANT LE TRAVAIL

```bash
git branch                              # Vérifier sur quelle branche on est (la branche active a un *)
git status                              # Voir les fichiers modifiés à tout moment
git diff                                # Voir les changements en détail
```

> Règle d'or : Ne jamais travailler directement sur `main`. Toujours sur ta branche personnelle.

---

### 4. FIN DE SESSION — Envoyer son travail

```bash
git status                              # Vérifier ce qui a changé
```

**Ajouter uniquement les fichiers de code — jamais les données :**

```bash
# Ajouter tous les notebooks d'un coup
git add *.ipynb

# Ajouter des scripts Python
git add *.py

# Ajouter un fichier spécifique
git add nom_du_fichier.ipynb

# NE JAMAIS faire git add Data/ ou git add Data_2026/ ou git add *.xlsx
# Le .gitignore les bloque automatiquement, mais mieux vaut être explicite
```

```bash
git commit -m "Description claire de ce que tu as fait"
# Exemples :
# "Ajout filtres data cleaning et investment set"
# "Correction bug calcul rendements mensuels"
# "Première version portefeuille minimum-variance"

git push origin prenom/ma-tache
```

---

### 5. CRÉER UNE PULL REQUEST (PR) SUR GITHUB

> Cette étape se fait sur le site GitHub, pas dans le terminal.

1. Va sur **github.com** → ton repository
2. GitHub affiche souvent une bannière *"Compare & pull request"* → clique dessus
   - Sinon : onglet **"Pull requests"** → bouton vert **"New pull request"**
3. Vérifie que :
   - **base :** `main`
   - **compare :** `prenom/ma-tache`
4. Donne un **titre clair** à ta PR et une **description** de ce que tu as fait
5. Clique sur **"Create pull request"**
6. **Demande à un coéquipier de relire** avant de merger
7. Une fois approuvée → clique sur **"Merge pull request"** puis **"Confirm merge"**

---

### 6. APRÈS LE MERGE

```bash
git checkout main
git pull origin main                    # Récupérer le main mis à jour
```

---

## ERREURS FRÉQUENTES ET SOLUTIONS

| Problème | Solution |
|---|---|
| *"Je suis sur main par erreur"* | `git checkout prenom/ma-tache` |
| *"J'ai oublié de pull avant de travailler"* | `git pull origin main` sur ta branche |
| *"Conflit lors du pull"* | Ouvre les fichiers concernés, cherche `<<<<<<<`, résous manuellement, puis `git add .` et `git commit` |
| *"J'ai commité sur main par erreur"* | Préviens l'équipe, ne force pas le push |
| *"Mon push est refusé"* | Fais d'abord `git pull origin prenom/ma-tache` pour récupérer d'éventuels changements |
| *"J'ai accidentellement ajouté un fichier Excel"* | `git rm --cached nom_fichier.xlsx` puis commit |

---

## RÈGLES DU GROUPE BB

- **Une branche par personne et par tâche** : `prenom/description-courte`
- **Des commits réguliers** avec des messages clairs en français ou anglais
- **Toujours passer par une Pull Request** pour merger dans main — jamais de push direct sur main
- **Relire le code des autres** avant d'approuver une PR
- **Communiquer** si tu travailles sur un fichier qu'un autre membre touche aussi
- **Ne jamais pousser les données** — chacun garde `Data_2026/` en local

---

## STRUCTURE DU REPO

```
Sustainability-Aware-Asset-Management-BB/
│
├── .gitignore                              # Ignore les données et fichiers temporaires
├── README.md                               # Présentation du projet
├── github_workflow_BB.md                   # Ce guide
│
├── *.ipynb                                 # Notebooks Jupyter (un ou plusieurs selon l'avancement)
│                                           # Ex: Sustainability_Aware_Asset_Management_Group_BB.ipynb
│
├── Data_2026/                              # NON versionné — données en local uniquement
│   ├── Static_2025.xlsx
│   ├── DS_RI_T_USD_M_2025.xlsx
│   └── ...
│
└── reports/                                # Rapports et visualisations (PDF, figures)
```

---

*Guide préparé pour le Groupe BB — Sustainability-Aware Asset Management*
