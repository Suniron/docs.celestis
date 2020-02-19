# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Map](#map)
  - [changeMap](#map-change-map)
  - [moveToCell](#map-move-to-cell)
  - [useById](#map-use-by-id)
  - [use](#map-use)
  - [useLockedHouse](#map-use-locked-house)
  - [useLockedStorage](#map-use-locked-storage)
  - [useZaap](#map-use-zaap)
  - [useZaapi](#map-use-zaapi)
  - [usePaddock](#map-use-paddock)
  - [useWell](#map-use-well)
  - [saveZaap](#savezaap)
  - [waitMapChange](#map-wait-map-change)
  - [joinFriend](#map-join-friend)
  - [onCell](#map-on-cell)
  - [currentCell](#map-current-cell)
  - [onMap](#map-on-map)
  - [currentPos](#currentpos)
  - [currentMapId](#currentmapid)
  - [area](#area)
  - [subArea](#subarea)
  - [monstersGroups](#monstersgroups)

# Map

Toutes les fonctions relatives aux maps.

Les cellId vont de 0 à 559, vous pouvez les afficher dans l'onglet Map de Celestis.

<hr>

<h2 id="map-change-map">
  changeMap(<code>where</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet de changer de carte. Les directions suivantes sont acceptées:

- `top` pour aller vers le haut.
- `bottom` pour aller vers le bas.
- `right` pour aller vers la droite.
- `left` pour aller vers la gauche.

**Exemple:**

```js
yield * changeMap("right"); // Change de map vers la droite
```

<hr>

<h2 id="map-move-to-cell">
  moveToCell(<code>cellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de se déplacer sur une cellule. Les cellId vont de 0 à 559, vous pouvez les afficher dans l'onglet Map de Celestis.

**Exemple:**

```js
yield * moveToCell(200); // Se déplace sur la cellulle 200
```

<hr>

<h2 id="map-use-by-id">
  useById(<code>elementId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, skillInstanceUid?: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser une action d’un élement interactif à partir de son identifiant.

**Exemple:**

```js
yield * useById(1545));
```

<hr>

<h2 id="map-use">
  use(<code>elementCellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, skillInstanceUid?: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser une action d’un élement interactif sur une cellule donnée.

**Exemple:**

```js
yield * use(400);
```

<hr>

<h2 id="useemote">
  useEmote(<code>id</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser une émote.

**Exemple:**

```js
useEmote(8); // Utile l"émote "Péter"
```

<hr>

<h2 id="map-use-locked-house">
  useLockedHouse(<code>doorCellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, lockCode: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet d’utiliser une porte de maison protégée par un code.

**Exemple:**

```js
yield * useLockedHouse(239, "00000000"); // Ouvre la porte en cellule 239 avec le code 00000000.
```

<hr>

<h2 id="map-use-locked-storage">
  useLockedStorage(<code>elementCellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, lockCode: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet d’utiliser un coffre de maison protégé par un code.

**Exemple:**

```js
yield * useLockedStorage(127, "00000000"); // Ouvre le coffre en cellule 127 avec le code 00000000.
```

<hr>

<h2 id="map-use-zaap">
  useZaap(<code>destinationMapId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser un zaap.

**Exemple:**

```js
yield * useZaap(2545); // se téléporte sur le zaap de la map 2545.
```

<hr>

<h2 id="map-use-zaapi">
  useZaapi(<code>destinationMapId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser un zaapi.

**Exemple:**

```js
yield * useZaapi(3545); // se téléporte sur le zaapi de la map 3545.
```

<hr>

<h2 id="map-use-paddock">
  usePaddock()
</h2>

Permet d’utiliser l'enclos de la map.

**Exemple:**

```js
yield * usePaddock(); // ouvre l'enclos présent sur la map
```

<hr>

<h2 id="map-use-well">
  useWell()
</h2>

Permet de récolter le puit de la map.

**Exemple:**

```js
yield * useWell(); // récolte le puit présent sur la map
```

<hr>

## saveZaap()

Permet de sauvegarder un zaap pour l’utiliser comme position par défaut de réapparition de votre personnage.

**Exemple:**

```js
if (onMap("0,-2")) {
  yield * saveZaap(); // Sauvegarde le Zaap en "0,-2".
}
```

<hr>

<h2 id="map-wait-map-change">
  waitMapChange(<code>delay?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Met le script en pause jusqu’au prochain changement de map.

**Exemple:**

```js
yield * waitMapChange(2000); // Attend 2 secondes.
```

<hr>

<h2 id="map-join-friend">
  joinFriend(<code>name</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Vous permet de rejoindre un ami. Disponible seulement si vous êtes à Incarnam.

**Exemple:**

```js
yield * joinFriend("DevChris"); // Se téléporte sur le personnage nommé "DevChris"
```

<hr>

<h2 id="map-on-cell">
  onCell(<code>cellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est sur la cellule, sinon retourne false.

**Exemple:**

```js
printMessage("Je suis sur la cell 210 ? -> " + onCell(210)); // Affiche "Je suis sur la cell 210 -> false" si vous n'êtes pas sur la cell 210
```

<hr>

<h2 id="map-current-cell">
  currentCell()
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne l'id de la celle actuelle du personnage

**Exemple:**

```js
printMessage("Je suis sur la cell " + currentCell()); // Affiche "Je suis sur la cell 210" si vous êtes sur la cell 210
```

<hr>

<h2 id="map-on-map">
  onMap(<code>coords</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est sur la map donnée, sinon retourne false.

**Exemple:**

```js
if (onMap("-2,0")) {
  // You are in "-2.0".
}
```

<hr>

## currentPos()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne les coordonnées de la map actuelle.

**Exemple:**

```js
onMap(currentPos()); // Retourne toujours true.
```

<hr>

## currentMapId()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne la mapId de la map actuelle.

**Exemple:**

```js
if (currentMapId() === 88081177) {
  // 88081177 est la map exterieure "9,2".
  yield * useLockedHouse(cellid, 00000000); // Lorsque le bot arrive sur la map de votre maison, entrer dans la maison.
}
```

<hr>

## area()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom de la zone.

**Exemple:**

```js
if (area() === "Astrub") {
  // Nous sommes dans la zone Astrub.
}
```

<hr>

## subArea

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom de la sous-zone.

**Exemple:**

```js
if (subArea() === "Cité d'Astrub") {
  // Nous sommes à l'intérieur de la ville d'Astrub.
}
```

<hr>

## monstersGroups

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne les groupes de monstres présent sur la map.

**Exemple:**

```js
const groups = monstersGroups();
```
