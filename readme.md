# 🏢 Système de Gestion des Sinistres

> Application web développée dans le cadre d'un stage de découverte pour la gestion des sinistres des collectivités locales.

## 📋 Table des Matières

- [Aperçu du Projet](#aperçu-du-projet)
- [Fonctionnalités](#fonctionnalités)
- [Technologies Utilisées](#technologies-utilisées)
- [Installation](#installation)
- [Configuration](#configuration)
- [Utilisation](#utilisation)
- [Structure du Projet](#structure-du-projet)
- [Captures d'Écran](#captures-décran)
- [Améliorations Futures](#améliorations-futures)

---

## 🎯 Aperçu du Projet

Ce système de gestion des sinistres permet aux collectivités locales de :
- Enregistrer et suivre les déclarations de sinistres
- Gérer les informations des postes comptables et des comptables
- Analyser les données avec des statistiques avancées
- Générer des documents Word automatiquement

**Développé avec** : Python Flask, MySQL, Bootstrap

---

## ✨ Fonctionnalités

### 📊 Gestion des Données
| Module | Description |
|--------|-------------|
| **Collectivités** | Gestion des codes postaux et organisationnels |
| **Postes Comptables** | Administration des postes et leurs libellés |
| **Comptables** | Profils des comptables (nom, email, sexe) |
| **Nature de Sinistre** | Catégorisation des types de sinistres |
| **Cours des Comptes** | Référentiel des cours de comptes |

### 🔧 Fonctionnalités Avancées
- ✅ Ajout d'entrées avec validation automatique
- ✅ Génération de documents Word
- ✅ Statistiques descriptives complètes
- ✅ Visualisations graphiques interactives
- ✅ Interface responsive avec Bootstrap

### 📈 Analyse Statistique
- **Métriques** : Moyenne, médiane, écart-type, variance, asymétrie, kurtosis
- **Graphiques** : Histogrammes, box plots, scatter plots, matrices de corrélation

---

## 🛠️ Technologies Utilisées

### Backend
```python
Flask 2.0+          # Framework web Python
MySQL 8.0+          # Base de données
Flask-MySQLdb       # Connecteur MySQL
python-docx         # Génération de documents Word
```

### Analyse de Données
```python
NumPy              # Calculs numériques
Pandas             # Manipulation de données
Matplotlib         # Visualisations
Seaborn           # Graphiques statistiques
SciPy             # Calculs statistiques avancés
```

### Frontend
```html
HTML5 + CSS3       # Structure et style
Bootstrap 4.0      # Framework CSS responsive
JavaScript         # Interactivité
```

---

## 🚀 Installation

### Prérequis
- Python 3.7+
- MySQL Server 8.0+
- pip (gestionnaire de paquets Python)

### 1. Cloner le projet
```bash
git clone https://github.com/votre-username/systeme-gestion-sinistres.git
cd systeme-gestion-sinistres
```

### 2. Installer les dépendances
```bash
pip install flask flask-mysqldb mysql-connector-python python-docx numpy matplotlib pandas seaborn scipy
```

---

## ⚙️ Configuration

### 1. Configuration de la base de données
Créer une base de données MySQL nommée `new_schema` :
```sql
CREATE DATABASE new_schema;
USE new_schema;
```

### 2. Création des tables
```sql
-- Table des collectivités
CREATE TABLE collectivites (
    code_poste VARCHAR(50),
    code_org VARCHAR(50),
    libelle_collectivite VARCHAR(255)
);

-- Table des postes comptables
CREATE TABLE postes_comptables (
    code_poste VARCHAR(50),
    libelle_poste VARCHAR(255)
);

-- Table des comptables
CREATE TABLE comptables (
    code_poste VARCHAR(50),
    nom VARCHAR(100),
    prenom VARCHAR(100),
    email VARCHAR(150),
    sexe VARCHAR(10)
);

-- Table des natures de sinistre
CREATE TABLE nature_sinistre (
    id INT AUTO_INCREMENT PRIMARY KEY,
    libelle VARCHAR(255)
);

-- Table des cours des comptes
CREATE TABLE cours_comptes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    libelle VARCHAR(255)
);

-- Table des entrées
CREATE TABLE entries (
    id INT AUTO_INCREMENT PRIMARY KEY,
    poste_comptable VARCHAR(255),
    numero_demande VARCHAR(100),
    date DATE,
    nature_sinistre VARCHAR(255),
    date_sinistre DATE,
    montant DECIMAL(10,2)
);
```

### 3. Configuration de l'application
Dans `app.py`, modifier les paramètres de connexion :
```python
app.config['MYSQL_HOST'] = 'localhost'
app.config['MYSQL_USER'] = 'votre_utilisateur'
app.config['MYSQL_PASSWORD'] = 'votre_mot_de_passe'
app.config['MYSQL_DB'] = 'new_schema'
```

---

## 🎮 Utilisation

### Lancer l'application
```bash
python app.py
```

### Accéder à l'interface
Ouvrir un navigateur et aller à : `http://localhost:5000`

### Navigation
1. **Accueil** : Vue d'ensemble du système
2. **Consultation** : Naviguer entre les différents modules
3. **Ajout d'entrée** : Enregistrer un nouveau sinistre
4. **Statistiques** : Analyser les données avec des graphiques

---

## 📁 Structure du Projet

```
systeme-gestion-sinistres/
│
├── 📄 app.py                 # Application Flask principale
├── 📄 README.md              # Documentation
├── 📄 .gitignore             # Fichiers à ignorer
│
└── 📁 templates/             # Templates HTML
    ├── 📄 index.html         # Page d'accueil
    ├── 📄 add_entry.html     # Formulaire d'ajout
    ├── 📄 confirmation.html  # Confirmation d'ajout
    ├── 📄 data.html          # Affichage des données
    └── 📄 statistics.html    # Page statistiques
```

---

## 📸 Captures d'Écran

### 🏠 Page d'Accueil
Interface principale avec navigation intuitive

### 📝 Formulaire d'Ajout
Saisie des informations de sinistre avec validation

### 📊 Statistiques
Graphiques interactifs et métriques détaillées

---

## 🔮 Améliorations Futures

### 🎯 Prochaines Fonctionnalités
- [ ] **Authentification** : Système de connexion utilisateur
- [ ] **API REST** : Intégration avec d'autres systèmes
- [ ] **Export de données** : Formats CSV, Excel, PDF
- [ ] **Tableau de bord** : Indicateurs en temps réel
- [ ] **Notifications** : Alertes automatiques

### 🚀 Améliorations Techniques
- [ ] **Tests unitaires** : Couverture de code complète
- [ ] **Containerisation** : Support Docker
- [ ] **Déploiement** : Configuration pour production
- [ ] **Sécurité** : Validation et sanitisation avancées

---

## 🎓 Contexte du Stage

**Objectifs pédagogiques atteints :**
- ✅ Découverte du développement web avec Flask
- ✅ Apprentissage de MySQL et bases de données
- ✅ Initiation à l'analyse de données avec Python
- ✅ Développement d'une application métier complète

**Compétences développées :**
- Programmation Python orientée web
- Gestion de bases de données relationnelles
- Analyse statistique et visualisation
- Interface utilisateur responsive



**⭐ Si ce projet vous a plu, n'hésitez pas à lui donner une étoile !**

*Développé avec ❤️ dans le cadre d'un stage de découverte*

