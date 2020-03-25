# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

---

## Sommaire

- [Merchants](merchants)
  - [open](#merchantsopen)
  - [objectsInShop](#merchantsobjectsinshop)
  - [buy](#merchantsbuy)

# Merchants

Toutes les fonctions relatives au mode marchand

---

<h2 id="merchantsopen">
  api.merchants.open(<code>cellId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Ouvre un mode marchand sur la cellule précisée

```js
yield * api.merchants.open(320); // Ouvre le mode marchand de la cellule 320
```

---

## api.merchants.objectsInShop()

Retourne tous les objets présent dans le mode marchand

---

<h2 id="merchantsbuy">
  api.merchants.buy(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Achète un objet en quantité demandé dans le mode marchand

```js
yield * api.merchants.buy(289, 2); // Achète 2 blé dans le mode marchand
```

---
