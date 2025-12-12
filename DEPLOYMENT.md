# 🌐 Guide de Déploiement - E-CV

## Options de Déploiement

### Option 1 : GitHub Pages (Frontend uniquement) ⚠️

**Limitation** : GitHub Pages ne supporte que les sites statiques. Le backend Node.js ne fonctionnera pas.

#### Étapes :
1. Aller sur votre repository GitHub
2. Settings → Pages
3. Source : Deploy from a branch
4. Branch : main → / (root)
5. Save

**URL** : `https://mohammedazzouzi1.github.io/E-CV/`

**Note** : Le formulaire de contact ne fonctionnera pas sans backend.

---

### Option 2 : Heroku (Recommandé) ✅

Heroku permet de déployer le backend Node.js + frontend.

#### Prérequis :
- Compte Heroku gratuit
- Heroku CLI installé

#### Étapes :

1. **Installer Heroku CLI**
```bash
# Windows (avec Chocolatey)
choco install heroku-cli

# Ou télécharger depuis https://devcenter.heroku.com/articles/heroku-cli
```

2. **Login Heroku**
```bash
heroku login
```

3. **Créer une app Heroku**
```bash
heroku create e-cv-portfolio
```

4. **Ajouter ClearDB MySQL (gratuit)**
```bash
heroku addons:create cleardb:ignite
```

5. **Récupérer les credentials MySQL**
```bash
heroku config:get CLEARDB_DATABASE_URL
```

6. **Configurer les variables d'environnement**
```bash
heroku config:set EMAIL_USER=votre_email@gmail.com
heroku config:set EMAIL_PASS=votre_mot_de_passe_app
```

7. **Modifier portfolio.js pour Heroku**
Ajouter au début du fichier :
```javascript
const port = process.env.PORT || 3000;
```

8. **Créer Procfile**
```bash
echo "web: node portfolio.js" > Procfile
```

9. **Déployer**
```bash
git add .
git commit -m "chore: prepare for Heroku deployment"
git push heroku main
```

10. **Ouvrir l'app**
```bash
heroku open
```

**URL** : `https://e-cv-portfolio.herokuapp.com`

---

### Option 3 : Vercel (Frontend + Serverless) 🚀

#### Étapes :

1. **Installer Vercel CLI**
```bash
npm install -g vercel
```

2. **Login**
```bash
vercel login
```

3. **Déployer**
```bash
vercel
```

4. **Configuration**
- Framework Preset : Other
- Build Command : (laisser vide)
- Output Directory : ./

**Note** : Nécessite de convertir le backend en Serverless Functions.

---

### Option 4 : Netlify (Frontend uniquement) 🎨

1. Aller sur [netlify.com](https://netlify.com)
2. New site from Git
3. Connecter GitHub
4. Sélectionner E-CV
5. Deploy

**URL** : `https://e-cv-portfolio.netlify.app`

---

### Option 5 : Railway (Recommandé pour Full-Stack) 🚂

Railway est une excellente alternative à Heroku.

#### Étapes :

1. **Aller sur [railway.app](https://railway.app)**
2. Sign up with GitHub
3. New Project → Deploy from GitHub repo
4. Sélectionner E-CV
5. Add MySQL database
6. Configurer les variables d'environnement
7. Deploy

**Avantages** :
- ✅ Gratuit (500h/mois)
- ✅ MySQL inclus
- ✅ Déploiement automatique
- ✅ Logs en temps réel

---

### Option 6 : Render (Alternative gratuite) 🎯

1. **Aller sur [render.com](https://render.com)**
2. New → Web Service
3. Connect GitHub → E-CV
4. Configuration :
   - Environment : Node
   - Build Command : `npm install`
   - Start Command : `node portfolio.js`
5. Add MySQL database (PostgreSQL gratuit disponible)
6. Deploy

---

## 🔧 Modifications Nécessaires pour le Déploiement

### 1. Modifier `portfolio.js`

```javascript
// Remplacer
const port = 3000;

// Par
const port = process.env.PORT || 3000;
```

### 2. Créer `Procfile` (pour Heroku)

```
web: node portfolio.js
```

### 3. Mettre à jour `package.json`

```json
{
  "scripts": {
    "start": "node portfolio.js",
    "dev": "nodemon portfolio.js"
  },
  "engines": {
    "node": ">=14.0.0",
    "npm": ">=6.0.0"
  }
}
```

### 4. Configuration Base de Données

Pour les services cloud, utilisez les variables d'environnement :

```javascript
const db = mysql.createConnection({
  host: process.env.DB_HOST || "localhost",
  user: process.env.DB_USER || "root",
  password: process.env.DB_PASSWORD || "",
  database: process.env.DB_NAME || "contact_messages",
});
```

---

## 📊 Comparaison des Options

| Service | Frontend | Backend | Database | Prix | Difficulté |
|---------|----------|---------|----------|------|------------|
| **GitHub Pages** | ✅ | ❌ | ❌ | Gratuit | ⭐ |
| **Heroku** | ✅ | ✅ | ✅ | Gratuit* | ⭐⭐⭐ |
| **Vercel** | ✅ | ⚠️ | ❌ | Gratuit | ⭐⭐ |
| **Netlify** | ✅ | ⚠️ | ❌ | Gratuit | ⭐⭐ |
| **Railway** | ✅ | ✅ | ✅ | Gratuit | ⭐⭐ |
| **Render** | ✅ | ✅ | ✅ | Gratuit | ⭐⭐ |

*Heroku gratuit limité à 550h/mois

---

## 🎯 Recommandation

**Pour E-CV (avec backend)** :
1. **Railway** - Le plus simple et gratuit
2. **Render** - Bonne alternative
3. **Heroku** - Classique mais limité

**Pour frontend uniquement** :
1. **GitHub Pages** - Le plus simple
2. **Netlify** - Plus de fonctionnalités

---

## 🔐 Sécurité en Production

Avant de déployer :

1. ✅ Vérifier que `.env` est dans `.gitignore`
2. ✅ Configurer les variables d'environnement sur le service cloud
3. ✅ Utiliser HTTPS (automatique sur la plupart des services)
4. ✅ Activer CORS uniquement pour votre domaine
5. ✅ Valider toutes les entrées utilisateur
6. ✅ Limiter le taux de requêtes (rate limiting)

---

## 📞 Support

Pour plus d'aide :
- [Documentation Heroku](https://devcenter.heroku.com/)
- [Documentation Railway](https://docs.railway.app/)
- [Documentation Render](https://render.com/docs)

---

**Bon déploiement ! 🚀**
