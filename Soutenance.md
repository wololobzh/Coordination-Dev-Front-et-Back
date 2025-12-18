# Soutenance finale du projet – Plateforme de gestion d’événements

Cette soutenance finale a pour objectif d’évaluer la maîtrise globale du projet, la capacité du groupe à concevoir, développer, déployer et maintenir une application web complète, ainsi que la qualité professionnelle de la démarche technique et organisationnelle.

Le projet évalué est la plateforme de gestion d’événements TopEvent, composée d’un front-end SPA et d’un back-end API REST, déployés et accessibles en ligne.

---

## Durée et organisation de la soutenance

### Durée totale : 75 minutes (présentation en groupe)

* 45 minutes de présentation et démonstration
* 30 minutes de questions-réponses

La soutenance est collective (groupe de 5 personnes).
Chaque membre du groupe doit prendre la parole et présenter une partie clairement identifiée du projet.

---

## Répartition attendue de la parole

La répartition ci-dessous est indicative. Elle peut être adaptée, à condition que tous les aspects du projet soient couverts.

| Membre | Thématique principale                              |
| ------ | -------------------------------------------------- |
| 1      | Conception, cadrage, besoins, use cases            |
| 2      | Architecture globale et choix techniques           |
| 3      | Back-end, API, base de données, sécurité           |
| 4      | Front-end, UX, gestion d’état, intégration API     |
| 5      | Docker, environnements, CI/CD, DevOps, déploiement |

---

## Structure attendue de la présentation (45 minutes)

### 1. Introduction et contexte (5 minutes)

Objectif : poser le cadre du projet.

* Présentation générale du projet TopEvent
* Problématique métier adressée
* Publics cibles (visiteurs, utilisateurs, administrateurs)
* Objectifs fonctionnels et pédagogiques
* Organisation de l’équipe et répartition front/back

---

### 2. Conception et cadrage du projet (7 minutes)

Objectif : démontrer une démarche de conception structurée.

À présenter :

* Analyse du besoin initial
* Identification des acteurs et des use cases clés
* Gestion des rôles et des permissions
* Choix d’une architecture front/back découplée
* Définition du contrat d’API (routes, payloads, statuts HTTP)
* Versionnement de l’API (/api/v1)

Les choix doivent être justifiés.

---

### 3. Architecture technique globale (7 minutes)

Objectif : montrer une vision d’ensemble cohérente du système.

À détailler :

* Schéma d’architecture globale
* Séparation des responsabilités

  * Front-end (SPA)
  * Back-end (API REST)
  * Base de données
* Communication front/back (HTTP, JSON, JWT)
* Gestion des environnements (développement, production)

---

### 4. Back-end et API (8 minutes)

Objectif : démontrer la solidité et la qualité du socle serveur.

À aborder :

* Technologies utilisées (Node.js / Express ou Django REST)
* Structure du projet back-end
* Modélisation de la base de données
* Endpoints principaux (authentification, événements, inscriptions)
* Authentification et autorisation (JWT, rôles)
* Sécurité

  * Hash des mots de passe
  * Validation des entrées
  * Gestion des erreurs
  * CORS
* Documentation Swagger / OpenAPI
* Tests back-end (unitaires et intégration)

---

### 5. Front-end et expérience utilisateur (8 minutes)

Objectif : évaluer la qualité de l’interface et de l’intégration avec l’API.

À présenter :

* Framework utilisé (React ou autre)
* Architecture des composants
* Routing
* Gestion de l’état global
* Communication avec l’API
* Gestion de l’authentification côté client
* Parcours utilisateur et UX
* Gestion des erreurs et des états de chargement
* Responsive design
* Tests front-end (si présents)

---

### 6. Docker, environnements et DevOps (5 minutes)

Objectif : démontrer une approche professionnelle et industrialisée.

À détailler :

* Intérêt de Docker dans le projet
* Conteneurisation du front-end et du back-end
* Dockerfile (principes et bonnes pratiques)
* Docker Compose (services, réseaux, volumes)
* Gestion des variables d’environnement (.env)
* Séparation des environnements (dev / prod)

---

### 7. CI/CD, déploiement et démonstration (5 minutes)

Objectif : prouver que le projet fonctionne réellement en conditions proches de la production.

À présenter et démontrer :

* Pipeline CI/CD

  * Lint
  * Tests
  * Build
  * Déploiement
* Outils utilisés (GitHub Actions ou équivalent)
* Accès à l’application déployée
* Démonstration fonctionnelle

  * Navigation visiteur
  * Authentification utilisateur
  * Inscription à un événement
  * Interface administrateur
* Accès aux dépôts GitHub

La démonstration doit être fluide et préparée.

---

## Questions – Réponses (30 minutes)

Les questions viseront à évaluer la compréhension approfondie du projet et la capacité à prendre du recul.

### Conception et architecture

* Pourquoi avoir choisi une architecture découplée ?
* Quels seraient les impacts d’une montée en charge ?
* Quelles alternatives techniques étaient possibles ?

### Back-end et API

* Fonctionnement précis du JWT
* Gestion des erreurs et des statuts HTTP
* Évolution et versionnement de l’API
* Sécurisation supplémentaire possible

### Front-end

* Choix de la gestion d’état
* Sécurité côté client
* Performances et optimisation

### Docker, DevOps et déploiement

* Différence entre image et conteneur
* Rôle de Docker Compose
* Gestion des secrets et variables sensibles
* Processus de mise à jour en production

### Vision produit et évolutions

* Améliorations fonctionnelles possibles
* Industrialisation supplémentaire
* Passage à l’échelle (scalabilité, monitoring, logs)

---

## Rappels importants

* Le temps est strict : 45 minutes de présentation, puis questions.
* Tous les membres du groupe doivent intervenir.
* L’application, l’API et les dépôts doivent être accessibles le jour de la soutenance.
* Le README et la documentation Swagger seront consultés.
* L’évaluation porte autant sur la compréhension que sur le résultat final.

---

## Objectif final de la soutenance

Montrer que vous êtes capables, en équipe, de :

* Concevoir une application web complète
* Mettre en place une architecture propre et maintenable
* Développer un front-end et un back-end coordonnés
* Gérer les environnements et la configuration
* Conteneuriser et déployer un projet
* Mettre en place une démarche DevOps cohérente
* Présenter et défendre vos choix techniques de manière professionnelle

