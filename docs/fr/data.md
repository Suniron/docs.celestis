# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Data](#data)
  - [averagePrice](#averagePrice)
  - [item](#item)
  - [getStepRewards](#getsteprewards)

# Data

Fonctions relatives aux data

<hr>

<h2 id="averagePrice">data.averagePrice(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Donne le prix moyen d'un item

**Exemple:**

```js
const prix = data.averagePrice(289); // Donne le prix moyen du blé
```

<hr>

<h2 id="item">data.item(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Donne toutes les infos d'un item

**Exemple:**

```js
const ble = await data.item(289); // Donne toutes les infos du blé
```

<hr>

<h2 id="getsteprewards">data.getStepRewards(<code>stepId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Donne toutes les récomponses d'une étape de quête (xp, kamas, ids des objets)

**Exemple:**

```js
const rewards = await data.getStepRewards(2733);
```

<hr>
