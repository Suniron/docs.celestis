# CookieTouch API Documentation

[Summary](README.md) | [Single page summary](singlepage.md)

<hr>

## Sommaire

- [Gather](#fight)
  - [canGather](#gather-can-gather)
  - [gather](#gather-gather)
  - [gather](#gather-gatherscount)

# Récolte

Toutes les fonctions relatives à la récolte.

**Les resourcesIds se trouvent dans [resources.txt](https://docs.cookietouch.com/ids/resources.txt).**

<hr>

<h2 id="gather-can-gather">
  canGather(<code>...resourcesIds</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Vérifie si il est possible de récolter la ou les ressources choisies en paramètre.

Retourne true si la map contient les ressources recherchées, sinon retourne false.

**Exemple:**

```js
canGather(1, 28); // True si il est possible de recolter du Frene et/ou de l'If sur cette map.
// ou
canGather(...[1, 28]);
```

<hr>

<h2 id="gather-gather">
  gather(<code>jobId?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>...resourcesIds</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>)
</h2>

Récolte les ressources passées en paramètre après avoir vérifié si il etait possible de récolter la ou les ressources choisies en paramètre.

**Exemple:**

```js
yield * gather(1, 28); // Récolte le Frene et/ou l'If si ils sont présents sur la map.
// ou
yield * gather(...[1, 28]);
// ou
yield * gather(26, 46); // Récolte du Chanvre (46) en tant qu'Alchimiste (26)
```

<hr>
<h2 id ="gather-gatherscount">gathersCount()</h2>

Retourne le nombre de récoltes fait durant la session.

```js
printMessage("J'ai fait " + gathersCount() + " récoltes :)"); // Affiche: J'ai fait 10 récoltes :) par exemple
```
