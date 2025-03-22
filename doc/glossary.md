<!--
    created: June 17th, 2024
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

a mask visual is a visual representation of information contained in a tile mask.

the flags at the bottom of a mask visual are small indicators of a tile's properties. so, the *Hue* (H) flag indicates the tile will be tinted by the level hues (`HUE` & `HUE #2`), the *Visible* (V) flag indicates the tile will be visible in-game, and the *Entity* (E) flag indicates the tile will spawn an entity.

the icons representing the different kinds of quarter tiles also have their own meanings as well.

icon | name | meaning
---- | ---- | -------
|| blank | this quarter tile is non-solid and does nothing
![solid](../res/icons/solid.png) | solid  | this quarter tile is solid
![danger](../res/icons/danger.png) | danger | this quarter tile can hurt the player
![conveyor](../res/icons/conveyor.png) | conveyor | this quarter tile will move the player like a conveyor belt
![active](../res/icons/active.png) | active | this quarter tile will activate a full tile upon touch (crumbling platforms, launching springs, opening doors, or triggering groups)
![stop](../res/icons/stop.png) | stop | this quarter tile stops enemies and lifts from passing through
![collect](../res/icons/collect.png) | collect | unused, but was seemingly only used for apples