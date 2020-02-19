# CookieTouch API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Mount](mount)
  - [isRiding](#mountisriding)
  - [hasMount](#mounthasmount)
  - [currentLevel](#mountcurrentlevel)
  - [currentRatio](#mountcurrentratio)
  - [id](#mountid)
  - [sex](#mountsex)
  - [toggleRiding](#mount-toggle-riding)
  - [setRatio](#mount-set-ratio)
  - [setName](#mount-set-name)

# Monture

Toutes les fonctions relatives à la monture du personnage.

<hr>

## mount.isRiding()

Retourne true si le personnage est sur la monture, sinon retourne false.

<hr>

## mount.hasMount()

Retourne true si le personnage possède une monture, sinon retourne false.

<hr>

## mount.currentRatio()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le pourcentage d'experience donnée à la monture.

<hr>

## mount.id()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne l'id de la monture.

<hr>

## mount.sex()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Boolean_type">boolean</a>

Retourne le sexe de la monture (true = femelle / false = male)

<hr>

## mount.currentLevel()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le level de la monture.

<hr>

<h2 id="mount-toggle-riding">
  mount.toggleRiding()
</h2>

Permet de descendre ou de monter sur la monture.

**Exemple:**

```js
if (!mount.isRiding()) {
  yield * mount.toggleRiding(); // Si le personnage n'est pas sur la monture, alors monter sur la monture.
  yield * delay(2000);
}
```

_Astuce : Une fois la fonction appelée, il faut entre une seconde et une seconde et-demi pour que l’action soit effective.
Si vous devez obligatoirement être sûr d’être monté/descendu de la monture pour continuer, vous pouvez utiliser delay(2000) après toggleRiding()._

<hr>

<h2 id="mount-set-ratio">
  mount.setRatio(<code>ratio</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Permet de modifier le pourcentage d'experience donnée à la monture.

**Exemple:**

```js
yield * mount.setRatio(90);
```

<hr>

<h2 id="mount-set-name">
  mount.setName(<code>name</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>)
</h2>

Permet de modifier le nom de la monture.

**Exemple:**

```js
yield * mount.setName("Jacquie");
```

<hr>
