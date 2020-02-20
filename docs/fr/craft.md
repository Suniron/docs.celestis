# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Craft](#craft)
  - [craft](#craft)

# Craft

Fonctions relatives aux crafts

<h2 id="craft">api.craft.craft(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>qty</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Craft une quantité d'item

**Exemple:**

```js
function* craftItem() {
  yield* api.use(400); // Utilise l'atelier avec l'action (cuir du pain dans ce cas(-1))
  yield* api.craft.craft(468, 10); // Craft 10 pains d'amakna ( 468 = pain d'amakna )
}
```

<h2 id="craft">api.craft.speedcraft(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>qty</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>delay</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Craft une quantité d'item instantanément.

Un délais (en ms) à attendre entre chaque item doit renseigné mais il peut être de 0 (dans tous les cas une pause de 1s est effectuée toutes les 200ms)

**Exemple:**

```js
function* craftItem() {
  yield* api.use(400); // Utilise l'atelier avec l'action (cuir du pain dans ce cas(-1))
  yield* api.craft.speedcraft(468, 500, 10); // Craft 500 pains d'amakna au rythme d'un craft chaque 10ms ( 468 = pain d'amakna )
}
```

**Tous les GID des items peuvent être trouvés dans [items.txt](https://suniron.github.io/docs.celestis/ids/items.txt)**
