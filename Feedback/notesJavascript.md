**Notes JS**

*02 Avril*

**use strict**; en haut du code permet d'activer les dernières modifs du code js (attention compatibilité avec ancien code)
let : définit une variable à portée de bloc
var : définit une variable à portée globale
Il existe deux limitations pour un nom de variable en JavaScript :
- Le nom ne doit contenir que des lettres, des chiffres, des symboles $ et _.
- Le premier caractère ne doit pas être un chiffre.
const COLOR_ORANGE = "#FF7F00"; 

Cela permet + de lisibilité d'utiliser une constante plutôt qu'une suite de caractères abstraite.

Nommer les constantes en MAJUSCULES si leur valeur est connue avant le chargement de la page.

En JavaScript, **null** n’est pas une “référence à un objet non existant” ou un “pointeur nul” comme dans d’autres langages. 
C’est juste une valeur spéciale qui a le sens de “rien”, “vide” ou “valeur inconnue”.


```typeof(x)``` retourne une string du type de x
une chaîne de caractère non vide est traitée comme true

**opérandes** : nombres concernés par un opérateur mathématique
- opérande unaire = un seul nombre concerné
- opérande binaire = deux nombres concernés

Le résultat de a % b est le reste de la division entière de a par b.
L’opérateur d’exponentiation a ** b multiplie a par lui-même b fois. En mathématiques à l’école, nous écrivons cela ab.

alert( 2 + '1' ); // "21"
alert(2 + 2 + '1' ); // "41" et non "221"
let apples = "2";
let oranges = "3";
// les deux valeurs converties en nombres avant le binaire plus

alert( +apples + +oranges ); // 5

L’incrémentation / décrémentation ne peut être appliquée qu’à une variable. Une tentative pour l’utiliser sur une valeur comme 5++ donnera une erreur.

La valeur **undefined** ne doit pas du tout participer aux comparaisons : alert( undefined == 0 ); // false (3)

```let accessAllowed = (age > 18) ? true : false; ``` operateur ternaire

Un !! est parfois utilisé pour convertir une valeur en type booléen :

```alert( !!"non-empty string" );``` // true

```alert( !!null );``` // false

renvoie le premier argument s’il n’est pas nul/undefined. Sinon, le second.

|| renvoie la première valeur vraie.

?? renvoie la première valeur définie.

La combinaison “boucle infinie + **break** au besoin” est idéale pour les situations où la condition doit être vérifiée non pas au début / à la fin de la boucle, mais au milieu, voire à plusieurs endroits du corps.

La directive **continue** est une “version plus légère” de **break**. Cela n’arrête pas toute la boucle. Au lieu de cela, elle arrête l’itération en cours et force la boucle à en démarrer une nouvelle (si la condition le permet).
switch(x) {
  case 'value1':   si (x === 'value1')
    ...
    [break]
  case 'value2':   si (x === 'value2')
    ...
    [break]
  default:
    ... 
    [break]
}

Plusieurs variantes de **case** partageant le même code peuvent être regroupées.
  case 3: // (*) grouped two cases
  case 5:
    alert('Wrong!');
    alert("Why don't you take a math class?");
    break;

Les variables déclarées en dehors de toute fonction sont appelées globales
Les variables globales sont visibles depuis n’importe quelle fonction (sauf si elles sont masquées par les variables locales).
C’est une bonne pratique de minimiser l’utilisation de variables **globales**

Si un paramètre n’est pas fourni, sa valeur devient **undefined**.

*03 Avril*

Il est parfois judicieux de définir des valeurs par défaut pour les paramètres non pas dans la déclaration de fonction, mais à un stade ultérieur, lors de son exécution.
Pour vérifier un paramètre omis, nous pouvons le comparer avec undefined
La directive return peut être n’importe où dans la fonction. Lorsque l’exécution le permet, la fonction s’arrête et la valeur est renvoyée au code appelant (affecté à result ci-dessus).
Il peut y avoir plusieurs occurrences de return dans une seule fonction.
Il est possible d’utiliser return sans valeur. Cela entraîne la sortie immédiate de la fonction.
Une fonction doit faire exactement ce qui est suggéré par son nom, pas plus.
Deux actions indépendantes méritent généralement deux fonctions, même si elles sont généralement appelées ensemble 
expression de fonction :
let sayHi = function() {
  alert( "Hello" );
};
Ici, la fonction est créée et attribuée explicitement à la variable, comme toute autre valeur. Quelle que soit la définition de la fonction, il ne s’agit que d’une valeur stockée dans la variable sayHi.
Une **Fonction Expression** est créée lorsque l’exécution l’atteint et est utilisable à partir de cet moment.
Une **fonction déclaration** peut être appelée plus tôt que sa définition.
f **callback** & f **anonymes**
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); }, //**callback anonyme**
  function() { alert("You canceled the execution."); } //**callback anonyme**
);
let func = (arg1, arg2, ..., argN) => expression //expression flechée de 
let func = function(arg1, arg2, ..., argN) {
  return expression;
};

function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
); // expression de fonction

ask(
  "Do you agree?",
  () => alert("You agreed."),
  () => alert("You canceled the execution.")
); // fonction flechée

*06 Avril*

async/await

*07 Avril*

if else sans {} si une seule ligne
un tableau défini en const reste un tableau (objet idem), mais son contenu peut changer, à l'inverse des string et autres conneries du genre
on ne touche plus au fondement de l'être de la constante définie une fois qu'elle est définie
un tableau/objet est toujours défini en constante

*08Avril*

L'opérateur ... permet de décomposer un itérable
```
const ids = userList.map(item => item.id)
const idmax = Math.max(...ids)
```
Ici, math.max sera appliqué à l'ensemble des résultats du tableau et non au tableau lui-même, qui sinon donnerait ```NaN```.

*12Avril*

str.subsract permet d'enlever des caractères d'une string en partant de l'un ou l'autre des bouts de la string.

Si on veut enlever un bout de string fixe à la fin d'une string (une extension par exemple), on peut utiliser 
```
mastring.slice(0, -4)
```
où -4 correspond au nombre de caractères que l'on enlève à la fin de la string