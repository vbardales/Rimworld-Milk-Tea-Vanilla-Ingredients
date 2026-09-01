# Egg Milk Tea — Vanilla Ingredients

A standalone rebuild of **MengYeYu's** egg milk tea (露珠卵龙娘奶茶, Steam
[3542599309](https://steamcommunity.com/sharedfiles/filedetails/?id=3542599309)), rebased on
ordinary ingredients.

**Theirs is the original.** The drink, its artwork and its design are their work, and the tea
here is still shown with the texture they drew. If you want the two race mods, use their mod
and not this one — it is the fuller version and it will keep being updated.

## Why a separate mod, and not a patch

This started as a **patch mod**, which was the cleaner answer: nothing copied, the original
stayed installed and kept receiving updates.

What changed the decision was the **Required Items** block on the Workshop page:

> This item requires all of the following also
> — 让露珠卵再次伟大！ ([2960593459](https://steamcommunity.com/sharedfiles/filedetails/?id=2960593459))
> — Gloomy Dragonian race ([3373605540](https://steamcommunity.com/sharedfiles/filedetails/?id=3373605540))

**That is a Steam mechanism, not a RimWorld one.** The mod's `About.xml` declares no
`<modDependencies>` at all — the requirement is set on Valve's side, in the Workshop interface,
and Steam subscribes you to both automatically. A patch can stop you having to *load* the two
races in a save; it cannot stop you having to *download* them.

Hence a standalone version, which depends on the original mod not at all.

The patch version is kept in [`attic/`](attic/) — if MengYeYu ever drops the required items, it
becomes the better answer again.

## What changed

| | Original | Here |
|---|---|---|
| Egg | `Axolotl_Egg` | vanilla **`EggsUnfertilized`** category — any bird, including modded ones |
| Milk | `DragonianMilk` | vanilla **`Milk`**, ×4 |
| Text | Chinese, naming the two creatures | English, with a French translation included |

**On the amounts:** an egg is 0.25 nutrition and a milk is 0.05, so `1 + 4 = 0.45` going in for
**0.4** coming out. The recipe stays roughly neutral, as it was.

A `fixedIngredientFilter` was added, which the original did not have. Without one, players who
do have the two race mods installed would still be offered the axolotl egg and the dragonian
milk in the bill's filter, which the recipe no longer accepts.

Everything else is MengYeYu's, untouched: fine meal, 0.4 nutrition, 0.3 joy, +8 mood for half a
day, a buff to consciousness and moving — and **their texture**.

Original defNames are kept and their mod is declared in `<incompatibleWith>`: a save moves
between the two without losing anything, and the two cannot run together.

## What this mod owes, and says

A standalone version **replaces** the original rather than adding to it: anyone who installs
this one has no reason left to install that one. That is a deliberate choice, not a detail, and
the mod description carries it in plain sight:

- **the link to their mod first**, presented as the original and the fuller one
- *"if you do want them, use theirs and not this one"*
- credit for the artwork and the design
- an **unconditional takedown clause** — if MengYeYu asks, the mod comes down, no argument

## Layout

```
MilkTeaVanillaIngredients/
  Mod/          <- the published folder. Target of the junction.
  Art/          <- 1254px image sources, never published
  attic/        <- the abandoned patch version, never published
  README.md
```

Steam uploads `RootDir` **as-is**, with no way to exclude anything — the only way not to publish
your sources is for them not to be there. Hence the separate `Mod/`.

`Preview.png` is **640×640 (662 KB)** and `ModIcon.png` is **128×128 (32 KB)**. Both came out of
generation at 1254px weighing 1.6 and 1.8 MB — over the 1 MB preview limit, and absurd for an
icon rendered at 32px in the mod list. The originals are kept in `Art/`.

## Status

**Public**, under the takedown clause above.

**Before the first Steam upload:** the `About.xml` description is only sent when the item is
**created** — `SteamUGC.SetItemDescription` is called only `if (creating)`. Every later update
leaves it alone, and any correction has to be made by hand on the Workshop page. Read it once
more before clicking.
