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
```
app.listen(port, '0.0.0.0', () => {
  console.log(`Example app listening on port ${port}!`)
});
```
Soit dans bin/www

```
server.listen(port, '0.0.0.0');
```
si on a utilisé la génération de projet avec express.

*07 Avril*

Chaque fichier a des stats inhérentes telles que la date de création ou de modification. Le **mtime** garde la date de dernière modification du contenu du fichier. Le **ctime** garde la date de dernière modification des métadonnées du fichier tel que le nom du fichier ou ses droits d'accès. mtime et ctime sont exprimées jusqu'à la miliseconde.

Pour utiliser les ctime et mtime on utilise le module node ```fs``` comme "file system" en l'appelant dans le code :
```
const Fs = require('fs')

function lastUpdatedDate (file) {  
  const { mtime, ctime } = Fs.statSync(file)

  console.log(`File data   last modified: ${mtime}`)
  console.log(`File status last modified: ${ctime}`)

  return mtime
}
```

Les vues d'express sont au format .jade (~= twig pour symfony)
insomnia = postman en light

*08 Avril*

Avant d'interagir avec un fichier du filesystem, il faut lui donner un file descriptor

File descriptor : A file descriptor is what's returned by opening the file using the open() method offered by the fs module:
```
const fs = require('fs')

fs.open('/Users/joe/test.txt', 'r', (err, fd) => {
  //fd is our file descriptor
})
```
Le r en second paramètre est pour "read" qui permet la lecture du fichier. On trouve également r+ pour lire et écrire, w+ pareil mais crée le fichier s'il n'existe pas encore.

Attention : ```fs.writeFile()```écrase le texte tapé avant l'appel de la fonction ! Il faut préciser le flag a+ pour rajouter du texte au texte existant :`
```
fs.writeFile('test.txt', content, { flag: 'a+' }, err => {
  if (err) {
    console.error(err)
    return
  }
  //file written successfully
})
```
On peut aussi utiliser ``fs.appendFile()``

*09Avril*

Pour utiliser une fonction d'un fichier dans un autre, il faut faire un 
```
module.exports = { mafonction };
```
dans le fichier source et 
```
const monfichier = require("./mondossier/monfichier");
```
dans le fichier destination

Lorsqu'on utilise l'export / import pour les events, il est préférable de découper les events dans des fichiers différents pour éviter la full merde

fs open permet d'accéder au fichier si besoin

*12Avril*

fs.open et fs.readfile vont chercher dans le dossier source. Pour pointer vers un fichier précis dans un dossier, il faut rajouter le chemin vers la cible expressément

Ne pas oublier d'installer les packages requis dans chaque dossier, ou faire une install en -g pour global