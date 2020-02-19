# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Exchange](#exchange)
  - [weightP](#exchangeweightp)
  - [targetWeightP](#exchange-target-weight-p)
  - [startExchange](#exchange-start-exchange)
  - [sendReady](#exchangesendready)
  - [putItem](#exchange-put-item)
  - [removeItem](#exchange-remove-item)
  - [putKamas](#exchange-put-kamas)
  - [removeKamas](#exchange-remove-kamas)
  - [putAllItems](#exchangeputallitems)
  - [removeAllItems](#exchangeremoveAllItems)
  - [startShop](#exchangestartshop)
  - [addItemShop](#exchangeadditemshop)

# Exchange

Toutes les fonctions relatives aux échanges.

## exchange.weightP

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les pods actuel du bot en pourcentage.

**Exemple:**

```js
while (exchange.weightP() > 10) {
  yield * exchange.putItem(289, 100); // Tant que vous avez plus de 10% de pods, ajoute 100 blé à l'échange.
}
```

<hr>

<h2 id="exchange-target-weight-p">exchange.targetWeightP</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne les pods actuel de la cible de l’échange en pourcentage.

**Exemple:**

```js
while (exchange.targetWeightP() < 90) {
  yield * exchange.putItem(289, 100); // Tant que la cible n'a pas plus de 90% de pods, ajoute 100 blé à l'échange.
}
```

<hr>

<h2 id="exchange-start-exchange">exchange.startExchange(<code>playerId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Commence l'échange avec un joueur donné.

```js
yield * exchange.startExchange(7127912);
```

_Note: il est possible de récupérer le playerId à coté de votre nom dans l'onglet personnage._

<hr>

## exchange.sendReady()

Valide l'échange.

```js
yield * exchange.sendReady();
```

<hr>

<h2 id="exchange-put-item">exchange.putItem(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Insère un objet dans l’échange.

```js
yield * exchange.putItem(289, 100); // quantity = 0 pour tout mettre.
```

<hr>

<h2 id="exchange-remove-item">exchange.removeItem(<code>gid/uid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Récupère un objet dans l’échange.

```js
yield * exchange.removeItem(289, 100); // Enlève 100 blé à l'échange.
```

<hr>

<h2 id="exchange-put-kamas">exchange.putKamas(<code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Insère une quantité donnée de kamas dans l’échange.

```js
yield * exchange.putKamas(10000); // Ajoute 10 000 kamas à l'échange.
```

<hr>

<h2 id="exchange-remove-kamas">exchange.removeKamas(<code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Retire une quantité donnée de kamas dans l'échange.

```js
yield * exchange.removeKamas(10000); // Retire 10 000 kamas à l'échange.
```

<hr>

## exchange.putAllItems()

Insère tous les objets de votre inventaire dans l’échange.

```js
yield * exchange.putAllItems();
```

<hr>

## exchange.removeAllItems()

Retire tous les items de l'échange.

```js
yield * exchange.removeAllItems();
```

<hr>

## exchange.startShop()

Démarre votre mode marchand

```js
yield * exchange.startShop();
```

<hr>

<h2 id="exchangeadditemshop">exchange.addItemShop(<code>gid</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>quantity</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>, <code>price</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Ajoute un item à votre mode marchand

```js
yield * exchange.addItemShop(289, 10, 20); // Ajoute 10 blé à 20k/u à votre mode marchand
```

<hr>
