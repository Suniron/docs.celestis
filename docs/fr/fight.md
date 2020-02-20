# Celestis API Documentation

[Sommaire](README.md) | [Sommaire détaillé](singlepage.md)

<hr>

## Sommaire

- [Fight](#fight-somm)
  - [canFight](#fight-can-fight)
  - [fight](#fight-fight)
  - [fightsCount](#fight-fightscount)

<h2 id ="fight-somm">Fight</h2>

Toutes les fonctions relatives aux combats.

Pour les deux fonctions les paramètres sont tous facultatifs:

<table>
<thead>
<tr>
<th>Paramètres</th>
<th>Types</th>
<th>Valeur initiale</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>FORBIDDEN_MONSTERS</td>
<td>number[]</td>
<td>[]</td>
<td>Liste d’IDs de monstres interdits</td>
</tr>
<tr>
<td>MANDATORY_MONSTERS</td>
<td>number[]</td>
<td>[]</td>
<td>Liste d’IDs de monstres obligatoires</td>
</tr>
<tr>
<td>MIN_MONSTERS</td>
<td>number</td>
<td>1</td>
<td>Nombre de monstres minimum dans le groupe</td>
</tr>
 <tr>
<td>MAX_MONSTERS</td>
<td>number</td>
<td>8</td>
<td>Nombre de monstres maximum dans le groupe</td>
</tr>
<tr>
<td>MIN_MONSTERS_LEVEL</td>
<td>number</td>
<td>1</td>
<td>Niveau minimum du groupe de monstres</td>
</tr>
<tr>
<td>MAX_MONSTERS_LEVEL</td>
<td>number</td>
<td>1000</td>
<td>Niveau maximum du groupe de monstres</td>
</tr>
<tr>
<td>MIN_XP_PER_FIGHT</td>
<td>number</td>
<td>0</td>
<td>Minimum d'xp que doit donner le groupe de monstres</td>
</tr>
<tr>
<td>MAX_XP_PER_FIGHT</td>
<td>number</td>
<td>Infinity</td>
<td>Maximum d'xp que doit donner le groupe de monstres</td>
</tr>
</tbody>
</table>

**Exemple:**
_Dans cet exemple, nous initialisons tout se qui concerne les combats dans la config._

```js
api.config = {
  MIN_MONSTERS: 1,
  MAX_MONSTERS: 8,
  MIN_MONSTERS_LEVEL: 1,
  MAX_MONSTERS_LEVEL: 1000,
  MIN_XP_PER_FIGHT: 0,
  MAX_XP_PER_FIGHT: Infinity,
  FORBIDDEN_MONSTERS: [],
  MANDATORY_MONSTERS: []
};
```

<hr>

<h2 id ="fight-can-fight">canFight(<code>forbiddenMonsters</code>, <code>mandatoryMonsters</code>, <code>minMonsters</code>, <code>maxMonsters</code>, <code>minLevel</code>, <code>maxLevel</code>, <code>minXp</code>, <code>maxXp</code>)</h2>

Verifie si un groupe de monstres de la map correspond aux paramètres passés à la fonction.

```js
api.canFight([64], [68], 2, 6, 200, 600, 800, 1000); // Vérifie si, sur cette map, le bot peut combattre un groupe de 2 à 6 mobs avec un Wabbit au minimum et aucun Black Tiwabbit. Le groupe doit avoir un niveau supérieur ou égal à 200 et inférieur ou égal à 600 qui donne entre 800 et 1000 XP sans challenges.
```

<hr>
<h2 id ="fight-fight">fight(<code>forbiddenMonsters</code>, <code>mandatoryMonsters</code>, <code>minMonsters</code>, <code>maxMonsters</code>, <code>minLevel</code>, <code>maxLevel</code>, <code>minXp</code>, <code>maxXp</code>)</h2>

Lance un combat sur un groupe qui correspond aux paramètres passés à la fonction.

```js
yield * api.fight([], [], 2, 6, 200, 600, 800, 1000); // Attaque si, sur cette map, un groupe vérifie les paramètres: un groupe de 2 à 6 mobs avec un Wabbit au minimum et aucun Black Tiwabbit. Le groupe doit avoir un niveau supérieur ou égal à 200 et inférieur ou égal à 600 qui donne entre 800 et 1000 XP sans challenges.
```

<hr>
<h2 id ="fight-fightscount">fightsCount()</h2>

Retourne le nombre de combats fait durant la session.

```js
api.printMessage("J'ai fait " + api.fightsCount() + " combats :)"); // Affiche: J'ai fait 10 combats :) par exemple
```
