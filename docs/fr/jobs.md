# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Jobs](#jobs)
  - [hasJob](#metier-has-job)
  - [name](#metier-name)
  - [level](#metier-level)
  - [getCollectSkills](#metier-get-collection-skills)
  - [allCollectSkills](#jobsallcollectskills)

# Métiers

Toutes les fonctions relatives aux métiers.

**La liste des jobId se trouve dans [jobs.txt](https://suniron.github.io/docs.celestis/ids/jobs.txt).**

<hr>

<h2 id="metier-has-job">
  api.jobs.hasJob(<code>jobId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

Retourne true si le personnage a le métier, false si il ne l'a pas.

**Exemple:**

```js
const isPaysan = api.jobs.hasJob(28); // vérifie si le personnage a le métier paysan.
```

<hr>

<h2 id="metier-name">
  api.jobs.name(<code>jobId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#String_type">string</a>

Retourne le nom d'un métier.

**Exemple:**

```js
const paysanName = api.jobs.name(28); // paysanName = "Paysan"
```

<hr>

<h2 id="metier-level">
  api.jobs.level(<code>jobId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>

Retourne le niveau d'un métier.

**Exemple:**

```js
const nivPaysan = api.jobs.level(28);
```

<hr>

<h2 id="metier-get-collection-skills">
  api.jobs.getCollectSkills(<code>jobId</code>: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Data_structures#Number_type">number</a>)
</h2>

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>

Retourne un array de toutes les ressources d'un métier donné avec lesquelles le bot peut interagir.

**Exemple:**

```js
const paysanSkills = api.jobs.getCollectSkills(28); // Retourne [38, 39]: le bot peut faucher le Blé et le Houblon.
```

La liste des ressources se trouve dans [resources.txt](https://suniron.github.io/docs.celestis/ids/resources.txt)

<hr>

## api.jobs.allCollectSkills()

- Return type: <a href="https://developer.mozilla.org/fr-Fr/docs/Web/JavaScript/Reference/Global_Objects/Array">number[]</a>

Retourne un array de toutes les ressources que le bot peut récolter.

**Exemple:**

```js
const skills = api.jobs.allCollectSkills(); // Retourne [38, 39, 1]: le bot peut faucher le Blé et le Houblon et couper du Frene.
```
