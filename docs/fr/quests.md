# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Quests](#quests)
  - [isActive](#isactive)
  - [isCompleted](#iscompleted)
  - [currentStep](#currentstep)
  - [objectivesNeeded](#objectivesneeded)
  - [needObjective](#needobjective)

# Quêtes

Fonctions relatives aux quêtes

**Tous les ID sont disponibles dans le fichier [quests.txt](https://suniron.github.io/docs.celestis/ids/quests.txt).**

<h2 id="isactive">
  api.quests.isActive(<code>questId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">Boolean</a>

Retourne true si la quête est active sinon false

```js
const isActive = api.quests.isActive(3); // Return true si la quête "La discorde végétale" est lancée
```

<hr>

<h2 id="iscompleted">
  api.quests.isCompleted(<code>questId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">Boolean</a>

Retourne true si la quête est finie sinon false

```js
const isCompleted = api.quests.isCompleted(3); // Return true si la quête "La discorde végétale" est finie
```

<hr>

<h2 id="currentstep">
  api.quests.currentStep(<code>questId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne l'id de l'étape actuelle de la quête

```js
const currentStep = await api.quests.currentStep(3);
```

<hr>

<h2 id="objectivesneeded">
  api.quests.objectivesNeeded(<code>questId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Array_type">Array<number></a>

Retourne un tableau avec tous les ids d'objectifs a réaliser pour cette quête

```js
const objectivesNeeded = await api.quests.objectivesNeeded(3);
```

<hr>

<h2 id="needobjective">
  api.quests.needObjective(<code>questId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>objectiveId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">Boolean</a>

Retourne true si on a besoin de cet objectif sinon false

```js
const needObjective = await api.quests.needObjective(3, 100);
```

<hr>
