<!--
    created: June 17th, 2024
    updated: December 22nd, 2024
-->

# glossary

## gameplay

### entity
*see also: [entity.md](./entity.md)*

a game object that exists separately from the rest of a level, usually with the ability to think and interact with other entities.

## technical

### quarter tile
a quarter tile is simply 1/4th of a full tile.

### solid check
the "solid check" is a simple check that occurs whenever an [entity](#entity) wants to know if the [quarter tile](#quarter-tile) they're currently on, is solid or not. if it's not solid, they'll likely fall through it.

### solid threshold
the "solid threshold" is a value given to tiles and [entities](#entity) that the [solid check](#solid-check) mainly relies on.

if a tile's solid threshold is greater than the entity's solid threshold, the solid check will pass. otherwise, it'll fail.

### mask visual
*see also: [tile-mask.md](./tile-mask.md)*

a mask visual is a visual representation of information contained in a tile mask