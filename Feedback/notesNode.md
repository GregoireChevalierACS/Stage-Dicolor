**Notes JS**

*06 Avril*

- Pour lancer vsc via le linux de wsl 2 :
    - ouvrir vsc
    - installer le plugin remote wsl
    - lancer ubuntu
    - taper code .

Pour lancer un serveur node, se positionner dans le dossier où se trouve un fichier js avec du code node et taper :

```node + {nomdufichier.js}```

Express, le framework nodeJs, est considéré par **npm** (NodePackageManager) comme un simple package qui doit être téléchargé et installé, et appelé dans le code.

Fetch & install du package **express** :

```npm init``` va initialiser le dossier et créer un fichier package.json avec les details promptés par l'utilisateur.

```npm install express``` va installer le package express et ajouter la ligne correspondante au package.json

Pour utiliser express, il faut appeler la fonction ```require()``` dans le fichier point d'entrée de l'application.

Les scripts dans le package.json permettent d'exécuter des tâches automatiquement (e.g., running tools to minify JavaScript, shrink images, LINT/analyze your code, etc).

Le express generator permet de générer des squelettes d'application (comme skeleton pour symfony) on l'installe avec la commande ```npm install express-generator -g```

```express nomduprojet``` génère le squelette du projet à venir. Reste plus qu'à se diriger dans le dossier, et run ```npm install``` pour installer les dépendances, puis ```DEBUG=helloworld:* npm start```

(Attention la commande change selon les os)

**important pour wsl2** :

Pour éviter que la connexion à 127.0.0.1 soit refusée quand on utilise wsl2, il faut préciser : ```, '0.0.0.0'``` après chaque définition d'écoute de port. Soit dans l'index avec :
```app.listen(port, '0.0.0.0', () => {
  console.log(`Example app listening on port ${port}!`)
});
```
Soit dans bin/www

```
server.listen(port, '0.0.0.0');
```
si on a utilisé la génération de projet avec express.