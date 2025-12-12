# 🚀 Guide de Déploiement Git - E-CV

## 📝 Instructions pour publier sur GitHub

### 1️⃣ Description du Repository (À copier sur GitHub)

```
🎓 Professional portfolio website for computer engineering students. Features interactive resumes, dark/light mode, contact form with email notifications, and MySQL backend. Built with Node.js, Express, and modern responsive design.
```

### 2️⃣ Topics/Tags suggérés pour GitHub

Ajoutez ces topics à votre repository pour améliorer la visibilité :

```
portfolio
nodejs
express
mysql
javascript
html5
css3
responsive-design
dark-mode
contact-form
nodemailer
student-project
web-development
full-stack
glassmorphism
```

### 3️⃣ Commandes Git pour publier

#### Initialiser Git (si pas déjà fait)
```bash
git init
```

#### Ajouter tous les fichiers
```bash
git add .
```

#### Premier commit
```bash
git commit -m "🎉 Initial commit: E-CV Portfolio Project

- ✨ Add interactive portfolio homepage
- 📄 Add detailed resume pages for 3 team members
- 📧 Add contact form with email notifications
- 🌓 Add dark/light mode toggle
- 📱 Add responsive design for all devices
- 🎨 Add glassmorphism effects and animations
- 🗄️ Add MySQL database integration
- 📨 Add Nodemailer email service
- 📚 Add comprehensive documentation"
```

#### Ajouter le remote GitHub
```bash
git remote add origin https://github.com/mohammedazzouzi1/E-CV.git
```

#### Vérifier le remote
```bash
git remote -v
```

#### Pousser vers GitHub
```bash
git branch -M main
git push -u origin main
```

### 4️⃣ Commandes Git Utiles

#### Vérifier le statut
```bash
git status
```

#### Voir l'historique des commits
```bash
git log --oneline --graph --all
```

#### Créer une nouvelle branche
```bash
git checkout -b feature/nouvelle-fonctionnalite
```

#### Changer de branche
```bash
git checkout main
```

#### Fusionner une branche
```bash
git checkout main
git merge feature/nouvelle-fonctionnalite
```

#### Mettre à jour depuis GitHub
```bash
git pull origin main
```

#### Annuler les modifications non commitées
```bash
git checkout -- .
```

#### Voir les différences
```bash
git diff
```

### 5️⃣ Workflow Recommandé

#### Pour ajouter une nouvelle fonctionnalité :
```bash
# 1. Créer une branche
git checkout -b feature/ma-fonctionnalite

# 2. Faire vos modifications
# ... éditer les fichiers ...

# 3. Ajouter et commiter
git add .
git commit -m "feat: description de la fonctionnalité"

# 4. Pousser la branche
git push origin feature/ma-fonctionnalite

# 5. Créer une Pull Request sur GitHub
# 6. Après merge, revenir sur main
git checkout main
git pull origin main
```

#### Pour corriger un bug :
```bash
git checkout -b fix/correction-bug
# ... faire les corrections ...
git add .
git commit -m "fix: correction du bug XYZ"
git push origin fix/correction-bug
```

### 6️⃣ Conventions de Commit

Utilisez des commits clairs et descriptifs :

```bash
# Nouvelle fonctionnalité
git commit -m "feat: ajout du système de commentaires"

# Correction de bug
git commit -m "fix: correction de l'affichage mobile"

# Documentation
git commit -m "docs: mise à jour du README"

# Style/CSS
git commit -m "style: amélioration du design des cartes"

# Refactoring
git commit -m "refactor: optimisation du code serveur"

# Performance
git commit -m "perf: optimisation du chargement des images"

# Tests
git commit -m "test: ajout de tests unitaires"
```

### 7️⃣ Fichiers à NE PAS commiter

Assurez-vous que ces fichiers sont dans `.gitignore` :
- ❌ `node_modules/`
- ❌ `.env` (informations sensibles)
- ❌ `package-lock.json` (optionnel)
- ❌ Fichiers IDE (`.vscode/`, `.idea/`)
- ❌ Fichiers OS (`.DS_Store`, `Thumbs.db`)

### 8️⃣ Mettre à jour le .gitignore

Si vous avez déjà commité des fichiers à ignorer :
```bash
# Supprimer du cache Git
git rm -r --cached node_modules
git rm --cached .env

# Commiter la suppression
git commit -m "chore: update .gitignore"
git push origin main
```

### 9️⃣ Créer un Release/Tag

Pour marquer une version :
```bash
# Créer un tag
git tag -a v1.0.0 -m "Version 1.0.0 - Initial Release"

# Pousser le tag
git push origin v1.0.0

# Pousser tous les tags
git push origin --tags
```

### 🔟 Résoudre les Conflits

Si vous avez des conflits lors d'un merge :
```bash
# 1. Git vous indiquera les fichiers en conflit
git status

# 2. Ouvrir les fichiers et résoudre manuellement
# Chercher les marqueurs <<<<<<< ======= >>>>>>>

# 3. Après résolution
git add .
git commit -m "merge: résolution des conflits"
git push
```

### 📊 Vérifier avant de Push

Checklist avant chaque push :
- ✅ `git status` - Vérifier les fichiers modifiés
- ✅ Tester le code localement
- ✅ Vérifier que `.env` n'est PAS dans les fichiers à commiter
- ✅ Relire le message de commit
- ✅ `git log` - Vérifier l'historique

### 🔐 Sécurité

**IMPORTANT** : Ne JAMAIS commiter :
- 🚫 Mots de passe
- 🚫 Clés API
- 🚫 Tokens d'authentification
- 🚫 Informations de base de données

Utilisez toujours `.env` et `.env.example` !

### 📞 Aide

En cas de problème :
```bash
# Voir l'aide Git
git --help

# Aide pour une commande spécifique
git commit --help
```

---

## 🎯 Résumé Rapide

```bash
# Workflow quotidien
git pull                          # Récupérer les dernières modifications
git checkout -b feature/ma-feature # Créer une branche
# ... faire vos modifications ...
git add .                         # Ajouter les fichiers
git commit -m "feat: description" # Commiter
git push origin feature/ma-feature # Pousser
# Créer une Pull Request sur GitHub
```

**Bon développement ! 🚀**
