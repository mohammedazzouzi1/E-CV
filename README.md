# 🎓 E-CV - Portfolio Professionnel

<div align="center">

![E-CV Logo](./pictures/logo.png)

**Portfolio interactif pour étudiants en génie informatique**

[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)](https://expressjs.com/)
[![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

[🌐 Démo en ligne](#) • [📖 Documentation](#fonctionnalités) • [🚀 Installation](#installation)

</div>

---

## 📋 Table des matières

- [À propos](#-à-propos)
- [Fonctionnalités](#-fonctionnalités)
- [Technologies](#-technologies)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Utilisation](#-utilisation)
- [Structure du projet](#-structure-du-projet)
- [Captures d'écran](#-captures-décran)
- [Contributeurs](#-contributeurs)
- [Licence](#-licence)

---

## 🎯 À propos

**E-CV** est un site web de portfolio personnel conçu pour présenter le parcours académique, les compétences et les projets de trois étudiants en informatique à l'Université Privée de Fès. Il offre une interface intuitive et moderne, mettant en avant leurs réalisations et facilitant la connexion avec des recruteurs et collaborateurs.

### 👥 Équipe AHA

- **Mohammed AZZOUZI** - [azzouzi-moh@upf.ac.ma](mailto:azzouzi-moh@upf.ac.ma)
- **Amine ASSOU** - [assou-ami@upf.ac.ma](mailto:assou-ami@upf.ac.ma)
- **Mohamed HIMMI** - [himmi-moh@upf.ac.ma](mailto:himmi-moh@upf.ac.ma)

---

## ✨ Fonctionnalités

### 🎨 Interface Utilisateur
- ✅ **Design Moderne** - Interface élégante avec effets de glassmorphisme
- 🌓 **Mode Sombre/Clair** - Basculement entre thèmes avec sauvegarde des préférences
- 📱 **Responsive Design** - Optimisé pour mobile, tablette et desktop
- ✨ **Animations Fluides** - Effets de scroll reveal et transitions CSS
- 🎭 **Effet Typewriter** - Animation de texte dynamique sur la page d'accueil

### 👤 Profils Interactifs
- 🃏 **Cartes Utilisateur** - Cartes interactives avec effet hover
- 📄 **CV Détaillés** - Pages de résumé complètes pour chaque membre
- 🏆 **Galerie de Certificats** - Affichage des certifications avec zoom
- 💼 **Projets** - Showcase de projets avec descriptions
- 🌐 **Compétences Linguistiques** - Barres de progression animées

### 📧 Système de Contact
- 📬 **Formulaire de Contact** - Interface utilisateur intuitive
- 💾 **Base de Données MySQL** - Stockage sécurisé des messages
- 📨 **Notifications Email** - Envoi automatique d'emails via Nodemailer
  - Email de confirmation à l'utilisateur
  - Notification à l'administrateur
- ✅ **Validation des Données** - Vérification côté serveur

### 🔧 Backend Robuste
- ⚡ **Serveur Express.js** - API RESTful performante
- 🔐 **Variables d'Environnement** - Configuration sécurisée avec dotenv
- 🌍 **CORS Activé** - Support des requêtes cross-origin
- 📊 **Gestion d'Erreurs** - Logging et gestion des erreurs

---

## 🛠 Technologies

### Frontend
| Technologie | Description |
|------------|-------------|
| **HTML5** | Structure sémantique moderne |
| **CSS3** | Styling avancé (Flexbox, Grid, Animations) |
| **JavaScript (ES6+)** | Logique interactive côté client |
| **Lottie** | Animations vectorielles |

### Backend
| Technologie | Version | Description |
|------------|---------|-------------|
| **Node.js** | Latest | Runtime JavaScript |
| **Express.js** | ^4.21.2 | Framework web minimaliste |
| **MySQL** | ^2.18.1 | Base de données relationnelle |
| **Nodemailer** | ^6.9.16 | Envoi d'emails |
| **dotenv** | ^16.4.7 | Gestion des variables d'environnement |
| **CORS** | ^2.8.5 | Middleware CORS |
| **body-parser** | ^1.20.3 | Parsing des requêtes |

---

## 🚀 Installation

### Prérequis

Assurez-vous d'avoir installé :
- [Node.js](https://nodejs.org/) (v14 ou supérieur)
- [MySQL](https://www.mysql.com/) (v5.7 ou supérieur)
- [Git](https://git-scm.com/)

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/mohammedazzouzi1/E-CV.git
cd E-CV
```

2. **Installer les dépendances**
```bash
npm install
```

3. **Configurer la base de données**
```bash
# Se connecter à MySQL
mysql -u root -p

# Créer la base de données
source contact_messages.sql
```

4. **Configurer les variables d'environnement**
```bash
# Créer un fichier .env à la racine du projet
cp .env.example .env
```

Modifier le fichier `.env` avec vos informations :
```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=votre_mot_de_passe
DB_NAME=contact_messages

EMAIL_USER=votre_email@gmail.com
EMAIL_PASS=votre_mot_de_passe_application
```

> ⚠️ **Note** : Pour Gmail, utilisez un [mot de passe d'application](https://support.google.com/accounts/answer/185833)

5. **Démarrer le serveur**
```bash
node portfolio.js
```

6. **Accéder à l'application**
```
http://localhost:3000
```

---

## ⚙️ Configuration

### Configuration de la base de données

La base de données `contact_messages` contient une table `messages` :

```sql
CREATE TABLE messages (
  id INT(11) NOT NULL AUTO_INCREMENT,
  name VARCHAR(100) DEFAULT NULL,
  email VARCHAR(100) DEFAULT NULL,
  subject VARCHAR(200) DEFAULT NULL,
  message TEXT DEFAULT NULL,
  created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (id)
);
```

### Configuration Email (Nodemailer)

Pour utiliser Gmail :
1. Activer la validation en 2 étapes
2. Générer un mot de passe d'application
3. Utiliser ce mot de passe dans `EMAIL_PASS`

---

## 📖 Utilisation

### Navigation

- **Page d'accueil** (`/`) - Présentation de l'équipe avec cartes interactives
- **Résumés** - CV détaillés accessibles via le menu déroulant
  - `/html/resume-azzouzi.html`
  - `/html/resume-amine.html`
  - `/html/resume-himmi.html`
- **Contact** (`/html/contact.html`) - Formulaire de contact

### Fonctionnalités Utilisateur

#### Basculer entre Mode Sombre/Clair
Cliquez sur le bouton 🌑/☀️ en bas à droite de la page.

#### Envoyer un Message
1. Accéder à la page Contact
2. Remplir le formulaire
3. Cliquer sur "Send Message"
4. Recevoir une confirmation par email

#### Navigation Mobile
Sur mobile, utilisez le menu hamburger (☰) pour accéder à la navigation.

---

## 📁 Structure du projet

```
E-CV/
├── 📄 index.html              # Page d'accueil
├── 📄 portfolio.js            # Serveur Express.js
├── 📄 package.json            # Dépendances npm
├── 📄 .env                    # Variables d'environnement (non versionné)
├── 📄 contact_messages.sql    # Script SQL de la base de données
├── 📄 README.md               # Documentation
│
├── 📁 html/                   # Pages HTML
│   ├── contact.html           # Formulaire de contact
│   ├── resume-azzouzi.html    # CV Mohammed
│   ├── resume-amine.html      # CV Amine
│   └── resume-himmi.html      # CV Mohamed
│
├── 📁 style/                  # Fichiers CSS
│   ├── style.css              # Styles principaux
│   ├── resume.css             # Styles des CV
│   └── contact.css            # Styles du formulaire
│
├── 📁 script/                 # Scripts JavaScript
│   └── script.js              # Logique frontend
│
├── 📁 pictures/               # Images
│   ├── azzouzi.JPG            # Photo Mohammed
│   ├── amine.jpg              # Photo Amine
│   ├── himmi.jpg              # Photo Mohamed
│   ├── logo.png               # Logo AHA
│   ├── black-background.jpg   # Fond mode sombre
│   └── light-background.jpg   # Fond mode clair
│
├── 📁 cv/                     # CV PDF
│   ├── Mohammed Azzouzi.pdf
│   ├── CV - ASSOU Amine 2024.pdf
│   └── CV HIMMI Med.pdf
│
├── 📁 certificates/           # Certificats (21 fichiers)
│   ├── Python_Essentials_1.png
│   ├── JavaScript_Essentials_1.jpg
│   └── ...
│
└── 📁 projects/               # Images de projets
    ├── skyluxe.jpg
    ├── chatbot.jpg
    └── ...
```

---

## 📸 Captures d'écran

### 🏠 Page d'accueil
![Page d'accueil](./pictures/logo.png)
*Interface moderne avec cartes interactives des membres de l'équipe*

### 🌓 Mode Sombre/Clair
| Mode Sombre | Mode Clair |
|-------------|------------|
| ![Dark Mode](./pictures/black-background.jpg) | ![Light Mode](./pictures/light-background.jpg) |

### 📱 Design Responsive
*Optimisé pour tous les appareils : desktop, tablette, mobile*

---

## 🎨 Fonctionnalités CSS Avancées

- **Glassmorphism** - Effets de verre avec `backdrop-filter: blur()`
- **Animations CSS** - Transitions fluides et keyframes
- **Flexbox & Grid** - Layouts modernes et flexibles
- **Media Queries** - Responsive design avec breakpoints
- **Custom Properties** - Variables CSS pour la cohérence
- **Pseudo-éléments** - Effets visuels avancés

---

## 🔒 Sécurité

- ✅ Variables d'environnement pour les données sensibles
- ✅ Validation des entrées utilisateur
- ✅ Protection contre les injections SQL (requêtes paramétrées)
- ✅ CORS configuré
- ✅ Gestion des erreurs côté serveur

---

## 🚧 Améliorations Futures

- [ ] Ajouter l'authentification utilisateur
- [ ] Implémenter un système de blog
- [ ] Intégrer un chat en temps réel
- [ ] Ajouter des tests unitaires
- [ ] Déployer sur un serveur cloud (Heroku, AWS, etc.)
- [ ] Optimiser les performances (lazy loading, compression)
- [ ] Ajouter le support multilingue (FR/EN/AR)
- [ ] Intégrer Google Analytics

---

## 👥 Contributeurs

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/mohammedazzouzi1">
        <img src="./pictures/azzouzi.JPG" width="100px;" alt="Mohammed Azzouzi"/><br />
        <sub><b>Mohammed AZZOUZI</b></sub>
      </a><br />
      💻 🎨 📖
    </td>
    <td align="center">
      <img src="./pictures/amine.jpg" width="100px;" alt="Amine Assou"/><br />
      <sub><b>Amine ASSOU</b></sub><br />
      💻 🎨 📖
    </td>
    <td align="center">
      <img src="./pictures/himmi.jpg" width="100px;" alt="Mohamed Himmi"/><br />
      <sub><b>Mohamed HIMMI</b></sub><br />
      💻 🎨 📖
    </td>
  </tr>
</table>

### 🏫 Institution
**Université Privée de Fès (UPF)**  
Génie Informatique - Master Intégré

---

## 📞 Contact

Pour toute question ou suggestion :

- 📧 Email : aha.support@gmail.com
- 📍 Adresse : Lotissement Quaraouiyine, Route Ain Chkef, Fès 30000
- 📱 Téléphone : +212 666-666666

---

## 📄 Licence

Ce projet est sous licence **MIT** - voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

## 🙏 Remerciements

- [Lottie](https://lottiefiles.com/) pour les animations
- [Font Awesome](https://fontawesome.com/) pour les icônes
- [Google Fonts](https://fonts.google.com/) pour les polices
- [Cisco Networking Academy](https://www.netacad.com/) pour les certifications
- L'Université Privée de Fès pour le soutien académique

---

## 📊 Statistiques du Projet

![GitHub repo size](https://img.shields.io/github/repo-size/mohammedazzouzi1/E-CV)
![GitHub stars](https://img.shields.io/github/stars/mohammedazzouzi1/E-CV?style=social)
![GitHub forks](https://img.shields.io/github/forks/mohammedazzouzi1/E-CV?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/mohammedazzouzi1/E-CV?style=social)

---

<div align="center">

**Fait avec ❤️ par l'équipe AHA**

⭐ Si vous aimez ce projet, n'hésitez pas à lui donner une étoile !

[⬆ Retour en haut](#-e-cv---portfolio-professionnel)

</div>
