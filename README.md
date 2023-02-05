# Carousel vuejs

Au final un carousel est plutot simple, il doit afficher un slide en particulier donc:

- Il doit savoir sur quel slide on est actuellement
- Il doit aussi connaitre le nombre d'enfant qu'il y a, c-à-d le nombre de slide dans notre carousel. et on peut le savoir avec `this.$children`
- Pour charger une image local avec vue.js on utilise la method `require` permet de charger une ressource local et cette methode est integer à vuejs mais attention la ressource que vous voulez charger doit exister sinon vous aurez une erreur.

## Project setup

```{SHELL}
pnpm install
```

### Compiles and hot-reloads for development

```{SHELL}
pnpm run serve
```

### Compiles and minifies for production

```{SHELL}
pnpm run build
```

### Lints and fixes files

```{SHELL}
pnpm run lint
```
