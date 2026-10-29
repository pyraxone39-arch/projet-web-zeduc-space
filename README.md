# 🍔 Projet de développement web : ZeDuc@Space — Mon Miam Miam

![Laravel](https://img.shields.io/badge/Laravel-12.70-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?style=for-the-badge&logo=php&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.0-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

**ZeDuc@Space** est une plateforme web centralisée et complète développée pour la gestion de la restauration étudiante au sein du campus de l'Institut Ucac-Icam. Elle permet de fluidifier la prise de commande, d'intégrer des paiements mobiles (Mobile Money) et d'animer la vie étudiante via un programme de fidélité et de parrainage, tout en offrant un back-office complet pour le personnel.

## ✨ Fonctionnalités Principales de la Plateforme

- **Espace Étudiant (Client) :** 
  * Consultation du catalogue complet, des menus et des plats du jour.
  * Prise de commande en ligne avec gestion avancée du panier.
  * Programme de fidélité automatisé (1 point crédité uniquement à la livraison effective de la commande).
  * Système de parrainage avec codes uniques.
  * Suivi des commandes en temps réel et module de dépôt de réclamations.
- **Espace Employé (Cuisine & Comptoir) :** 
  * Suivi et gestion du cycle de vie des commandes en direct (En attente ➔ En préparation ➔ Prête ➔ Livrée/Terminée).
  * Gestion rapide de la disponibilité des plats (mise en rupture de stock en un clic).
- **Espace Administration (Back-Office) :** 
  * Gestion complète du catalogue (Création/Modification des Plats, Catégories, Prix).
  * Planification et publication des événements et promotions du campus (avec affichage conditionnel selon la date).
  * Traitement des réclamations étudiantes.
- **Classement Dynamique :** Affichage en temps réel d'un Top 10 des clients les plus fidèles (filtrable par jour, semaine, mois).

## 🛠️ Stack Technique

- **Backend :** PHP 8.2, Laravel 12 (Architecture MVC)
- **Frontend :** Laravel Blade, Bootstrap 5.0.2, Bootstrap Icons
- **Base de données :** MySQL / MariaDB (SQLite pour les tests locaux)
- **Passerelle de paiement :** API REST CinetPay
- **Outils :** Git, Composer

> ⚠️ **Note d'intégration :** La fonctionnalité de simulation de paiement via l'API CinetPay (Orange Money / MTN MoMo) est en cours d'intégration et n'est pas encore totalement finalisée. Le paiement en espèces reste l'alternative fonctionnelle par défaut.

## 🚀 Installation & Configuration en local

### Prérequis
- PHP 8.2 ou supérieur
- Composer
- Un serveur MySQL (XAMPP, Laragon, WAMP, etc.)
- Git

### Étapes d'installation

1. **Cloner le dépôt sur votre machine locale :**
   ```bash
   git clone [https://github.com/pyraxone39-arch/projet-web-zeduc-space.git](https://github.com/pyraxone39-arch/projet-web-zeduc-space.git)
   cd backend-zeduc-space
	
2.Installer les dépendances PHP :

Bash
composer install

3.Configurer l'environnement :

4.Dupliquer le fichier d'exemple : cp .env.example .env

5.Générer la clé d'application : php artisan key:generate

6.Configurer la base de données dans le .env :

Extrait de code
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=mon_miam_miam
DB_USERNAME=root
DB_PASSWORD=

7.Préparer la base de données :

Bash
php artisan migrate:fresh --seed

8.Lancer le serveur de développement :


Sécurité et Rôles
L'application utilise les Middlewares Laravel pour isoler strictement les espaces :

role:student : Accès exclusif aux commandes et au programme de fidélité.

role:employee / role:admin : Accès au back-office de gestion.

Protection contre les failles CSRF, XSS et injections SQL nativement gérée par Laravel Eloquent.


(Projet réalisé dans le cadre de la formation à l'Institut Ucac-Icam)

Bash
php artisan serve
L'application sera accessible sur http://127.0.0.1:8000.