# <img src="https://raw.githubusercontent.com/iris-william/memo-github/c57254b985ede98da25b5a9e1a9efcc3900bfe9d/assets/flags/france.svg" height="24" alt="French Flag"> MEMO GITHUB EN FRANÇAIS
**Commandes de base pour les débutants sur GitHub**
<hr>

## Prérequis
- Avoir un compte GitHub
- Git installé et accessible (path) sur la machine
- Identifiants initialisés en global 
  - `git config --global user.name "Ton Nom"`
  - `git config --global user.email "ton@email.com"`  

### Vérifier son installation git
```bash
Avec la console Windows (cmd) ou PowerShell :
git --version : renvoie la version de git
where git : renvoie l'emplacement de l'exécutable accessible

Si besoin d'ajouter git au path :
1) Menu Démarrer → “Variables d’environnement”
2) “Modifier les variables d’environnement système”
3) Variables d’environnement
4) Dans Path → Modifier
5) Ajouter `C:\Program Files\Git\cmd` (ou le chemin renvoyé par `where git`)
```
### Initialliser ses identifiants pour pouvoir synchroniser les travaux
```bash
git config --global user.name "your_name"
git config --global user.email "username@domain.tld"
```

## xxx

### yyy


## Modifier un projet jamais importé
- 1️⃣ Importer le projet avec `git clone` 
- 2️⃣
- 3️⃣
- 4️⃣


## Modifier un projet déjà importé
---
---
---
# MÉMO GITHUB - GIT POUR LES NULS - TUTO FRANÇAIS
<div align="center"><img src="../assets/Images/carto_mentale.png" alt="carto mentale GitHub"></img></div>

## Pré requis

## Commandes de base

## Travailler sur une nouvelle branche ()

## Renvoyer la branche sur GitHub (push)

## Reprendre une branche sur un autre PC (ou reprendre une branche jamais importée)

## Valider une branche (Merge)

## Poursuivre les travaux sur une branche après un merge

## Supprimer une branche


---
---
---
## Clone du projet

```bash
git clone URL_DU_PROJET
cd NOM_DU_PROJET
```

---

# Récupérer une branche distante (UNE SEULE FOIS par PC et par branche)

Exemple avec `ma_branche` :

```bash
git fetch
git switch -c ma_branche --track origin/ma_branche
```

Après ça, la branche existe localement.

Tu ne refais plus cette commande pour cette branche.

---

# Vérifier les branches

## Branches locales

```bash
git branch
```

## Toutes les branches (locales + distantes)

```bash
git branch -a
```

---

# Workflow quotidien

## Avant de travailler (quand on change de PC)

```bash
git switch ma_branche
git pull
```

---

## Travailler puis sauvegarder sur GitHub

```bash
git add .
git commit -m "Mon message"
git push
```

---

# Workflow typique entre 2 PC

```text
PC A :
pull → travail → commit → push

PC B :
pull → travail → commit → push

PC A :
pull → travail → commit → push
```

IMPORTANT :
Toujours faire un `git pull` avant de recommencer à travailler sur un autre PC.

---

# Créer une nouvelle branche

Depuis `main` :

```bash
git switch main
git pull
git switch -c nouvelle_branche
```

Puis premier push :

```bash
git push -u origin nouvelle_branche
```

---

# Merge d'une branche terminée

## Revenir sur main

```bash
git switch main
git pull
```

## Merge

```bash
git merge ma_branche
```

## Push

```bash
git push
```

---

# Supprimer une branche après merge

## Supprimer localement

```bash
git branch -d ma_branche
```

## Supprimer sur GitHub

```bash
git push origin --delete ma_branche
```

---

# Nettoyer les branches supprimées sur un autre PC

```bash
git fetch --prune
```

---

# Voir l'historique des commits

```bash
git log --oneline
```

Exemple :

```text
a1b2c3d Correction bug
e4f5g6h Ajout formulaire
i7j8k9l Version stable
```

---

# Revenir à un ancien commit (NON pushé)

ATTENTION :
Cette commande supprime les commits après le commit ciblé.

```bash
git reset --hard ID_DU_COMMIT
```

Exemple :

```bash
git reset --hard i7j8k9l
```

---

# Annuler un commit déjà pushé (SAFE)

```bash
git revert ID_DU_COMMIT
git push
```

Ça crée un nouveau commit qui annule l’ancien.

---

# Annuler un merge (SAFE)

## Trouver le commit de merge

```bash
git log --oneline
```

Exemple :

```text
f9e8d7c Merge branch 'ma_branche'
```

## Annuler le merge

```bash
git revert -m 1 f9e8d7c
git push
```

---

# Revenir temporairement à un ancien état

```bash
git switch --detach ID_DU_COMMIT
```

Revenir ensuite sur la branche :

```bash
git switch ma_branche
```

---

# Sauvegarde rapide avant manipulation risquée

```bash
git branch sauvegarde_temp
```

---

# Commandes modernes

Git moderne recommande :

## Changer de branche

```bash
git switch ma_branche
```

## Créer une branche

```bash
git switch -c ma_branche
```

## Restaurer un fichier

```bash
git restore fichier.txt
```

Ancienne commande encore valide :

```bash
git checkout
```

mais `switch` et `restore` sont plus clairs.

---

# Rappel ultra simple

## Quand tu commences à travailler

```bash
git pull
```

## Quand tu finis

```bash
git add .
git commit -m "message"
git push
```
