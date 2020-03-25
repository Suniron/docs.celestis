# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

---

## Sommaire

- [Storage](#storage)
  - [itemCount](#storage-item-count)
  - [items](#storageitems)
  - [kamas](#storagekamas)
  - [putItem](#storage-item-put)
  - [getItem](#storage-item-get)
  - [putKamas](#storage-put-kamas)
  - [getKamas](#storage-get-kamas)
  - [putAllItems](#storageputallitems)
  - [getAllItems](#storagegetallItems)
  - [putExistingItems](#storageputexistingitems)
  - [getExistingItems](#storagegetexistingitems)

# Stockage

Toutes les fonctions relatives au api.storage.

**Tous les GID sont disponibles dans le fichier [items.txt](https://suniron.github.io/docs.celestis/ids/items.txt).**

---

<h2 id="storage-item-count">
  api.storage.itemCount(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre d’objets dans l'espace de api.storage.

**Exemple:**

```js
const itemCount = api.storage.itemCount(289); // Retourne le nombre de blé présents dans l'inventaire.
```

---

## api.storage.items()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne les items présent dans l'espace de api.storage.

**Exemple:**

```js
const items = api.storage.items();
```

---

## api.storage.kamas()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre de kamas dans l'espace de api.storage.

**Exemple:**

```js
const kamas = api.storage.kamas();
```

---

<h2 id="storage-item-put">
  api.storage.putItem(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Insère un item donné dans une quantité donnée.

**Exemple:**

```js
yield * api.storage.putItem(367, 100); // Insère 100 Oeufs de Tofu dans le coffre.
```

---

<h2 id="storage-item-get">
  api.storage.getItem(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Récupère un item donné dans une quantité donnée.

**Exemple:**

```js
yield * api.storage.getItem(371, 200); // Récupère 200 Sourcils de Moskito du coffre.
```

---

<h2 id="storage-put-kamas">
  api.storage.putKamas(<code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Insère des kamas dans le api.storage.

**Exemple:**

```js
yield * api.storage.putKamas(1000000000); // Insère 1 milliard de kamas dans le coffre. (Oui, j'suis riche :))
```

---

<h2 id="storage-get-kamas">
  api.storage.getKamas(<code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Récupère des kamas dans le api.storage.

**Exemple:**

```js
yield * api.storage.getKamas(1000000000); // Récupère 1 milliard de kamas du coffre. (Toujours aussi riche :o)
```

---

## api.storage.putAllItems()

Insère tous les items dans le api.storage.

**Exemple:**

```js
yield * api.storage.putAllItems(); // Insère tous les items
```

---

## api.storage.getAllItems()

Récupère tous les items dans le api.storage.

**Exemple:**

```js
yield * api.storage.getAllItems(); // Récupère tous les items.
```

---

## api.storage.putExistingItems()

Insère tous les items déjà existants dans le api.storage.

**Exemple:**

```js
yield * api.storage.putExistingItems(); // Insère tous les items déjà existants dans le api.storage.
```

---

## api.storage.getExistingItems()

Récupère tous les items déjà existants dans l'inventaire.

**Exemple:**

```js
yield * api.storage.getExistingItems(); // Récupère tous les items déjà existants dans l'inventaire.
```
