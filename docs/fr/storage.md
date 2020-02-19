# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

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

Toutes les fonctions relatives au storage.

**Tous les GID sont disponibles dans le fichier [items.txt](https://docs.Celestis.com/ids/items.txt).**

<hr>

<h2 id="storage-item-count">
  storage.itemCount(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre d’objets dans l'espace de storage.

**Exemple:**

```js
const itemCount = storage.itemCount(289); // Retourne le nombre de blé présents dans l'inventaire.
```

<hr>

## storage.items()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne les items présent dans l'espace de storage.

**Exemple:**

```js
const items = storage.items();
```

<hr>

## storage.kamas()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre de kamas dans l'espace de storage.

**Exemple:**

```js
const kamas = storage.kamas();
```

<hr>

<h2 id="storage-item-put">
  storage.putItem(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Insère un item donné dans une quantité donnée.

**Exemple:**

```js
yield * storage.putItem(367, 100); // Insère 100 Oeufs de Tofu dans le coffre.
```

<hr>

<h2 id="storage-item-get">
  storage.getItem(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Récupère un item donné dans une quantité donnée.

**Exemple:**

```js
yield * storage.getItem(371, 200); // Récupère 200 Sourcils de Moskito du coffre.
```

<hr>

<h2 id="storage-put-kamas">
  storage.putKamas(<code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Insère des kamas dans le storage.

**Exemple:**

```js
yield * storage.putKamas(1000000000); // Insère 1 milliard de kamas dans le coffre. (Oui, j'suis riche :))
```

<hr>

<h2 id="storage-get-kamas">
  storage.getKamas(<code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Récupère des kamas dans le storage.

**Exemple:**

```js
yield * storage.getKamas(1000000000); // Récupère 1 milliard de kamas du coffre. (Toujours aussi riche :o)
```

<hr>

## storage.putAllItems()

Insère tous les items dans le storage.

**Exemple:**

```js
yield * storage.putAllItems(); // Insère tous les items
```

<hr>

## storage.getAllItems()

Récupère tous les items dans le storage.

**Exemple:**

```js
yield * storage.getAllItems(); // Récupère tous les items.
```

<hr>

## storage.putExistingItems()

Insère tous les items déjà existants dans le storage.

**Exemple:**

```js
yield * storage.putExistingItems(); // Insère tous les items déjà existants dans le storage.
```

<hr>

## storage.getExistingItems()

Récupère tous les items déjà existants dans l'inventaire.

**Exemple:**

```js
yield * storage.getExistingItems(); // Récupère tous les items déjà existants dans l'inventaire.
```
