# Egg Milk Tea — Vanilla Ingredients

Version **autonome** du thé au lait de **MengYeYu** (露珠卵龙娘奶茶, Steam
[3542599309](https://steamcommunity.com/sharedfiles/filedetails/?id=3542599309)), rebranchée
sur des ingrédients ordinaires.

## Pourquoi une version séparée, et pas un patch

Le mod d'origine a d'abord été traité en **mod de patchs** — c'était la solution propre : rien
de copié, son mod restait installé et continuait de se mettre à jour.

Ce qui a fait changer d'avis, c'est le bloc **« Éléments requis »** de sa page Workshop :

> Cet article nécessite tous les autres articles suivants
> — 让露珠卵再次伟大！ ([2960593459](https://steamcommunity.com/sharedfiles/filedetails/?id=2960593459))
> — Gloomy Dragonian race ([3373605540](https://steamcommunity.com/sharedfiles/filedetails/?id=3373605540))

**C'est un mécanisme Steam, pas RimWorld.** Son `About.xml` ne déclare aucun
`<modDependencies>` — l'obligation est posée côté Workshop, dans l'interface de Valve, et
Steam abonne d'office aux deux éléments requis. Un patch ne peut rien contre ça : il évite
d'avoir à **charger** les deux races en jeu, mais pas de les **télécharger**.

D'où la version autonome, qui ne dépend plus de son mod du tout.

## Ce qui a changé

| Élément | Origine | Ici |
|---|---|---|
| Œuf | `Axolotl_Egg` | catégorie vanilla **`EggsUnfertilized`** — n'importe quel oiseau, mods compris |
| Lait | `DragonianMilk` | **`Milk`** vanilla, ×4 |
| Textes | chinois, nommant les deux créatures | anglais, + injection française |

**Les quantités :** un œuf vaut 0,25 de nutrition, un lait 0,05. `1 + 4 = 0,45` en entrée pour
**0,4** en sortie — la recette reste à peu près neutre, comme elle l'était.

Un `fixedIngredientFilter` a été ajouté, absent de l'original.

Tout le reste est celui de MengYeYu, inchangé : repas fin, 0,4 de nutrition, 0,3 de loisir,
+8 d'humeur pendant une demi-journée, bonus de conscience et de déplacement, et **sa texture**.

Les `defName` d'origine sont conservés et son mod est déclaré en `<incompatibleWith>` : une
sauvegarde passe de l'un à l'autre sans rien perdre, et les deux ne peuvent pas tourner ensemble.

## Ce que ce mod doit dire, et le dit

La version autonome **se substitue** au mod d'origine au lieu de s'y ajouter : qui installe
celui-ci n'a plus de raison d'installer celui-là. C'est un choix assumé, pas un détail, et la
description le porte en clair :

- le **lien vers son mod en premier**, présenté comme l'original et le plus complet
- « **si vous voulez les deux races, prenez le sien, pas celui-ci** »
- le crédit du graphisme et de la conception
- une **clause de retrait sans condition** : s'il le demande, le mod est dépublié

## Structure

```
MilkTeaVanillaIngredients/
  Mod/          <- le dossier publié. Cible de la jonction.
  Art/          <- les sources d'image en 1254 px, jamais publiées
  README.md
```

Steam envoie `RootDir` **tel quel**, sans exclusion possible : le seul moyen de ne pas publier
les sources est qu'elles n'y soient pas. D'où le `Mod/` séparé.

`Preview.png` est en **640×640 (662 Ko)** et `ModIcon.png` en **128×128 (32 Ko)**. Les deux
sortaient de la génération en 1254 px et pesaient 1,6 et 1,8 Mo — au-dessus de la limite de
1 Mo pour la preview, et absurde pour une icône rendue à 32 px dans la liste des mods.
Les originaux sont conservés dans `Art/`.

## Statut

**Public**, avec la clause de retrait ci-dessus.

**Attention avant le premier envoi Steam :** la description d'`About.xml` n'est transmise qu'à
la **création** de l'item (`SteamUGC.SetItemDescription` n'est appelé que si `creating`). Toute
correction ultérieure se fait à la main sur la page Workshop. À relire avant de cliquer.
