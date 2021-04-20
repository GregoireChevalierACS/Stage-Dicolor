**Notes NUXT**

*20 Avril*

Dans une application Nuxt.js, les **vues** se composent d'un template, d'un layout et de la page actuelle. Il est possible de définir des méta tags personnalisés pour la section head de chaque page (important pour le SEO : référencement naturel).

```
<template>
  <h1 class="red">Hello World</h1>
</template>

<script>
  export default {
    head() {
      // Configurer ici les méta tags (seo)
    }
    // ...
  }
</script>

<style>
  .red {
    color: red;
  }
</style>
```

Il est possible de définir un **layout** par défaut en ajoutant un fichier default.vue dans le répertoire des layouts. Ceci sera utilisé pour toutes les pages qui n'ont pas de layout déjà spécifié. La seule chose qu'il sera nécessaire d'inclure dans le layout est le composant <Nuxt /> qui s'occupera de render le composant page.
```
<template>
  <Nuxt />
</template>
```
Ces layouts peuvent être personnalisés en créant des fichiers dans le dossier layouts, qui seront à appeler dans les vues correspondantes :
```<template>
  <!-- notre template -->
</template>
<script>
  export default {
    layout: 'blog'
    // ici se trouvent les définitions du composant page
  }
</script>
```

Le **cycle de vie** de Nuxt.js décrit les différentes étapes qui ont lieu après la phase de build, une fois que notre application a été bundlée, chunkée et minifiée. Ce qu'il se passe après cette phase dépend de si nous avons activé le rendu côté serveur ou pas. Si c'est le cas, il faut ensuite regarder le type de rendu serveur que nous avons choisi:

Rendu dynamique côté serveur (SSR) (nuxt start)

ou Génération statique de site (SSG) (nuxt generate).

Le **contexte** fournit des informations additionnelles et souvent optionnelles de la requête envoyée à l'application. L'object ```context``` est disponible dans des fonctions spécifiques de Nuxt comme asyncData, plugins, middleware et nuxtServerInit

Le **contexte** est utilisé pour permettre un accès aux autres parties d'une application Nuxt.js, comme par exemple un store Vuex ou l'instance connect sous-jacente. Ainsi, nous avons les objets req et res disponibles dans le contexte du côté serveur et le store de toujours disponible. 

**HMR** : "hot reload", en gros ce qui permet à l'app de se recharger dans le navigateur à la modification de fichier ( = watcher)

**computed** : ensemble de valeurs toujours à jour et toujours accessibles

**watch** : permet de vérifier une variable (ou objet ou tableau)

**method**

**vmodel**

**mounted** 

v-for

v-if  **! : en cas de non remplissage de la condition, les éléments relatifs sont supprimés du dom**

v-show comme v-if mais cache au lieu de détruire

v-model

module != buildmodule != plugin

axios = module pour requetes http

plugins = import + inject

possibilité de faire marcher un plugin que coté client ou serveur (server side rendering )

toujours utiliser un module nuxt officiel si possible

