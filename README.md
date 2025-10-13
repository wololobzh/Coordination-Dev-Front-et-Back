# Plateforme de gestion d’événements avec API partagée

---

## **1. Contexte du projet**

Les organisations, écoles ou entreprises doivent souvent gérer la création, la publication et la gestion d’événements : conférences, ateliers, formations, séminaires, webinaires, etc.
Ce projet vise à développer une **application web complète** permettant :

* aux **administrateurs** de publier et gérer des événements,
* aux **utilisateurs** de consulter et s’inscrire à ces événements,
* et à l’équipe projet de **coordonner efficacement le développement du front-end et du back-end**.

L’objectif pédagogique est de simuler un environnement de production où plusieurs équipes doivent collaborer autour d’une architecture distribuée et d’interfaces clairement définies.

---

## **2. Objectifs pédagogiques**

À l’issue du projet, vous serez capables de :

1. Concevoir une architecture **front/back découplée et cohérente**.
2. **Définir, documenter et implémenter une API RESTful** claire et maintenable.
3. **Collaborer efficacement** entre équipes front et back grâce à une communication structurée (contrats d’API, versioning, outils).
4. Mettre en place un **pipeline CI/CD** pour automatiser les tests, la validation et le déploiement.
5. Garantir la **qualité du code, la sécurité et la performance** de l’application.
6. Documenter et présenter votre solution de manière professionnelle.

---

## **3. Description générale**

L’application doit permettre de :

* **Lister** les événements publics à venir,
* **Afficher** le détail d’un événement,
* **Permettre** à un utilisateur connecté de s’y inscrire,
* **Gérer** les événements et utilisateurs côté administrateur.

Les deux couches de l’application devront être **parfaitement séparées** :

* Le **Front-end** (SPA – Single Page Application) consommera uniquement l’API.
* Le **Back-end** (API RESTful) gérera la logique métier et les accès à la base de données.

---

## **4. Rôles et responsabilités**

| Rôle               | Description                 | Accès                                                          |
| ------------------ | --------------------------- | -------------------------------------------------------------- |
| **Visiteur**       | Utilisateur non connecté    | Consultation des événements publics                            |
| **Utilisateur**    | Utilisateur authentifié     | Inscription / désinscription à un événement, gestion du profil |
| **Administrateur** | Gestion complète du contenu | CRUD complet sur événements et utilisateurs                    |

---

## **5. Fonctionnalités à implémenter**

### **A. Fonctionnalités utilisateur**

* Consulter la **liste des événements publics**.
* Filtrer les événements par **catégorie, date ou lieu**.
* Voir le **détail complet d’un événement** (description, image, date, lieu, capacité).
* Créer un **compte utilisateur** (inscription).
* Se **connecter / déconnecter** (JWT).
* S’inscrire ou se désinscrire à un événement.
* Consulter la **liste de ses inscriptions** dans un espace personnel.
* Modifier son profil (nom, email, mot de passe).

### **B. Fonctionnalités administrateur**

* Créer, modifier ou supprimer un événement.
* Définir la **capacité maximale** et la **visibilité** (public/privé).
* Publier / dépublier un événement.
* Consulter la liste des inscrits à chaque événement.

### **C. Fonctionnalités bonus**

* Notification email lors d’une inscription ou d’une annulation.
* Upload d’image pour un événement.
* Pagination et recherche par mot-clé.

---

## **6. Liste complète des Use Cases**

| ID   | Titre du use case                 | Acteur         | Description                                                            |
| ---- | --------------------------------- | -------------- | ---------------------------------------------------------------------- |
| UC01 | Consulter la liste des événements | Visiteur       | Le visiteur accède à la page listant les événements publics.           |
| UC02 | Filtrer les événements            | Visiteur       | Il applique un filtre par catégorie, date ou lieu.                     |
| UC03 | Voir le détail d’un événement     | Visiteur       | Il consulte la fiche détaillée d’un événement.                         |
| UC04 | Créer un compte utilisateur       | Visiteur       | Le visiteur crée un compte pour s’inscrire à des événements.           |
| UC05 | Se connecter                      | Utilisateur    | L’utilisateur s’authentifie pour accéder à son espace.                 |
| UC06 | Modifier son profil               | Utilisateur    | L’utilisateur met à jour ses informations personnelles.                |
| UC07 | S’inscrire à un événement         | Utilisateur    | L’utilisateur s’inscrit à un événement si des places sont disponibles. |
| UC08 | Se désinscrire d’un événement     | Utilisateur    | L’utilisateur retire sa participation avant la date limite.            |
| UC09 | Consulter ses inscriptions        | Utilisateur    | L’utilisateur consulte les événements auxquels il participe.           |
| UC10 | Créer un événement                | Administrateur | L’administrateur ajoute un nouvel événement.                           |
| UC11 | Modifier un événement             | Administrateur | L’administrateur met à jour les informations d’un événement.           |
| UC12 | Supprimer un événement            | Administrateur | L’administrateur supprime un événement.                                |
| UC13 | Publier / Dépublier un événement  | Administrateur | L’administrateur contrôle la visibilité publique.                      |
| UC14 | Consulter les inscrits            | Administrateur | L’administrateur visualise la liste des participants.                  |

---

## **7. Contraintes techniques**

### **Back-end**

* Langage : **Node.js (Express)** ou **Python (Django REST Framework)**
* Base de données : **PostgreSQL** ou **MongoDB**
* Architecture RESTful et versionnée (`/api/v1/...`)
* Authentification **JWT** (login/logout)
* ORM : Sequelize / Prisma / Django ORM
* Documentation : **Swagger / OpenAPI** obligatoire
* Tests unitaires et d’intégration (Jest, Pytest, etc.)
* Respect du CORS pour la communication avec le front

### **Front-end**

* Framework : **React** (ou Vue.js / Angular)
* Gestion d’état : Redux Toolkit / Zustand / Pinia
* Appels API via Axios ou Fetch
* Routing : React Router
* Interface responsive et claire
* Tests : React Testing Library ou Cypress

### **CI/CD**

* Utilisation de **Git** avec branches séparées (`frontend`, `backend`, `main`)
* Intégration continue via **GitHub Actions** ou **GitLab CI**
* Étapes automatiques : lint + tests + build
* Déploiement possible sur n'importe quels VPS. Le formateur testera sur un VPS OVH.
* Conteneurisation avec **Docker**

---

## **8. Organisation du projet**

| Phase                             | Objectif                                          | Livrables                         | 
| --------------------------------- | ------------------------------------------------- | --------------------------------- |
| **Phase 1 : Cadrage**             | Définition des rôles, architecture, GANTT, outils et API | Cahier des charges + schéma d’API |
| **Phase 2 : Développement**       | Développement parallèle front / back              | Code source propre + doc Swagger  |
| **Phase 3 : Intégration & tests** | Intégration complète + pipeline CI/CD             | Version stable + rapport de tests |
| **Phase 4 : Soutenance**          | Présentation du projet et démo                    | Présentation orale + support PDF  |

---

## **9. Livrables attendus**

* **Dépôt Git complet** (frontend + backend) avec README détaillé.
* **Documentation technique** (API, installation, exécution).
* **Documentation utilisateur** (usage basique, captures).
* **Lien vers la version déployée** (front + back).
* **Support de présentation pour la soutenance**.

---

## **10. Évaluation**

| Critère                                  | Détails                                   | Pondération |
| ---------------------------------------- | ----------------------------------------- | ----------- |
| **Respect des fonctionnalités**          | Conformité aux use cases                  | 25 %        |
| **Qualité du code et de l’architecture** | Structure, propreté, cohérence            | 25 %        |
| **Documentation**                        | Swagger, README, guide d’installation     | 15 %        |
| **CI/CD & tests**                        | Automatisation, couverture minimale       | 15 %        |
| **Coordination front/back**              | Communication, intégration, gestion API   | 10 %        |
| **Présentation / soutenance**            | Clarté, maîtrise technique, démonstration | 10 %        |

---

## **11. Ressources recommandées**

* [React Documentation](https://react.dev)
* [Express.js](https://expressjs.com/) / [Django REST Framework](https://www.django-rest-framework.org/)
* [Swagger Editor](https://editor.swagger.io/)
* [GitHub Actions](https://docs.github.com/actions)
* [Docker Getting Started](https://docs.docker.com/get-started/)

---

## **12. Conseils de réussite**

* **Définissez l’API dès le départ** : le contrat d’échange est la clé du projet.
* **Synchronisez régulièrement vos branches front/back**.
* **Testez vos endpoints isolément** (Postman / Insomnia) avant d’intégrer.
* **Versionnez vos données et vos routes** pour éviter les incohérences.
* **Documentez tout** : l’oubli de la doc est pénalisé.
* Une intégration propre vaut mieux qu’une surenchère de fonctionnalités non terminées.
