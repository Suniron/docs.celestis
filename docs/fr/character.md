# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

---

## Sommaire

- [Character](#character)
  - [change](#characterchange)
  - [isAlive](#characterisalive)
  - [isTombstone](#characteristombstone)
  - [isPhantom](#characterisphantom)
  - [name](#charactername)
  - [level](#characterlevel)
  - [sex](#charactersex)
  - [lifePoints](#characterlifepoints)
  - [maxLifePoints](#charactermaxlifepoints)
  - [lifePointsP](#characterlifepointsp)
  - [experience](#characterexperience)
  - [energyPoints](#characterenergypoints)
  - [maxEnergyPoints](#charactermaxenergypoints)
  - [energyPointsP](#characterenergypointsp)
  - [kamas](#characterkamas)
  - [serverId](#characterserverid)
  - [serverName](#characterservername)
  - [sit](#charactersit)
  - [freeSoul](#characterfreesoul)

# Personnage

Toutes les fonctions relatives au personnage.

---

<h2 id="characterchange">
  api.character.change(<code>name</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Change de personnage et relance le script (Le personnage doit être sur le même serveur)

**Exemple:**

```js
yield * api.character.change("Michel"); // Se reconnecte sur le personnage du même serveur qui s'appelle Michel, et relance le script
```

---

## api.character.isAlive()

Retourne true si le personnage est en vie, sinon retourne false.

**Exemple:**

```js
if (api.character.isAlive()) {
  // Le personnage est en vie.
}
```

---

## api.character.isTombstone()

Retourne true si le personnage est une tombe, sinon retourne false.

**Exemple:**

```js
if (api.character.isTombstone()) {
  // Le personnage est une tombe.
}
```

---

## api.character.isPhantom()

Retourne true si le personnage est un fantôme, sinon retourne false.

**Exemple:**

```js
if (api.character.isPhantom()) {
  // Le personnage est un fantome.
}
```

---

## api.character.name()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom du personnage.

**Exemple:**

```js
api.character.name();
```

---

## api.character.level()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le niveau du personnage.

**Exemple:**

```js
api.character.level();
```

---

## api.character.sex()

Retourne true si le personnage est un male, false si c'est une femelle.

**Exemple:**

```js
api.character.sex();
```

---

## api.character.breed()

Retourne l'id de la classe du personnage

**Exemple:**

```js
api.character.breed();
```

---

## api.character.lifePoints()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les points de vie du personnage.

**Exemple:**

```js
api.character.lifePoints();
```

---

## api.character.maxLifePoints()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les points de vie maximum du personnage.

**Exemple:**

```js
api.character.maxLifePoints();
```

---

## api.character.lifePointsP()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le pourcentage de vie du personnage.

**Exemple:**

```js
api.character.lifePointsP();
```

---

## api.character.experience()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne l’expérience du personnage.

**Exemple:**

```js
api.character.experience();
```

---

## api.character.energyPoints()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les points d’énergie du personnage.

**Exemple:**

```js
api.character.energyPoints();
```

---

## api.character.maxEnergyPoints()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les points d’énergie maximum du personnage.

**Exemple:**

```js
api.character.maxEnergyPoints();
```

---

## api.character.energyPointsP()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le pourcentage d'energie du personnage.

**Exemple:**

```js
api.character.energyPoints();
```

---

## api.character.kamas()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre de kamas que possède le personnage.

**Exemple:**

```js
api.character.kamas();
```

---

## api.character.serverId()

- Return type: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne l'ID du serveur sur lequel le personnage est connecté.

**Example:**

```js
const id = api.character.serverId();
```

## api.character.serverName()

- Return type: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom du serveur sur lequel le personnage est connecté.

**Example:**

```js
const name = api.character.serverName();
```

## api.character.sit()

Permet au personnage de s’asseoir.

**Exemple:**

```js
api.character.sit();
```

## api.character.freeSoul()

Permet de libérer l’âme du personnage.

Retourne true si le personnage a réussi à libérer son âme, sinon retourne false.

**Exemple:**

```js
if (api.character.isTombstone()) {
  if (api.character.freeSoul()) {
    // Si le personnage est une tombe, alors libère son âme.
    // L'âme a été libérée.
  } else {
    // L'âme n'a pas été libérée.
  }
}
```
