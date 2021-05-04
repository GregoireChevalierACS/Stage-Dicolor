**visio strapi**

cms open source headless (que partie back) gratuit utilisé pour la getsion de bases de données. Créé en 2018 et est très actif dans le développement.

Hyper complet. Modélisation de base avec partie graphique intégrée, et utilisation d'api en conséquence

Ajoute une surcouche de plugins (content type builder notamment.)

1337 est le port par défaut de strapi mais peut être modifié dans le .env

Tintin Dupont tintin@mail.com
Test123456

https://strapi.io/documentation/developer-docs/latest/getting-started/quick-start.html

La mediatheque permet de stocker les medias img etc

content type builder creer une collection
définir les champs de la table
et sauvegarder

couper le serveur

Le serveur garde une trace de toutes les requetes envoyées

Les changements apportés commités seront partagés à tous les contributeurs ce qui permet d'harmoniser les routes, fichiers, tables etc...

strapi comprend une surcouche de permissions et roles (parametres -> role&permission -> public - permissions) == authenticator de symfony
strapi cache les lignes de commades relatives aux actions demandées via l'interface

interactivité accrue entre front et back car pas besoin d'orm entre autres.

Moyen d'automatiser les process de création (fixtures) en couplant avec cron

Strapi utilise aussi le principe de services 

attention au publish !

voir strapi blog pour les exemples d'utilisations

possibilité d'ajouter des opérateurs dans les requetes pour alléger leur poids sur le serveur (exemple find id_x id_y au lieu de tout chercher et trier / pagination / tri ...)

regarder la config manuelle

autoriser strapi a envoyer la newslettter

valeur par défaut != placeholder

voir insomnia