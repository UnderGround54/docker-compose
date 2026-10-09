# Lancer le projet en local

Ce fichier Compose orchestre l'API Symfony, MySQL et l'application Angular. Les
deux applications doivent rester dans les dossiers voisins `../clean_architecture`
et `../gestion-stock-front-CA`.

Depuis ce dossier, lancer :

```sh
docker compose up --build
```

Au premier démarrage, le conteneur de l'API attend que MySQL soit prêt puis
applique les migrations Doctrine. Accès locaux :

- Frontend : http://localhost:4201
- API : http://localhost:8080/api/v1

Les paramètres sont surchargeables dans le fichier `.env` de ce dossier :
`DB_USER`, `DB_PASSWORD`, `DB_ROOT_PASSWORD`, `APP_SECRET`, `APP_ENV`,
`APP_DEBUG` et `FRONT_PORT` (4201 par défaut). Les valeurs par défaut sont
uniquement destinées au développement
local ; ne pas les réutiliser en production. Les mots de passe de base de
données doivent être alphanumériques pour rester compatibles avec l'URL de
connexion Doctrine.

Arrêter les conteneurs avec `docker compose down`. Les données MySQL sont
conservées dans le volume `db_data`.
