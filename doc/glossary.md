<!--
    created: June 17th, 2024
    updated: June 17th, 2024
-->

# glossary

## gameplay

### entity
an entity is simply just anything that's fully capable of "thought" and performing actions, so anything that's alive really. this includes the player, mobs, and dynamic tiles (like moving platforms)

## tiles

### quarter tile
a quarter tile is simply 1/4th of a full tile

### solid check
the "solid check" is a simple check that occurs whenever an [entity](#entity) wants to know if the [quarter tile](#quarter-tile) they're currently on, is solid or not. if it's not solid, they'll likely fall through it.

### solid threshold
the "solid threshold" is a value given to tiles and [entities](#entity) that the [solid check](#solid-check) mainly relies on.

if a tile's solid threshold is greater than the entity's solid threshold, the solid check will pass. otherwise, it'll fail.