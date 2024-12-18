# Projet Web 3 - 2024-2025

*Pluquet Frédéric - HELHa*

## Description

Trouver un film à regarder en fonction des envies de tous les membres de la famille est souvent un casse-tête. Pour résoudre ce problème, nous avons décidé de créer une application web qui permet de trouver un film en fonction de plusieurs critères.

## Fonctionnalités principales

### Inscription & Connexion

L'utilisateur peut s'inscrire sur le site web en fournissant son nom, son prénom, son adresse email et un mot de passe. Il peut aussi se connecter en fournissant son adresse email et son mot de passe. Il peut également choisir les fournisseurs de streaming qu'il utilise.

### Groupe familial

L'utilisateur peut créer un groupe familial en fournissant un nom pour le groupe et en invitant d'autres utilisateurs à rejoindre le groupe. Il peut aussi rejoindre un groupe familial.

### Recherche d'un film

Quand un utilisateur est connecté, le site web sera divisé en 2 grandes parties :
- la sélection de ses films préférés;
- la recherche d'un film en fonction des critères de son groupe familial.

### Sélection de ses films préférés

Le site web choisira une liste de films populaires et les affichera à l'utilisateur par une interface proche de celle de Tinder. Pour chaque film, le site web affichera une image, le titre du film, la date de sortie, le genre, le résumé, la note moyenne et le nombre de votes.

L'utilisateur pourra swiper à droite pour dire qu'il aime le film et à gauche pour dire qu'il ne l'aime pas. Il peut aussi indiquer qu'il a déjà vu le film. Les informations sur les films seront récupérées à partir de l'API The Movie Database.

Chaque membre du groupe familial devra faire cela pour établir ses propres préférences. Le site web proposera un ensemble de films limités à ceux qui ont été aimés par au moins un membre du groupe familial et complétera avec des films populaires une fois la liste épuisée.

### Recherche d'un film en fonction des critères de son groupe familial

Une fois que chaque membre du groupe familial a établi ses préférences, un des membres du groupe familial pourra demander de voir les films qui correspondent aux critères de tous les membres du groupe familial présents (une sélection peut être faite facilement). Si aucun film ne correspond complètement, le site web proposera une liste de films qui correspond aux critères du plus grand nombre de membres du groupe familial.

Les films seront triés par ordre de pertinence. Pour chaque film, le site web affichera une image, le titre du film, la date de sortie, le genre, le résumé, la note moyenne et le nombre de votes. L'utilisateur pourra swiper à droite pour dire qu'il veut regarder le film et à gauche pour dire qu'il ne veut pas le regarder.

S'il swipe sur la droite, le film sera alors ajouté à l'historique de l'utilisateur et marqué comme vu pour les autres membres du groupe familial.

### Gestion des préférences

Un utilisateur peut modifier son profil et ses préférences à tout moment. Il peut par exemple indiquer s'il aime certains genres de films, s'il aime revoir des films qu'il a déjà vus, quels sont les fournisseurs de streaming qu'il utilise, etc.

## Fonctionnalités supplémentaires

### Gestion des groupes familiaux

Un utilisateur peut quitter un groupe familial. Un utilisateur peut aussi supprimer un groupe familial s'il en est le créateur. On peut faire partie de plusieurs groupes familiaux.

### Notifications

Un utilisateur peut recevoir des notifications pour l'inviter à rejoindre un groupe familial, pour lui indiquer qu'un membre du groupe familial a rejoint le groupe, pour lui indiquer qu'un film a été trouvé, etc.

Une notification peut être également envoyée quand cela fait plus de 7 jours qu'un utilisateur n'a pas utilisé l'application pour lui rappeler de revenir.

### Historique

Un utilisateur peut consulter l'historique des films qu'il a aimés et des films qu'il a vus. Il peut aussi consulter l'historique des films vus par les membres du groupe familial.

### Emails

Un email sera envoyé à l'utilisateur pour confirmer son inscription. 

Un email sera envoyé à l'utilisateur pour l'inviter à rejoindre un groupe familial. 

Un email sera envoyé à l'utilisateur quand de nouveaux films qui pourraient lui plaire sont disponibles.

Un email sera envoyé à l'utilisateur pour lui rappeler de revenir sur l'application s'il n'a pas utilisé l'application depuis plus de 14 jours.

### Offline

L'application doit fonctionner en mode déconnecté pour consulter tout l'historique. Le reste de l'application n'est pas disponible en mode déconnecté.

### Suppression du compte

Un utilisateur peut supprimer son compte. Toutes les données de l'utilisateur seront supprimées de la base de données.

### Internationalisation

L'application doit être disponible en français et en anglais. L'utilisateur peut choisir la langue de l'application dans son profil.

### Dark mode

L'utilisateur peut choisir d'utiliser l'application en mode sombre ou en mode clair.

### Séries

L'utilisateur peut choisir de regarder des séries au lieu de films. Les séries seront affichées de la même manière que les films.

## Technologies

- Frontend : *React*
    - Client HTTP : *Axios*
    - Router : *React Router*
    - *Architecture claire avec des composants réutilisables et des contextes pour gérer les données*
    - Design : *Uniquement en SASS*. Utilisez une bibliothèque de composants React (Material-UI, Ant Design, etc.), ou Bootstrap, ou Tailwind CSS, ...
    - Tout en *TypeScript* pour la partie React
    - *Bonne gestion des erreurs (surtout liées à l'API)*
- Backend : *Node.js avec Express*
    - Base de données : *MongoDB ou MariaDB*
    - Avec Object Relational Mapping (ORM) : *Mongoose ou TypeORM ou Prisma*
    - API : *The Movie Database (TMDB)*. *La clé de l'API sera stockée dans un fichier .env et ne sera pas déposée sur votre dépôt Git. La clé ne sera jamais envoyée au client. Notre client communiquera avec notre serveur qui lui-même communiquera avec l'API de TMDB. Vous veillerez également à ne pas faire de requêtes vers TMDB lorsque cela n'est pas nécessaire : mettez en cache (en base de données ou ailleurs) les résultats pour ne plus les redemander.*
    - Authentification : *JSON Web Token (JWT)*
    - Tout en *TypeScript*
    - *Vous devez faire tourner au moins un processus en arrière-plan sur le serveur (par exemple pour envoyer des emails, pour envoyer des notifications, etc.) qui ne sera pas bloquant pour le serveur. Il ne fonctionnera pas sur votre serveur distant mais il doit marcher localement.*
- Versionning : *GitHub*
- Déploiement : 
    - ~~sur votre propre serveur~~
    - ~~automatiquement via des GitHub Actions ou autre~~
    - *Vous ne devez plus déployer votre application sur un serveur distant (par faute de VPS). Votre application tournera donc uniquement en local. Mais vous devez comprendre comment votre client React peut être servi par votre serveur Express, si nous devions le mettre en ligne.*
    - Si vous l'avez déjà fait, vous pouvez continuer à déployer votre application sur un serveur distant. Indiquez-le dans votre documentation et montrez comment cela fonctionne dans votre vidéo de présentation (voir plus bas). Cela pourra compter dans les points bonus.
- Tests :
    - En *TypeScript*
    - Tests unitaires : Jest
    - Tests d'intégration : Jest
    - Tests end-to-end : *Cypress (local)*
- Documentation :
    - En *Markdown* (pas de pdf ou autres).
    - *Elle doit être lisible directement sur GitHub.*
    - *Dans le dossier `docs` à la racine du projet, la documentation technique doit permettre de comprendre comment installer et utiliser l'application. Vous devez également indiquer ce qu'il faut mettre en place pour configurer les processus en arrière-plan (crontab, ...) ou autre.*
    - *Dans le dossier `teams` à la racine du projet, la documentation SCRUM va décrire ce que chaque sprint a apporté au projet (ce qui a été réalisé, ce qui n'a pas été réalisé, ce qui a été reporté, etc.).*
- Sécurité :
    - Protection contre les attaques *XSS* et *CSRF*
    - Protection contre les *injections SQL*

Toutes les fonctionnalités ne sont pas obligatoires mais l'ensemble de vos fonctionnalités doit recouvrir tout ce qui est en *italique*. Ce qui est en *italique* est donc la partie obligatoire pour ce projet. Tout ce qui n'est pas en italique est optionnel. Vous pouvez ajouter d'autres technologies si vous le souhaitez.
    
## Equipe

- Vous devrez travailler en équipe de 2 ou 3 personnes. Vous devrez utiliser GitHub pour gérer votre projet. Vous devrez utiliser des branches pour travailler sur des fonctionnalités différentes. Vous pouvez utiliser des pull requests pour fusionner vos branches. Vous devrez utiliser des issues pour gérer les tâches à réaliser.

- Chaque membre de l'équipe devra participer à la rédaction de la documentation. La documentation sera rédigée en Markdown et sera stockée dans le dossier `docs` à la racine du projet.
- Chaque membre de l'équipe devra participer à la rédaction des tests. Les tests seront écrits en TypeScript et seront stockés dans le dossier `tests` à la racine du projet.


## Planning

- Le projet a commencé le 3 octobre 2024 et se terminera le 9 janvier 2025 à 22h.
- Le projet va être découpé en 5 sprints de 2 semaines, dont voici le calendrier :

    - Sprint 1 : du 3 octobre 2024 au 17 octobre 2024
    - Sprint 2 : du 17 octobre 2024 au 7 novembre 2024
    - Sprint 3 : du 7 novembre 2024 au 28 novembre 2024 (attention à la semaine à TechnoCampus)
    - Sprint 4 : du 28 novembre 2024 au 12 décembre 2024
    - Sprint 5 : du 12 décembre 2024 au 19 décembre 2024

- Chaque sprint commencera par une réunion de planification et se terminera par une réunion de revue et de rétrospective. Le professeur prendra un code d'une équipe au hasard pour le corriger. Il pourra poser des questions sur l'utilisation de GitHub, des branches, des pull requests, des issues, des tests, de la documentation, etc.
- Chaque membre de l'équipe devra travailler sur une tâche à la fois. Les tâches seront distribuées équitablement entre les membres de l'équipe et devront être réalisées dans le sprint en cours. Si une tâche n'est pas terminée à la fin du sprint, elle sera reportée au sprint suivant. Toutes les tâches seront notées sur le tableau de bord (de GitHub ou autres).
- Vos points seront calculés en fonction de la quantité et de la qualité de votre travail. Vous devrez respecter les délais et les consignes pour obtenir des points. Vous devrez aussi participer activement aux réunions de planification, de revue et de rétrospective pour obtenir des points.
- Votre présence est donc obligatoire à toutes les séances de cours. Si vous ne pouvez pas être présent à une séance, vous devrez prévenir à l'avance et vous devrez rattraper le travail manqué.
- Afin de noter au mieux chaque membre de l'équipe, vous devrez utiliser des branches pour travailler sur des fonctionnalités différentes. Vous pourrez être interrogés sur l'utilisation de ces outils lors de la revue de projet.

## Modalité de l'examen Q1

- Vous devez remettre votre projet sur votre repository GitHub pour **le 9 janvier 2025 à 22h maximum**.
- L'application doit être fonctionnelle et respecter les fonctionnalités obligatoires. Si ce n'est pas le cas, alors l'examen ne pourra pas être réussi (mieux vaut le repasser en Q3 alors).
- Pour cette même date, vous ferrez une vidéo de présentation de votre projet (une vidéo par groupe). Vous devrez expliquer les fonctionnalités de votre application, les technologies utilisées, les difficultés rencontrées, l'architecture de votre code, etc. Vous devrez montrer votre application en fonctionnement. Vous mettrez le lien de la vidéo dans le fichier `README.md` de votre projet.
- Vous passerez un examen oral le 16 janvier 2025 par groupe. Chaque membre du groupe doit être capable d'expliquer l'ensemble du code du projet, les tests, la documentation, etc. Chaque membre devra aussi répondre à des questions sur les technologies utilisées, les choix que vous avez faits, les difficultés rencontrées, etc. Vous devez également être capable de montrer votre application en fonctionnement.
- Prenez chacun vos ordinateurs portables pour l'examen oral. Vous serez potentiellement interrogés simultanément via une application en ligne. 

## Modalité de l'examen Q3

- Si vous n'avez pas réussi à obtenir la moyenne à l'examen Q1, vous devrez remettre une version améliorée de votre projet.
- Vous pouvez continuer à travailler en équipe ou seul pour améliorer votre projet. Vous devrez remettre votre projet sur GitHub pour la date indiquée ci-dessus. Si vous n'avez pas de repository GitHub, je dois vous le créer pour vous.
- L'énoncé de projet reste le même (fonctionnalités et livrables). 
- Vous devrez également remettre une documentation expliquant les améliorations que vous avez apportées à votre projet.
- Vous devrez également remettre une vidéo de présentation de votre projet (une vidéo par groupe). Vous devrez expliquer les fonctionnalités de votre application, les technologies utilisées, les difficultés rencontrées, l'architecture de votre code, etc. Vous devrez montrer votre application en fonctionnement. Vous mettrez le lien de la vidéo dans le fichier `README.md` de votre projet.
- Tout ce qui précède est obligatoire pour réussir l'examen Q3 et doit être rendu pour **maximum 7 jours avant l'examen Q3 (si l'examen se déroule le 16 août 2025, vous devrez remettre votre projet pour le 9 août 2025 à 22h maximum).**
- Vous passerez un examen oral par groupe. Chaque membre du groupe doit être capable d'expliquer l'ensemble du code du projet, les tests, la documentation, etc. Chaque membre devra aussi répondre à des questions sur les technologies utilisées, les choix que vous avez faits, les difficultés rencontrées, etc. Vous devez également être capable de montrer votre application en fonctionnement.
- Prenez chacun vos ordinateurs portables pour l'examen oral. Vous serez potentiellement interrogés simultanément via une application en ligne.


### *Bon travail !*

