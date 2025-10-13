## 🎓 **Projet encadré – Coordination développement Front & Back**

### **Plateforme de gestion d’événements avec API partagée**

---

### 🧩 **1. Contexte général**

Les entreprises, écoles et associations organisent régulièrement des événements (conférences, ateliers, séminaires, hackathons, webinaires…).
Ce projet a pour objectif de concevoir et développer une **application web moderne** permettant :

* la **publication et gestion d’événements** par les administrateurs,
* l’**inscription et la consultation** d’événements par les utilisateurs,
* une **communication fluide entre le front-end et le back-end**, à travers une **API documentée et sécurisée**.

Le projet est à réaliser en **binômes ou trinômes**, avec une répartition claire :

* 1 à 2 développeurs **Front-End**
* 1 à 2 développeurs **Back-End**

Les étudiants devront **collaborer étroitement** pour définir, implémenter et tester les points d’échange entre les deux couches.

---

### 🎯 **2. Objectifs pédagogiques**

À la fin du projet, les apprenants seront capables de :

1. **Concevoir une architecture front/back cohérente** et découplée.
2. **Définir, documenter et implémenter une API RESTful**.
3. **Organiser la collaboration entre équipes front et back** (versioning, communication, test d’intégration).
4. **Mettre en place un pipeline CI/CD** (lint, tests, build, déploiement).
5. **Rédiger une documentation technique et utilisateur claire**.
6. **Présenter et justifier les choix techniques** lors de la soutenance.

---

### 🧱 **3. Architecture cible**

#### 3.1. Vision générale

```
[Frontend SPA] <-----> [API REST Backend] <-----> [Database]
     (React)                 (Express / Django)         (PostgreSQL)
```

* Les deux couches communiquent uniquement via l’API.
* L’API est **documentée (Swagger)** et **versionnée** (`/api/v1/...`).
* Le déploiement peut se faire sur des plateformes gratuites (Vercel, Render, Railway, etc.).

---

### 🧩 **4. Spécifications fonctionnelles**

#### 4.1. Rôles utilisateurs

| Rôle                    | Description                 | Accès                                                          |
| ----------------------- | --------------------------- | -------------------------------------------------------------- |
| **Visiteur**            | Utilisateur non connecté    | Consultation d’événements publics                              |
| **Utilisateur inscrit** | Utilisateur authentifié     | Inscription / désinscription à un événement, gestion du profil |
| **Administrateur**      | Gestion complète du contenu | CRUD complet sur événements et utilisateurs                    |

---

#### 4.2. Fonctionnalités principales

##### **A. Gestion des événements (Administrateur)**

* Créer un nouvel événement : titre, description, lieu, date/heure, capacité, image, visibilité (public/privé).
* Modifier ou supprimer un événement.
* Voir la liste des participants.
* Publier ou dépublier un événement.

##### **B. Consultation (Tous utilisateurs)**

* Afficher la liste des événements à venir.
* Filtrer/sélectionner les événements par catégorie, date, lieu.
* Voir les détails d’un événement (description, organisateur, nombre de places restantes).

##### **C. Inscriptions (Utilisateur connecté)**

* S’inscrire à un événement si des places sont disponibles.
* Se désinscrire d’un événement avant sa date.
* Consulter la liste de ses inscriptions dans son espace personnel.

##### **D. Gestion du compte utilisateur**

* Créer un compte (nom, email, mot de passe).
* Se connecter / se déconnecter (JWT).
* Modifier son profil (nom, avatar, mot de passe).
* Supprimer son compte (optionnel).

##### **E. Notifications (bonus / optionnel)**

* Envoyer un email de confirmation d’inscription.
* Avertir les participants si un événement est modifié ou annulé.

---

### 🧾 **5. Liste exhaustive des Use Cases (UML simplifié)**

| ID   | Titre du use case                 | Acteur         | Description                                                       |
| ---- | --------------------------------- | -------------- | ----------------------------------------------------------------- |
| UC01 | Consulter la liste des événements | Visiteur       | Le visiteur consulte la page listant les événements publics.      |
| UC02 | Filtrer les événements            | Visiteur       | Le visiteur applique un filtre (par date, catégorie ou lieu).     |
| UC03 | Voir le détail d’un événement     | Visiteur       | Le visiteur consulte la fiche d’un événement sélectionné.         |
| UC04 | Créer un compte utilisateur       | Visiteur       | Le visiteur crée un compte via un formulaire.                     |
| UC05 | Se connecter                      | Utilisateur    | L’utilisateur s’authentifie via JWT et accède à son espace.       |
| UC06 | Modifier son profil               | Utilisateur    | L’utilisateur met à jour ses informations personnelles.           |
| UC07 | S’inscrire à un événement         | Utilisateur    | L’utilisateur inscrit son compte à un événement public.           |
| UC08 | Se désinscrire d’un événement     | Utilisateur    | L’utilisateur retire sa participation.                            |
| UC09 | Consulter ses inscriptions        | Utilisateur    | L’utilisateur voit la liste des événements auxquels il participe. |
| UC10 | Créer un événement                | Administrateur | L’administrateur crée un nouvel événement via un formulaire.      |
| UC11 | Modifier un événement             | Administrateur | L’administrateur met à jour les informations d’un événement.      |
| UC12 | Supprimer un événement            | Administrateur | L’administrateur supprime un événement.                           |
| UC13 | Consulter les inscrits            | Administrateur | L’administrateur voit la liste des participants.                  |
| UC14 | Publier/Dépublier un événement    | Administrateur | L’administrateur contrôle la visibilité publique.                 |

---

### 🧰 **6. Contraintes techniques**

#### 6.1. Backend

* **Langage** : Node.js (Express) ou Python (Django REST Framework).
* **Base de données** : PostgreSQL ou MongoDB.
* **Architecture RESTful**, avec versioning des endpoints.
* **Authentification JWT** (login/logout).
* **ORM** : Sequelize / Prisma / Django ORM.
* **Validation des données** : Joi, Pydantic ou équivalent.
* **Documentation Swagger** générée automatiquement.
* **Tests unitaires & d’intégration** (Jest ou Pytest).

#### 6.2. Frontend

* **Framework** : React (ou Vue.js / Angular).
* **Gestion d’état** : Redux Toolkit, Zustand ou Pinia.
* **Appels API** via Axios ou Fetch.
* **Routing** avec React Router.
* **UI responsive** (Material UI, Tailwind ou Bootstrap).
* **Tests** : React Testing Library ou Cypress.

#### 6.3. CI/CD

* **Git obligatoire** : branches “frontend” / “backend” + PR fusionnées après revue.
* **CI/CD** : GitHub Actions (lint + test + build).
* **Conteneurisation (bonus)** : Dockerfile pour chaque service.
* **Déploiement** : Vercel (front) + Render/Railway (back).

---

### 📦 **7. Livrables attendus**

| Phase                 | Livrables                                                     | Format attendu           |
| --------------------- | ------------------------------------------------------------- | ------------------------ |
| Phase 1 – Cadrage     | Cahier des charges, schéma d’API, diagramme de données        | Markdown / PDF           |
| Phase 2 – Dev         | Code source structuré, documentation Swagger, scripts init DB | Dépôt Git                |
| Phase 3 – Intégration | Version stable + logs CI/CD + tests                           | Dépôt Git / Lien déployé |
| Phase 4 – Soutenance  | Démo live + présentation technique (10-15 min)                | Support PDF ou slides    |

---

### 🧮 **8. Évaluation détaillée**

| Critère                                  | Description                                                | Pondération |
| ---------------------------------------- | ---------------------------------------------------------- | ----------- |
| **Fonctionnalités livrées**              | Respect des use cases, fonctionnement global               | 25 %        |
| **Qualité du code et de l’architecture** | Lisibilité, modularité, cohérence des API                  | 25 %        |
| **Documentation**                        | Swagger complet, README clair, instructions d’installation | 15 %        |
| **CI/CD et tests**                       | Pipeline opérationnel + couverture de tests minimale       | 15 %        |
| **Coordination front/back**              | Communication, versioning, intégration fluide              | 10 %        |
| **Soutenance**                           | Clarté, justification des choix, démonstration             | 10 %        |
