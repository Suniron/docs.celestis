# CookieTouch API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Inventory](#inventory)
  - [objects](#inventoryobjects)
  - [consumables](#inventoryconsumables)
  - [equipments](#inventoryequipments)
  - [resources](#inventoryresources)
  - [questObjects](#inventoryquestObjects)
  - [pods](#inventorypods)
  - [podsMax](#inventorypodsmax)
  - [podsP](#inventorypodsp)
  - [equipedItems](#inventoryequipeditems)
  - [isEquiped](#inventoryisequiped)
  - [itemCount](#inventaire-item-count)
  - [itemWeight](#inventaire-item-weight)
  - [useItem](#inventaire-item-use)
  - [equipItem](#inventaire-item-equip)
  - [unEquipItem](#inventaire-item-un-equip)
  - [dropItem](#inventaire-item-drop)
  - [deleteItem](#inventaire-item-delete)

# Inventaire

Toutes les fonctions relatives à l’inventaire du personnage.

**Tous les GID sont disponibles dans le fichier [items.txt](https://docs.cookietouch.com/ids/items.txt).**

## inventory.objects()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne tous les objets présents en inventaire.

```js
const objects = inventory.objects();
```

<hr>

## inventory.consumables()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne tous les consomables présents en inventaire.

```js
const consumables = inventory.consumables();
```

<hr>

## inventory.equipments()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne tous les équipements présents en inventaire.

```js
const equipments = inventory.equipments();
```

<hr>

## inventory.resources()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne tous les ressources présentes en inventaire.

```js
const resources = inventory.resources();
```

<hr>

## inventory.questObjects()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne tous les objets de quêtes présents en inventaire.

```js
const questObjects = inventory.questObjects();
```

<hr>

## inventory.pods()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre de pods utilisés.

```js
const pods = inventory.pods();
```

<hr>

## inventory.podsMax()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les pods maximum du personnage.

```js
const podsMax = inventory.podsMax();
```

<hr>

## inventory.podsP()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le pourcentage de pods utilisés.

```js
const podsP = inventory.podsP();
```

<hr>

## inventory.equipedItems()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne les items équipés

```js
const items = inventory.equipedItems();
```

<hr>

<h2 id="inventoryisequiped">
  inventory.isEquiped(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">Boolean</a>

Retourne true si l'item est équipé sinon false

```js
const equiped = inventory.isEquiped(2411); // `equiped` seras true si vous avec une Coiffe du Bouftou d'équipé
```

<hr>

<h2 id="inventaire-item-count">
  inventory.itemCount(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre d’objets dans l’inventaire.

**Exemple:**

```js
const nombreBle = inventory.itemCount(289); // Retourne le nombre de blé dans l'inventaire.
```

<hr>

<h2 id="inventaire-item-weight">
  inventory.itemWeight(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le poids d’un item dans l’inventaire.

**Exemple:**

```js
const wheatWeight = inventory.itemWeight(289); // Retourne le poids d'un blé (2).
```

<hr>

<h2 id="inventaire-item-use">
  inventory.useItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, quantity: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser un objet..

**Exemple:**

```js
yield * inventory.useItem(6965); // Utilise une Potion de Cité Bonta.
```

<hr>

<h2 id="inventaire-item-equip">
  inventory.equipItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d'équiper un item.

**Exemple:**

```js
yield * inventory.equipItem(8575); // Equipe votre Ramboton.
```

<hr>

<h2 id="inventaire-item-un-equip">
  inventory.unEquipItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de déséquiper un item.

**Exemple:**

```js
yield * inventory.unEquipItem(7865); // Désequipe votre Dragodinde Squelette.
```

<hr>

<h2 id="inventaire-item-drop">
  inventory.dropItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de jetter un item.

**Exemple:**

```js
yield * inventory.dropItem(289, 50); // Drop 50 blé.
```

<hr>

<h2 id="inventaire-item-delete">
  inventory.deleteItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de supprimer un item.

**Exemple:**

```js
yield * inventory.deleteItem(289, 100); // Supprime 100 blé.
```
