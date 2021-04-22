**Point visio nuxt**

Présentation de l'arborescence et des fichiers de config

Montrage du linter eslint qui permet de définir des standards de code pour harmoniser la production de code entre les codeurs

le **store** :

les routes pointent vers les dossiers **pages** dans lesquels on a les fichiers vue. Nuxt s'occupe de générer le routing  quand on créée un dossier dans le dossier pages.
(voir la doc pour comprendre comment ça se passe derrière)

Le slug de nuxt permet le routing dynamique en utilisant des caracteres en plus de numéros d'id traditionnellement utilisés.

Penser à décomposer les éléments en composants qu'on réutilise

Convention de nommage des composants : 
- si utilisé une seule fois, préfixer avec The
- si a vocation à être réutilisé, utiliser app.

on définit les props dans son component

import des composants avec ``<composant props = "proptype />``

mettre : ou v-bind devant une variable permet de traiter dynamiquement

propirété != variable locale. Ne pas tenter de modifier une propriété

store -> input -> dispatch -> store -> commit mutation (? )

jm moins à l'aise que romain, mais donne plus de temps pour comprendre vu qu'il explique moin vite (et moins clairement aussi)

installer vue devtools ?