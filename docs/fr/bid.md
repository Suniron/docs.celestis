# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [BID](#bid)
  - [startBuying](#bidstartbuying)
  - [buyItem](#hdv-buy-item)
  - [startSelling](#bidstartselling)
  - [itemsInSaleCount](#biditemsInSaleCount)
  - [getItemPrice](#hdv-get-item-price)
  - [getItemsInSale](#bidgetitemsinsale)
  - [sellItem](#hdv-sell-item)
  - [editItemInSalePrice](#hdv-edit-item-in-sale-price)
  - [removeItemsInSale](#hdv-remove-item-in-sale)

# HDV

Toutes les fonctions relatives à l'hotel de vente.

Les lots peuvent etre egaux à 1, 10 ou 100.

<hr>

## api.bid.startBuying()

Active l'achat dans l'hdv, doit etre executé avant d'acheter des items.

**Exemple:**

```js
yield * api.bid.startBuying(); // Active l'achat.
```

<hr>

<h2 id="hdv-buy-item">
  api.bid.buyItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>lot</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d'acheter un lot d'item donné.

**Exemple:**

```js
yield * api.bid.startBuying(); // Active l'achat.
yield * api.bid.buyItem(423, 10); // Achète 10 Lin.
```

<hr>

<h2 id="hdv-get-item-price">
  api.bid.getItemPrice(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>lot</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le prix d'un lot d'item en vente.

**Exemple:**

```js
const prixBle = await api.bid.getItemPrice(289, 100); // Retourne le prix du lot de 100 blé.
```

<hr>

## api.bid.startSelling()

Active la vente dans l'hotel de vente, doit etre executé avant toutes les fonctions ci-dessous.

**Exemple:**

```js
yield * api.bid.startSelling(); // Active la vente.
```

<hr>

## api.bid.itemsInSaleCount()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le nombre d'items en vente.

**Exemple:**

```js
const itemsInSale = api.bid.itemsInSaleCount();
```

<hr>

## api.bid.getItemsInSale()

- Return type: <a href="http://flaviocorpa.com/linq.ts/docs/classes/list/index.html">List<{ gid: number; uid: number; lot: number; price: number }></a>

Retourne une liste de lots d'objets en vente et le prix du lot.

**Exemple:**

```js
for (const itemInSale of api.bid.getItemsInSale()) {
  const gid = itemInSale.objectGID;
  const uid = itemInSale.objectUID;
  const lot = itemInSale.lot;
  const price = itemInSale.price;
}
```

<h2 id="hdv-sell-item">
  api.bid.sellItem(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>lot</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>price</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de vendre un lot d'un item donné à un prix donné.

**Exemple:**

```js
yield * api.bid.sellItem(289, 100, 200); // Vend 100 blé pour 200 kamas.
```

<hr>

<h2 id="hdv-edit-item-in-sale-price">
  api.bid.editItemInSalePrice(<code>uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>newPrice</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet d'éditer le prix d'un item donné en vente.

**Exemple:**

```js
for (const itemInSale of api.bid.getItemsInSale()) {
  if (
    itemInSale.objectGID === 289 &&
    itemInSale.price <= 1000 &&
    itemInSale.lot <= 100
  ) {
    yield * api.bid.editItemInSalePrice(itemInSale.objectUID, 1200); // On augmente le prix des lots de 100 blé.
  }
}
```

_Le uid peut etre trouvé dans [getItemsInSale](#bidgetitemsinsale). Il est unique à chaque item (ou lot d'item)._

<hr>

<h2 id="hdv-remove-item-in-sale">
  api.bid.removeItemInSale(<code>uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Retire un item donné de la vente.

**Exemple:**

```js
for (const itemInSale of bid.getItemsInSale()) {
  if (itemInSale.objectGID === 289) {
    yield * bid.removeItemInSale(itemInSale.objectUID); // On retire tous les lots de blé de la vente.
  }
}
```

_Le uid peut etre trouvé dans [getItemsInSale](#bidgetitemsinsale). Il est unique à chaque item (ou lot d'item)._
