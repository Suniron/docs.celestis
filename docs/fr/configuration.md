# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Configuration](#configuration)
  - [MAX_PODS](#max_pods)
  - [MIN_MONSTERS](#min_monsters)
  - [MAX_MONSTERS](#max_monsters)
  - [MIN_MONSTERS_LEVEL](#min_monsters_level)
  - [MAX_MONSTERS_LEVEL](#max_monsters_level)
  - [MIN_XP_PER_FIGHT](#min_xp_per_fight)
  - [MAX_XP_PER_FIGHT](#max_xp_per_fight)
  - [FORBIDDEN_MONSTERS](#forbidden_monsters)
  - [MANDATORY_MONSTERS](#mandatory_monsters)
  - [MAX_FIGHTS_PER_MAP](#max_fights_per_map)
  - [ELEMENTS_TO_GATHER](#elements_to_gather)
  - [BANK_PUT_ITEMS](#bank_put_items)
  - [BANK_GET_ITEMS](#bank_get_items)
  - [BANK_PUT_KAMAS](#bank_put_kamas)
  - [BANK_GET_KAMAS](#bank_get_kamas)
  - [AUTO_REGEN](#auto_regen)
  - [AUTO_DELETE](#auto_delete)
  - [OPEN_BAGS](#open_bags)
  - [DISPLAY_GATHER_COUNT](#display_gather_count)
  - [DISPLAY_FIGHT_COUNT](#display_fight_count)
  - [Mise en pratique](#mise-en-pratique)

# Configuration

Nous allons voir comment configurer les comportements des différentes actions dans les scripts.

La configuration, c'est des variables avec des noms bien précis qui vous permettent de configurer les comportements des différentes actions dans les scripts.

Si vous ne déclarez pas une variable, elle aura une valeur par défaut. Vous n'êtes donc pas obligé de déclarer une variable si elle ne vous sert à rien.

**Vous trouverez tous les id des monstres dans [monsters.txt](https://docs.Celestis.com/ids/monsters.txt).**

**Vous trouverez tous les id des ressources récoltables dans [resources.txt](https://docs.Celestis.com/ids/resources.txt).**

**Vous trouverez tous les id des items dans [items.txt](https://docs.Celestis.com/ids/items.txt).**

_Remarque: ces variables doivent toutes etre définies dans l'object config, dans le cas contraire cela n'aurai aucune utilité._

<hr>

## MAX_PODS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le pourcentage de pods au-delà duquel votre personnage va retourner en banque (en utilisant le chemin **[bank](paths.md#bank)**).

**Exemple:**

```js
const config = { MAX_PODS: 100 }; // Retour en banque à 100% de pods
```

_Valeur par défaut: Retour en banque à 90% de pods._

<hr>

## MIN_MONSTERS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le nombre de monstres minimum à attaquer (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MIN_MONSTERS: 2 }; // Combattre les groupes de 2 monstres minimum
```

_Valeur par défaut: 1._

<hr>

## MAX_MONSTERS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le nombre de monstres maximum à attaquer (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MAX_MONSTERS: 5 }; // Combattre les groupes de 5 monstres maximum
```

_Valeur par défaut: 8._

<hr>

## MIN_MONSTERS_LEVEL

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le niveau minimum d'un groupe de monstres à attaquer (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MIN_MONSTERS_LEVEL: 200 }; // Combattre les groupes de niveau 200 minimum
```

_Valeur par défaut: niveau 1._

<hr>

## MAX_MONSTERS_LEVEL

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le niveau maximum d'un groupe de monstres à attaquer (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MAX_MONSTERS_LEVEL: 500 }; // Combattre les groupes de niveau 500 maximum
```

_Valeur par défaut: niveau 1000._

<hr>

## MIN_XP_PER_FIGHT

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le nombre minimum d'xp voulu d'un groupe de monstres à attaquer (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MIN_XP_PER_FIGHT: 500 }; // Combattre les groupes qui donnent minimum 500 XP (sans challenges)
```

_Valeur par défaut: 0._

<hr>

## MAX_XP_PER_FIGHT

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer le nombre maxium d'xp voulu d'un groupe de monstres à attaquer (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MAX_XP_PER_FIGHT: 90888 }; // Combattre les groupes qui donnent maximum 90888 XP (sans challenges)
```

_Valeur par défaut: Infinity._

<hr>

## FORBIDDEN_MONSTERS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>

Cette variable permet de configurer les monstres interdits (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { FORBIDDEN_MONSTERS: [148, 134] }; // Ne pas attaquer les Chef de Guerre Bouftou ou les Boufton Blanc
```

_Valeur par défaut: pas de monstre interdit._

<hr>

## MANDATORY_MONSTERS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>

Cette variable permet de configurer les monstres obligatoires (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MANDATORY_MONSTERS: [149] }; // Attaque uniquement s'il y a un Boufton Noir dans le groupe
```

_Valeur par défaut: pas de monstre obligatoire._

<hr>

## MAX_FIGHTS_PER_MAP

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Ce paramètre permet de configurer le nombre de combats maximum par map (lorsque vous utilisez l'action **[fight](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { MAX_FIGHTS_PER_MAP: 10 }; // Le bot continuera le script après 10 combats sur la map
```

_Valeur par défaut: pas de limite au nombre de combat sur la map._

<hr>

## ELEMENTS_TO_GATHER

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>

Cette variable permet de configurer les éléments à récolter (lorsque vous utilisez l'action **[gather](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { ELEMENTS_TO_GATHER: [38, 43] }; // Récolte uniquement le Blé et l'Orge
```

_Valeur par défaut: récolte tous les éléments._

<hr>

## BANK_PUT_ITEMS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">Array<{ id: number; quantity: number }></a>

Cette variable permet de configurer les éléments à déposer en banque (lorsque vous utilisez l'action **[npcBank](paths.md) = true** sur une map).

**Exemple:**

```js
const config = {
  BANK_PUT_ITEMS: [
    { id: 289, quantity: 0 }, // Dépose tout le blé en banque
    { id: 6965, quantity: 5 } // Dépose 5 Potion de cité : Bonta en banque
  ]
};
```

_Valeur par défaut: ne dépose rien._

Si vous mettez une quantité de 0, toute la quantité de l'élément sera déposée.

<hr>

## BANK_GET_ITEMS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">Array<{ id: number; quantity: number }></a>

Cette variable permet de configurer les éléments à récupérer en banque (lorsque vous utilisez l'action **[npcBank](paths.md) = true** sur une map).

**Exemple:**

```js
const config = {
  BANK_GET_ITEMS: [
    { id: 6964, quantity: 5 } // Récupère 5 Potion de cité : Brâkmar
  ]
};
```

_Valeur par défaut: ne récupère aucun élément._

Si vous mettez une quantité de 0, toute la quantité de l'élément sera récupérée.

<hr>

## BANK_PUT_KAMAS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer les kamas à déposer en banque (lorsque vous utilisez l'action **[npcBank](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { BANK_PUT_KAMAS: 2000 }; // Dépose 2 000 kamas en banque
```

_Valeur par défaut: ne dépose pas de kamas._

Si vous mettez 0, tous les kamas seront déposés.

<hr>

## BANK_GET_KAMAS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Cette variable permet de configurer les kamas à récupérer en banque (lorsque vous utilisez l'action **[npcBank](paths.md) = true** sur une map).

**Exemple:**

```js
const config = { BANK_GET_KAMAS: 2000 }; // Récupère 2 000 kamas en banque
```

_Valeur par défaut: ne récupère pas de kamas._

Si vous mettez 0, tous les kamas seront récupérés.

<hr>

## AUTO_REGEN

- Valeur: `{ items: number[]; store: number; minLife: number; maxLife: number }`

Cette variable permet de configurer la régénération automatique par items (lorsque vous utilisez l'action **[gather](paths.md) = true** ou [fight](paths.md) = true sur une map).

**Exemple:**

```js
const config = {
  AUTO_REGEN: {
    minLife: 60, // Regeneration si en-dessous de 60%
    maxLife: 90, // Regeneration jusqu'a 90%
    items: [1737, 528], // Items a utiliser pour la regeneration par ordre de priorité
    store: 200 // Avoir 200 items au total sur soit après le passage à la banque
  }
};
```

_Valeur par défaut: pas de régénération automatique._

L'attribut maxLife est facultatif, s'il n'est pas précisé, il se régènera jusqu'à 100%
Les items sont utilisés dans l'ordre, lorsque le premier item n'est plus disponible, il utilisera le second, etc.
Lors du retour en banque, il prendra en priorité le premier élément si il est disponible en quantité suffisante, sinon il comblera avec le second item jusqu'à atteindre la quantité désirée.
S'il n'y a plus d'items disponibles, le personnage attend d'avoir retrouvé ses points de vie avant de continuer.

<hr>

## AUTO_DELETE

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>

Cette variable permet de configurer la suppression automatique lorsque le personnage est full pods.

**Exemple:**

```js
const config = {
  AUTO_DELETE: [598, 1799] // Supprime automatiquement les Greu-Vette et les Kralamoure Unique
};
```

_Valeur par défaut: pas de suppression automatique._

Cette fonction est compatible avec le retour en banque, si le personnage est full pods, la suppression automatique va se faire et le personnage ira en banque si après la suppression automatique il est toujours full pods.

La suppression automatique se fait lorsque MAX_PODS est atteint.

<hr>

## OPEN_BAGS

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Cette variable permet de configurer l'ouverture automatique des sacs de récolte.

**Exemple:**

```js
const config = { OPEN_BAGS: true };
```

_Valeur par défaut: false, pas d'ouverture automatique des sacs._

<hr>

## DISPLAY_GATHER_COUNT

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Cette variable permet de configurer l'affichage du compteur de récoltes.

**Exemple:**

```js
const config = { DISPLAY_GATHER_COUNT: true }; // Affiche le compteur de récoltes
```

_Valeur par défaut: pas d'affichage du compteur de récoltes._

<hr>

## DISPLAY_FIGHT_COUNT

- Valeur: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Cette variable permet de configurer l'affichage du compteur de combats.

**Exemple:**

```js
const config = { DISPLAY_FIGHT_COUNT: true }; // Affiche le compteur de combats
```

_Valeur par défaut: pas d'affichage du compteur de combats._

<hr>

# Mise en pratique

**Exemple:**

```js
const config = {
  MAX_PODS: 90, // Retour en banque à 90% pods
  MIN_MONSTERS: 2, // 2 monstres minimum
  MAX_MONSTERS: 3, // 3 monstres maximum
  AUTO_DELETE: [384, 881, 885], // Supprime Laine Bouftou, Laine de Boufton Blanc et Laine de Boufton Noir
  BANK_GET_KAMAS: 200, // Récupère 200 kamas en banque (on ne sait jamais)
  BANK_GET_ITEMS: [
    { id: 548, quantity: 1 } // Récupère une Potion de Rappel à chaque passage en banque
  ]
};
```

Nous pouvons avoir accès à tout moment à ces variables. Donc on peut aussi les modifier dans une fonction custom !

**Exemple:**

```js
config.MAX_MONSTERS = 3;
printMessage(config.MAX_MONSTERS); // Affiche 3
```
