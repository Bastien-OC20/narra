# narra-realms

## Introduction

Narra-realms est une plateforme de narration interactive permettant aux utilisateurs de créer et de jouer des histoires immersives.

## Prérequis

- Node.js (version 14 ou supérieure)
- npm (version 6 ou supérieure)

## Installation

```bash
# Cloner le dépôt
$ git clone https://github.com/votre-utilisateur/narra-realms.git

# Aller dans le répertoire du projet
$ cd narra-realms

# Installer les dépendances
$ npm install
```

## Utilisation

```bash
# Servir avec rechargement à chaud à localhost:3000
$ npm run dev

# Construire pour la production et lancer le serveur
$ npm run build
$ npm run start

# Générer un projet statique
$ npm run generate
```

## Structure du Projet

- `assets/` : Contient les ressources non compilées telles que les fichiers Stylus ou Sass, les images ou les polices.
- `components/` : Contient les composants Vue.js réutilisables.
- `layouts/` : Contient les mises en page de l'application.
- `pages/` : Contient les vues et les routes de l'application.
- `plugins/` : Contient les plugins JavaScript à exécuter avant d'instancier l'application Vue.js principale.
- `static/` : Contient les fichiers statiques mappés à `/`.
- `store/` : Contient les fichiers de store Vuex.

## Contribuer

Les contributions sont les bienvenues ! Veuillez suivre les étapes suivantes pour contribuer :

1. Forker le dépôt
2. Créer une branche pour votre fonctionnalité (`git checkout -b feature/ma-fonctionnalité`)
3. Commiter vos modifications (`git commit -am 'Ajouter ma fonctionnalité'`)
4. Pousser la branche (`git push origin feature/ma-fonctionnalité`)
5. Ouvrir une Pull Request

## Licence

Ce projet est sous licence [GNU General Public License v3.0](LICENSE).
