# Projet Web 3 - 2024-2025

*Pluquet Frédéric - HELHa*

## Description

Trouvez un film à regarder en fonction des envies de tous les membres de la famille est souvent un casse-tête. Pour résoudre ce problème, nous avons décidé de créer une application web qui permet de trouver un film en fonction de plusieurs critères.

## Fonctionnalités principales

### Inscription & Connexion

L'utilisateur peut s'inscrire sur le site web en fournissant son nom, son prénom, son adresse email et un mot de passe. Il peut aussi se connecter en fournissant son adresse email et son mot de passe.

### Groupe familial

L'utilisateur peut créer un groupe familial en fournissant un nom pour le groupe et en invitant d'autres utilisateurs à rejoindre le groupe. Il peut aussi rejoindre un groupe familial.

### Recherche d'un film

Quand un utilisateur est connecté, le site web sera divisé en 2 grandes parties :
- la sélection de ses films préférés;
- la recherche d'un film en fonction des critères de son groupe familial.

### Sélection de ses films préférés

Le site web choisira une liste de films populaires et les affichera à l'utilisateur par une interface proche de celle de Tinder. Pour chaque film, le site web affichera une image, le titre du film, la date de sortie, le genre, le résumé, la note moyenne et le nombre de votes.

 L'utilisateur pourra swiper à droite pour dire qu'il aime le film et à gauche pour dire qu'il ne l'aime pas. Il peut aussi indiquer qu'il a déjà vu le film. Les informations sur les films seront récupérées à partir de l'API The Movie Database. 

Chaque membre du groupe familial devra faire cela pour établir ses propres préférences. Le site web proposera un ensemble de films limités à ceux qui ont été aimés par au moins un membre du groupe familial et complètera avec des films populaires une fois la liste épuisée.

### Recherche d'un film en fonction des critères de son groupe familial

Une fois que chaque membre du groupe familial a établi ses préférences, un des membres du groupe familial pourra demander de voir les films qui correspondent aux critères de tous les membres du groupe familial présents (une sélection peut être faite facimlement). Si aucun film ne correspond complètement, le site web proposera une liste de films qui correspond aux critères du plus grand nombre de membres du groupe familial.

Les films seront triés par ordre de pertinence. Pour chaque film, le site web affichera une image, le titre du film, la date de sortie, le genre, le résumé, la note moyenne et le nombre de votes. L'utilisateur pourra swiper à droite pour dire qu'il veut regarder le film et à gauche pour dire qu'il ne veut pas le regarder.

S'il swipe sur la droite, le film sera alors ajouté à l'historique de l'utilisateur et marqué comme vu pour les autres membres du groupe familial.


## Fonctionnalités supplémentaires

### Gestion des groupes familiaux

Un utilisateur peut quitter un groupe familial. Un utilisateur peut aussi supprimer un groupe familial s'il en est le créateur. On peut faire partie de plusieurs groupes familiaux.

### Gestion des préférences

Un utilisateur peut modifier son profile et ses préférences à tout moment. Il peut par exemple indiquer s'il aime certains genres de films, s'il aime revoir des films qu'il a déjà vu, quels sont les fournisseurs de streaming qu'il utilise, etc.

### Notifications

Un utilisateur peut recevoir des notifications pour l'inviter à rejoindre un groupe familial, pour lui indiquer qu'un membre du groupe familial a rejoint le groupe, pour lui indiquer qu'un film a été trouvé, etc.

Une notification peut être également envoyée quand cela fait plus de 7 jours qu'un utilisateur n'a pas utilisé l'application pour lui rappeler de revenir.

### Historique

Un utilisateur peut consulter l'historique des films qu'il a aimé et des films qu'il a vu. Il peut aussi consulter l'historique des films vus par les membres du groupe familial.


### Emails

Un email sera envoyé à l'utilisateur pour confirmer son inscription. 

Un email sera envoyé à l'utilisateur pour l'inviter à rejoindre un groupe familial. 

Un email sera envoyé à l'utilisateur quand de nouveaux films qui pourraient lui plaire sont disponibles.

Un email sera envoyé à l'utilisateur pour lui rappeler de revenir sur l'application s'il n'a pas utilisé l'application depuis plus de 14 jours.

### Offline

L'application doit fonctionner en mode déconnecté pour revoir tout l'historique. Le reste de l'application n'est pas disponible en mode déconnecté.

### Suppression du compte

Un utilisateur peut supprimer son compte. Toutes les données de l'utilisateur seront supprimées de la base de données.

### Internationalisation

L'application doit être disponible en français et en anglais. L'utilisateur peut choisir la langue de l'application dans son profile.

### Dark mode

L'utilisateur peut choisir d'utiliser l'application en mode sombre ou en mode clair.

### Séries

L'utilisateur peut choisir de regarder des séries au lieu de films. Les séries seront affichées de la même manière que les films.

## Technologies

- Frontend : *React*
    - Client HTTP : *Axios*
    - Router : *React Router*
    - *Architecture claire avec des composants réutilisables et des contextes pour gérer les données*
    - Design : *Uniquement en SASS*. Utilisez une librairie de composants React (Material-UI, Ant Design, etc.), ou Bootstrap, ou Tailwind CSS, ...
    - Tout en *TypeScript* pour la partie React
    - *Bonne gestion des erreurs (surtout liées à l'API)*
- Backend : *Node.js avec Express*
    - Base de données : *MongoDB ou MariaDB*
    - Avec Object Relational Mapping (ORM) : *Mongoose ou TypeORM* 
    - API : *The Movie Database (TMDB)*. *La clé de l'API sera stockée dans un fichier .env et ne sera pas déposé sur le git. La clé ne sera jamais envoyée au client. Notre client discutera avec notre serveur qui lui-même parlera avec l'API de TMDB. Vous vieillerez également à ne pas faire de requêtes vers TMDB quand cela n'est pas nécessaire : mettez en cache (en base de données ou autres) les résultats pour ne plus les redemander.*
    - Authentification : *JSON Web Token (JWT)*
    - Tout en *TypeScript*
- Versionning : *GitHub*
- Déploiement : 
    - *sur votre propre serveur*
    - *automatiquement via des GitHub Actions*
- Tests :
    - En *TypeScript*
    - Tests unitaires : Jest
    - Tests d'intégration : Jest
    - Tests end-to-end : *Cypress*
- Documentation : 
    - En *Markdown* (pas de pdf ou autre).
    - *Elle doit être lisible directement sur GitHub.*
    - *Dans le dossier `docs` à la racine du projet, la documentation technique doit permettre de comprendre comment installer et utiliser l'application.*
    - *Dans le dossier `teams` à la racine du projet, la documentation SCRUM va décrire ce que chaque sprint a apporté au projet (ce qui a été réalisé, ce qui n'a pas été réalisé, ce qui a été reporté, etc.).* 
- Sécurité :
    - Protection contre les attaques *XSS* et *CSRF*
    - Protection contre les *injections SQL*

Tout se qui est en *italique* est obligatoire. Tout ce qui n'est pas en gras est optionnel. Vous pouvez ajouter d'autres technologies si vous le souhaitez.
    
## Equipe 

- Vous devrez travailler en équipe de 2 ou 3 personnes. Vous devrez utiliser GitHub pour gérer votre projet. Vous devrez utiliser des branches pour travailler sur des fonctionnalités différentes. Vous pouvez utiliser des pull requests pour fusionner vos branches. Vous devrez utiliser des issues pour gérer les tâches à réaliser.

- Chaque membre de l'équipe devra participer à la rédaction de la documentation. La documentation sera rédigée en Markdown et sera stockée dans le dossier `docs` à la racine du projet.
- Chaque membre de l'équipe devra participer à la rédaction des tests. Les tests seront écrits en TypeScript et seront stockés dans le dossier `tests` à la racine du projet.


## Planning

- Le projet a commencé le 3 octobre 2024 et se terminera le 20 décembre 2024.
- Le projet va être découpé en 4 sprints de 2 semaines.
- Chaque sprint commencera par une réunion de planification et se terminera par une réunion de revue et de rétrospective. Le professeur prendra un code d'une équipe au hasard pour le corriger. Il pourra poser des questions sur l'utilisation de GitHub, des branches, des pull requests, des issues, des tests, de la documentation, etc.
- Chaque membre de l'équipe devra travailler sur une tâche à la fois. Les tâches seront distribuées équitablement entre les membres de l'équipe et devront être réalisées dans le sprint en cours. Si une tâche n'est pas terminée à la fin du sprint, elle sera reportée au sprint suivant. Toutes les tâches seront notées sur le tableau de bord (de GitHub ou autres).
- Vos points seront calculés en fonction de la quantité et de la qualité de votre travail. Vous devrez respecter les délais et les consignes pour obtenir des points. Vous devrez aussi participer activement aux réunions de planification, de revue et de rétrospective pour obtenir des points.
- Votre présence est donc obligatoire à toutes les séances de cours. Si vous ne pouvez pas être présent à une séance, vous devrez prévenir à l'avance et vous devrez rattraper le travail manqué.
- Afin de noter au mieux chaque membre de l'équipe, vous devrez utiliser des branches pour travailler sur des fonctionnalités différentes. Vous pourrez être interrogés sur l'utilisation de ces outils lors de la revue de projet.


### *Bon travail !*
