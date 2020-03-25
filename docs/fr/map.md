# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

---

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

---

<h2 id="map-change-map">
  api.changeMap(<code>where</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet de changer de carte. Les directions suivantes sont acceptées:

- `top` pour aller vers le haut.
- `bottom` pour aller vers le bas.
- `right` pour aller vers la droite.
- `left` pour aller vers la gauche.

**Exemple:**

```js
yield * api.changeMap("right"); // Change de map vers la droite
```

---

<h2 id="map-move-to-cell">
  api.moveToCell(<code>cellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de se déplacer sur une cellule. Les cellId vont de 0 à 559, vous pouvez les afficher dans l'onglet Map de Celestis.

**Exemple:**

```js
yield * api.moveToCell(200); // Se déplace sur la cellulle 200
```

---

<h2 id="map-use-by-id">
  api.useById(<code>elementId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, skillInstanceUid?: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser une action d’un élement interactif à partir de son identifiant.

**Exemple:**

```js
yield * api.useById(1545));
```

---

<h2 id="map-use">
  api.use(<code>elementCellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, skillInstanceUid?: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser une action d’un élement interactif sur une cellule donnée.

**Exemple:**

```js
yield * api.use(400);
```

---

<h2 id="useemote">
  api.useEmote(<code>id</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser une émote.

**Exemple:**

```js
api.useEmote(8); // Utile l"émote "Péter"
```

---

<h2 id="map-use-locked-house">
  api.useLockedHouse(<code>doorCellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, lockCode: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet d’utiliser une porte de maison protégée par un code.

**Exemple:**

```js
yield * api.useLockedHouse(239, "00000000"); // Ouvre la porte en cellule 239 avec le code 00000000.
```

---

<h2 id="map-use-locked-storage">
  api.useLockedStorage(<code>elementCellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, lockCode: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet d’utiliser un coffre de maison protégé par un code.

**Exemple:**

```js
yield * api.useLockedStorage(127, "00000000"); // Ouvre le coffre en cellule 127 avec le code 00000000.
```

---

<h2 id="map-use-zaap">
  api.useZaap(<code>destinationMapId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser un zaap.

**Exemple:**

```js
yield * api.useZaap(2545); // se téléporte sur le zaap de la map 2545.
```

---

<h2 id="map-use-zaapi">
  api.useZaapi(<code>destinationMapId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d’utiliser un zaapi.

**Exemple:**

```js
yield * api.useZaapi(3545); // se téléporte sur le zaapi de la map 3545.
```

---

<h2 id="map-use-paddock">
  api.usePaddock()
</h2>

Permet d’utiliser l'enclos de la map.

**Exemple:**

```js
yield * api.usePaddock(); // ouvre l'enclos présent sur la map
```

---

<h2 id="map-use-well">
  api.useWell()
</h2>

Permet de récolter le puit de la map.

**Exemple:**

```js
yield * api.useWell(); // récolte le puit présent sur la map
```

---

## api.saveZaap()

Permet de sauvegarder un zaap pour l’utiliser comme position par défaut de réapparition de votre personnage.

**Exemple:**

```js
if (onMap("0,-2")) {
  yield * api.saveZaap(); // Sauvegarde le Zaap en "0,-2".
}
```

---

<h2 id="map-wait-map-change">
  api.waitMapChange(<code>delay?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Met le script en pause jusqu’au prochain changement de map.

**Exemple:**

```js
yield * api.waitMapChange(2000); // Attend 2 secondes.
```

---

<h2 id="map-join-friend">
  api.joinFriend(<code>name</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Vous permet de rejoindre un ami. Disponible seulement si vous êtes à Incarnam.

**Exemple:**

```js
yield * api.joinFriend("Suniron"); // Se téléporte sur le personnage nommé "Suniron"
```

---

<h2 id="map-on-cell">
  onCell(<code>cellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est sur la cellule, sinon retourne false.

**Exemple:**

```js
api.printMessage("Je suis sur la cell 210 ? -> " + api.onCell(210)); // Affiche "Je suis sur la cell 210 -> false" si vous n'êtes pas sur la cell 210
```

---

<h2 id="map-current-cell">
  currentCell()
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne l'id de la celle actuelle du personnage

**Exemple:**

```js
api.printMessage("Je suis sur la cell " + api.currentCell()); // Affiche "Je suis sur la cell 210" si vous êtes sur la cell 210
```

---

<h2 id="map-on-map">
  api.onMap(<code>coords</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est sur la map donnée, sinon retourne false.

**Exemple:**

```js
if (api.onMap("-2,0")) {
  // You are in "-2.0".
}
```

---

## currentPos()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne les coordonnées de la map actuelle.

**Exemple:**

```js
api.onMap(api.currentPos()); // Retourne toujours true.
```

---

## api.currentMapId()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne la mapId de la map actuelle.

**Exemple:**

```js
if (api.currentMapId() === 88081177) {
  // 88081177 est la map exterieure "9,2".
  yield * api.useLockedHouse(cellid, 00000000); // Lorsque le bot arrive sur la map de votre maison, entrer dans la maison.
}
```

---

## api.area()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom de la zone.

**Exemple:**

```js
if (api.area() === "Astrub") {
  // Nous sommes dans la zone Astrub.
}
```

---

## api.subArea

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom de la sous-zone.

**Exemple:**

```js
if (api.subArea() === "Cité d'Astrub") {
  // Nous sommes à l'intérieur de la ville d'Astrub.
}
```

---

## api.monstersGroups

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array</a>

Retourne les groupes de monstres présent sur la map.

**Exemple:**

```js
const groups = api.monstersGroups();
```
