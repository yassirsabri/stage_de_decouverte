📊 Système de Gestion des Sinistres - Stage de Découverte
🎯 Description du Projet
Ce projet a été développé dans le cadre d'un stage de découverte et consiste en une application web de gestion des sinistres pour les collectivités locales. L'application permet de gérer les données relatives aux postes comptables, aux comptables, aux collectivités et aux sinistres déclarés.

✨ Fonctionnalités
🔍 Consultation des Données
Collectivités : Visualisation des codes postaux, codes organisationnels et libellés
Postes Comptables : Gestion des codes et libellés des postes
Comptables : Informations sur les comptables (nom, prénom, email, sexe)
Nature de Sinistre : Catégorisation des types de sinistres
Cours des Comptes : Référentiel des cours de comptes
📝 Gestion des Entrées
Ajout de nouvelles entrées de sinistres
Formulaire avec validation des données
Génération automatique de documents Word
📈 Statistiques Avancées
Statistiques descriptives : Moyenne, médiane, écart-type, variance, asymétrie, kurtosis
Visualisations :
Histogramme de distribution des montants
Box plot pour l'analyse des valeurs aberrantes
Scatter plot avec ligne de régression
Matrice de corrélation
🛠️ Technologies Utilisées
Backend
Flask : Framework web Python
MySQL : Base de données relationnelle
Flask-MySQLdb : Connecteur MySQL pour Flask
Frontend
HTML5 : Structure des pages
Bootstrap 4 : Framework CSS pour le design responsive
JavaScript : Interactivité côté client
Analyse de Données
NumPy : Calculs numériques
Pandas : Manipulation des données
Matplotlib : Génération de graphiques
Seaborn : Visualisations statistiques avancées
SciPy : Calculs statistiques
Génération de Documents
python-docx : Création de documents Word
📋 Prérequis
Python 3.7+
MySQL Server
pip (gestionnaire de paquets Python)
🚀 Installation
Cloner le repository
bash
git clone https://github.com/votre-username/systeme-gestion-sinistres.git
cd systeme-gestion-sinistres
Installer les dépendances
bash
pip install flask flask-mysqldb mysql-connector-python python-docx numpy matplotlib pandas seaborn scipy
Configuration de la base de données
Créer une base de données MySQL nommée new_schema
Mettre à jour les paramètres de connexion dans app.py :
python
app.config['MYSQL_HOST'] = 'localhost'
app.config['MYSQL_USER'] = 'votre_utilisateur'
app.config['MYSQL_PASSWORD'] = 'votre_mot_de_passe'
app.config['MYSQL_DB'] = 'new_schema'
Créer les tables nécessaires
sql
CREATE TABLE collectivites (
    code_poste VARCHAR(50),
    code_org VARCHAR(50),
    libelle_collectivite VARCHAR(255)
);

CREATE TABLE postes_comptables (
    code_poste VARCHAR(50),
    libelle_poste VARCHAR(255)
);

CREATE TABLE comptables (
    code_poste VARCHAR(50),
    nom VARCHAR(100),
    prenom VARCHAR(100),
    email VARCHAR(150),
    sexe VARCHAR(10)
);

CREATE TABLE nature_sinistre (
    id INT AUTO_INCREMENT PRIMARY KEY,
    libelle VARCHAR(255)
);

CREATE TABLE cours_comptes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    libelle VARCHAR(255)
);

CREATE TABLE entries (
    id INT AUTO_INCREMENT PRIMARY KEY,
    poste_comptable VARCHAR(255),
    numero_demande VARCHAR(100),
    date DATE,
    nature_sinistre VARCHAR(255),
    date_sinistre DATE,
    montant DECIMAL(10,2)
);
🎮 Utilisation
Lancer l'application
bash
python app.py
Accéder à l'application
Ouvrir un navigateur web
Aller à http://localhost:5000
Navigation
Utiliser la barre de navigation pour accéder aux différentes sections
Ajouter des entrées via le formulaire dédié
Consulter les statistiques pour analyser les données
📁 Structure du Projet
systeme-gestion-sinistres/
├── app.py                 # Application Flask principale
├── templates/             # Templates HTML
│   ├── index.html         # Page d'accueil
│   ├── add_entry.html     # Formulaire d'ajout d'entrée
│   ├── confirmation.html  # Page de confirmation
│   ├── data.html          # Template pour l'affichage des données
│   └── statistics.html    # Page des statistiques
├── details.docx           # Document Word généré
└── README.md             # Documentation du projet
🔧 Fonctionnalités Clés
Ajout d'Entrées
Formulaire intuitif avec validation
Listes déroulantes pour les postes comptables et natures de sinistres
Génération automatique de documents Word
Analyse Statistique
Calculs automatiques des métriques statistiques
Génération de graphiques en temps réel
Visualisations interactives avec matplotlib et seaborn
🎓 Contexte du Stage
Ce projet a été développé dans le cadre d'un stage de découverte, permettant de :

Découvrir le développement web avec Flask
Apprendre la gestion des bases de données MySQL
S'initier à l'analyse de données avec Python
Comprendre les principes du développement d'applications métier
📝 Améliorations Possibles
 Authentification et gestion des utilisateurs
 Interface d'administration pour la gestion des référentiels
 Export des données en différents formats (CSV, Excel)
 Tableau de bord avec indicateurs en temps réel
 API REST pour l'intégration avec d'autres systèmes
 Tests unitaires et fonctionnels
🤝 Contribution
Les contributions sont les bienvenues ! N'hésitez pas à :

Signaler des bugs
Proposer des améliorations
Soumettre des pull requests
📧 Contact
Pour toute question ou suggestion concernant ce projet de stage, n'hésitez pas à me contacter.

Développé avec ❤️ dans le cadre d'un stage de découverte

