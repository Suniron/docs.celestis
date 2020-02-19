# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Global](#global)
  - [isFighting](#isfighting)
  - [isGathering](#isgathering)
  - [isInDialog](#isindialog)
  - [printMessage](#printmessage)
  - [printBullet](#printbullet)
  - [printNotify](#printnotify)
  - [printTelegram](#printelegram)
  - [printDebug](#printdebug)
  - [printSuccess](#printsuccess)
  - [printError](#printerror)
  - [stopScript](#stopscript)
  - [delay](#delay)
  - [leaveDialog](#leavedialog)

# Global

Toutes les fonctions utiles en toutes circonstances.

## isFighting()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est en combat, sinon retourne false.

**Exemple:**

```js
if (isFighting()) {
  printMessage("Le personnage est en train de combattre!");
}
```

## isGathering()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est en train de récolter, sinon retourne false.

**Exemple:**

```js
if (isGathering()) {
  printMessage("Le personnage est en train de récolter.");
}
```

## isInDialog()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est dans un dialogue (échange, défi, banque, PNJ, etc…), sinon retourne false.

**Exemple:**

```js
if (isInDialog()) {
  printMessage("Un dialogue est ouvert !");
}
```

<hr>

<h2 id="printmessage">printMessage(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Affiche un message dans la console.

**Exemple:**

```js
printMessage("Ceci est un message.");
```

<hr>

<h2 id="printbullet">printBullet(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Envois une notification pushbullet + Affiche un message dans la console.

**Exemple:**

```js
printBullet("Ceci est un message.");
```

<hr>

<h2 id="printnotify">printNotify(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Envois une notification de bureau + Affiche un message dans la console.

**Exemple:**

```js
printNotify("Ceci est un message.");
```

<hr>

<h2 id="printtelegram">printTelegram(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Envois une notification Telegram + Affiche un message dans la console.

**Exemple:**

```js
printTelegram("Ceci est un message.");
```

<hr>

<h2 id="printdebug">printDebug(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Affiche un message de debug dans la console.

**Exemple:**

```js
printDebug("Ceci est un message de debug.");
```

<hr>

<h2 id="printsuccess">printSuccess(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Affiche un succès dans la console.

**Exemple:**

```js
printSuccess("Ceci est un message de succès.");
```

<hr>

<h2 id="printerror">printError(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Affiche une erreur dans la console.

**Exemple:**

```js
printError("Ceci est un message d'erreur");
```

<hr>

<h2 id="stopscript">stopScript(<code>reason?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>, <code>disconnect?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>)</h2>

Stoppe et termine le script immédiatement. (Vous pouvez préciser une raison, et même déconnecter le compte)

**Exemple:**

```js
stopScript(); // Arrête le script sans raison et laisse le personnage connecté
stopScript("J'ai fini"); // Arrête le script en disant "J'ai fini" et laisse le personnage connecté
stopScript("J'ai fini", true); // Arrête le script en disant "J'ai fini" et déconnecte le personnage
```

PS: Si vous aviez la planification d'activé le compte se déconnecte bien et n'essaye pas de se reconnecter instantanément, il va simplement repasser votre heure sur désactivé, et le reactivé à sa prochaine plage de connexion.

<hr>

<h2 id="delay">delay(<code>ms</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Fait une pause dans le script.

**Exemple:**

```js
yield * delay(3000); // Fait une pause de 3000ms (3 secondes).
```

<hr>

## leaveDialog()

Ferme une boite de dialogue.

**Exemple:**

```js
if (isInDialog()) {
  printMessage("Un dialogue est ouvert, on le ferme !");
  yield * leaveDialog();
}
```

<hr>
