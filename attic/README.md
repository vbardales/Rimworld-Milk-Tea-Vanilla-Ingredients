# Attic

## `MilkTea-patch-version.xml`

The **patch mod** version, abandoned in favour of the standalone one.

It rewrote the ingredients of MengYeYu's recipe by xpath, copying nothing from their mod —
technically the cleaner answer. What killed it was the **Required Items** block on their
Workshop page, which subscribes you to the two race mods automatically. A patch spares you
having to *load* the two races in a save, not having to *download* them. See the
[README](../README.md).

Kept in case the approach becomes the right one again — if MengYeYu ever drops the required
items, patching beats rebuilding.

Its eleven operations were each resolved against the source mod's defs before it was retired:
every one of them hit exactly one target.

**This folder is not published** — only `Mod/` is.
