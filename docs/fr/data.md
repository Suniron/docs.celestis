# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

---

## Sommaire

- [Data](#data)
  - [averagePrice](#averagePrice)
  - [item](#item)
  - [getStepRewards](#getsteprewards)

# api.data.

Fonctions relatives aux api.data.

---

<h2 id="averagePrice">data.averagePrice(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Donne le prix moyen d'un item

**Exemple:**

```js
const prix = api.data.averagePrice(289); // Donne le prix moyen du blé
```

---

<h2 id="item">data.item(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Donne toutes les infos d'un item

**Exemple:**

```js
const ble = await api.data.item(289); // Donne toutes les infos du blé
```

---

<h2 id="getsteprewards">data.getStepRewards(<code>stepId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Donne toutes les récomponses d'une étape de quête (xp, kamas, ids des objets)

**Exemple:**

```js
const rewards = await api.data.getStepRewards(2733);
```

---
