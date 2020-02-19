# CookieTouch API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Craft](#craft)
  - [craft](#craft)

# Craft

Fonctions relatives aux crafts

<h2 id="craft">craft(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>qty</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Craft une quantité d'item

**Exemple:**

```js
function* craftItem() {
  yield* use(400); // Utilise l'atelier avec l'action (cuir du pain dans ce cas(-1))
  yield* craft.craft(468, 10); // Craft 10 pain d'amakna ( 468 = pain d'amakna )
}
```

**Tous les GID des items peuvent être trouvés dans [items.txt](https://docs.cookietouch.com/ids/items.txt)**
