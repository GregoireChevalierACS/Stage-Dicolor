**06 Avril**

- Travailler en autonomie sur nodeJs pour pouvoir être intégré sur les projets rapidement.
- Se re-familiariser avec WSL2
- Bricoler un projet expressNodeJs / VSC / WSL2
- Revoir un peu la syntaxe SQL

**07 Avril**


- Apprendre à séparer front et back -> requetes http (notion de fetch en js)
- Créer une api pour retourner des infos de la requête http
- Apprendre à appeler une api depuis le front
- Ajouter une entrée à un tableau déjà existant

**09 Avril**

- Apprendre à utiliser lodash

**13Avril**

- Supprimer les fichiers json et tuiliser les données dans des tableaux
- Une fois l'exercice fini, mettre le cron dans app.js et y importer les fonctions de check de fichiers/folders
- au lancement de l'app, vider le dossier de sortie en csv
- refactorer l'ensemble

**15Avril**

- Bonus : passer les cron en await et y adjoindre un bool qui va autoriser la fonction à se lancer

**18Avril**

- Stocker les informations relatives aux users dans un tableau 
- lier chaque ligne du tableau à une route

**20Avril**

-Réaliser une to-do list avec nuxt et vue

**21Avril**

Consignes exercice formulaire : 

**nom**

minimum 1 caractère
		
ne doit contenir que des lettres et des espaces + tirets
**prénom**
	
minimum 2 caractères
			
ne doit contenir que des lettres et espaces + tirets
	
**adresse email**
		
doit répondre à la regex suivante : min 1 caractère @ min 1 caractère POINT min 2 caractères
		
ne doit contenir que des lettres, chiffres, arobase, tirets, underscores
	
**numéro de téléphone**
		
doit comprendre SOIT :

10 chiffres
			
OU + de 10 caractères avec obligatoirement 10 chiffres + des espaces ou points
	
**adresse**		

minimum 6 caractères
		
ne doit contenir que des lettres, chiffres, tirets, espaces
			
**complément d'adresse**		
		
non requis
		
si rempli, ne doit contenir que des lettres, chiffres, tirets, espaces
	
**code postal**

5 chiffres	
	
**ville**
		
minimum 2 caractères	
		
ne doit contenir que des lettres, tirets et espaces
	
**pays**

minimum 2 caractères
		
ne doit contenir que des lettres, tirets et espaces
		
**mot de passe**

minimum 8 caractères
		
ne doit contenir que des lettres, chiffres et les caractères suivants : -, _, +, *
		
doit contenir AU MOINS :
			
1 majuscule
			
1 minuscule	
			
1 chiffre

1 caractère spécial
				
**confirmation mdp**
		
- identique au mdp précédemment entré

**26Avril**

Etape 1 - Interface


	
	
- Créer un formulaire TheForm.vue pour ajouter un nouveau todo
	
	
	
- Ce formulaire comprend deux champs, le titre et le contenu (textarea)
	
	
	
- Lorsqu'on valide le formulaire (avec un bouton custom) en s'étant assuré que le titre et le contenu ont été remplis, on ajoute dans le store un nouveau todo.
	
	
	
- Créer un autre composant, TheTodoList.vue, qui contient la liste des todos que l'on a crée (sous forme de cards).
	
	
	
- Avec un clic sur une icône "croix" dans une card, on peut supprimer ladite todo.


- implémenter l'ajout de todo
- implémenter la suppression de todo
- styliser le form et le rendu de données
- utiliser les boucles vue pour afficher chaque entrée de todo et coupler avec un composant

**28Avril**

- *Ajouter un nouveau champ sous forme de case à cocher pour stipuler ou non que la tâche est prioritaire - cela ajoutera aux côtés de title et content une nouvelle clé important (booléen)*
	
- *Lorsqu'on ajoute un todo, on doit désormais écrire sa date de création au format timestamp (avec day.js) avec une nouvelle clé created_at* !!! timestamp

- Ajouter la possibilité de filtrer la liste des todos (via un menu select) :
		
- par ordre d'importance
		
- par date de création
		
- par ordre alphabétique
		
- Gérer un mode ascendant/descendant pour ces filtres
	
- *Ajouter un bouton pour supprimer toutes les tâches*