# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

---

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
  - [doneScript](#donescript)
  - [stopScript](#stopscript)
  - [restartScript](#restartscript)
  - [reloadScript](#reloadscript)
  - [delay](#delay)
  - [leaveDialog](#leavedialog)

# Global

Toutes les fonctions utiles en toutes circonstances.

## api.isFighting()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est en combat, sinon retourne false.

**Exemple:**

```js
if (api.isFighting()) {
  api.printMessage("Le personnage est en train de combattre!");
}
```

## api.isGathering()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est en train de récolter, sinon retourne false.

**Exemple:**

```js
if (api.isGathering()) {
  api.printMessage("Le personnage est en train de récolter.");
}
```

## api.isInDialog()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne true si le personnage est dans un dialogue (échange, défi, banque, PNJ, etc…), sinon retourne false.

**Exemple:**

```js
if (api.isInDialog()) {
  api.printMessage("Un dialogue est ouvert !");
}
```

---

<h2 id="printmessage">api.printMessage(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Affiche un message dans la console.

**Exemple:**

```js
api.printMessage("Ceci est un message.");
```

---

<h2 id="printnotify">printNotify(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

**Obsolète?**

Envois une notification de bureau + Affiche un message dans la console.

**Exemple:**

```js
printNotify("Ceci est un message.");
```

---

<h2 id="printtelegram">api.printTelegram(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

Envois une notification Telegram + Affiche un message dans la console.

**Exemple:**

```js
api.printTelegram("Ceci est un message.");
```

---

<h2 id="printdebug">api.printDebug(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

**Obsolète?**

Affiche un message de debug dans la console.

**Exemple:**

```js
api.printDebug("Ceci est un message de debug.");
```

---

<h2 id="printsuccess">api.printSuccess(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

**Obsolète?**

Affiche un succès dans la console.

**Exemple:**

```js
api.printSuccess("Ceci est un message de succès.");
```

---

<h2 id="printerror">api.printError(<code>message</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)</h2>

**Obsolète?**

Affiche une erreur dans la console.

**Exemple:**

```js
api.printError("Ceci est un message d'erreur");
```

---

<h2 id="donescript">yield* api.doneScript(<code>reason?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>, <code>disconnect?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>)</h2>

Stoppe et termine le script immédiatement. (Vous pouvez préciser une raison, et même déconnecter le compte)

**Exemple:**

```js
yield * api.doneScript(); // Arrête le script sans raison et laisse le personnage connecté
yield * api.doneScript("J'ai fini"); // Arrête le script en disant "J'ai fini" et laisse le personnage connecté
yield * api.doneScript("J'ai fini", true); // Arrête le script en disant "J'ai fini" et déconnecte le personnage
```

PS: Si vous aviez la planification d'activé le compte se déconnecte bien et n'essaye pas de se reconnecter instantanément, il va simplement repasser votre heure sur désactivé, et le reactivé à sa prochaine plage de connexion.

---

<h2 id="stopscript">yield* api.stopScript(<code>reason?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>, <code>disconnect?</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>)</h2>

Stoppe et termine le script immédiatement. (Vous pouvez préciser une raison, et même déconnecter le compte)

Cette action est similaire à `api.doneScript()` mais doit être plutôt utilisée lorsque quelque chose s'est mal passé.

**Exemple:**

```js
yield * api.stopScript(); // Arrête le script sans raison et laisse le personnage connecté
yield * api.stopScript("Oups, quelquechose ne s'est pas bien passé! :("); // Arrête le script en affichant un message et laisse le personnage connecté
yield *
  api.stopScript(
    "Il y a un problème dans le script. Je me déconnecte en attendant.",
    true
  ); // Arrête le script en affichant un message et déconnecte le personnage
```

PS: Si vous aviez la planification d'activé le compte se déconnecte bien et n'essaye pas de se reconnecter instantanément, il va simplement repasser votre heure sur désactivé, et le reactivé à sa prochaine plage de connexion.

---

<h2 id="restartscript">api.restartScript()</h2>

Permet de redémarrer le script.

_TODO: définition à finir_

**Exemple:**

```js
api.restartScript(); // redémarre le script
```

---

<h2 id="reloadscript">api.reloadScript()</h2>

Permet de recharger le script.

_TODO: définition à finir_

**Exemple:**

```js
api.reloadScript(); // recharge le script
```

---

<h2 id="delay">api.delay(<code>ms</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)</h2>

Fait une pause dans le script.

**Exemple:**

```js
yield * api.delay(3000); // Fait une pause de 3000ms (3 secondes).
```

---

## api.leaveDialog()

Ferme une boite de dialogue.

**Exemple:**

```js
if (api.isInDialog()) {
  api.printMessage("Un dialogue est ouvert, on le ferme !");
  yield * api.leaveDialog();
}
```

---
