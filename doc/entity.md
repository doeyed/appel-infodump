<!--
    created: June 19th, 2024
    updated: December 23rd, 2024
-->

# entity
an **entity** is a game object that exists separately from the rest of a level, usually with the ability to think and interact with other entities. this would allow the player, enemies, collectables, lifts (moving platforms), and anything else, may also be considered an entity.

when a level starts, every entity in the level will be spawned in. once an entity spawns in, it won't start ticking until after both the player and the camera are in the same area as the entity. if an entity has a trigger group assigned to it, it'll begin ticking regardless.

most entities have a "root position" they'll return to after a player death occurs. a mob's root position is usually the same as its spawner tile's position, and doesn't normally change during gameplay.

despite there already being a global "TICK" counter, mobs prefer to have their own local frame counter, which comes in handy for animation and whatnot. a notable example of this are the eye ground tiles blinking every 200 frames[^1], to then reset the frame counter afterwards.

# list of entities
type         | unused | name                        | category    | sprite name | [solid threshold](./glossary.md#solid-threshold)
------------ | ------ | --------------------------- | ----------- | ----------- | ------------------------------------------------
\-           | no     | Appel                       | Player      | Player      | 4
2            | no     | Mob A1                      | Enemy       | Mob         | 4 / 0
3            | no     | Big Eye                     | Enemy       | Mob - Eye   | -
"blink"      | no     | Big Eyelid                  | Enemy       | Mob - Eye   | -
4            | no     | Sawblade                    | Enemy       | Mob         | 0
5            | yes    | Sawblade                    | Enemy       | Mob         | 0
6            | no     | Bird                        | Enemy       | Mob         | -
7            | no     | Bird Bomb / Egg Bomb        | Enemy       | Mob         | 4
8            | no     | Eye Launcher                | Enemy       | Mob         | -
9            | no     | Pip                         | Enemy       | Mob         | 4 / 0
10           | no     | Worm (CW)                   | Enemy       | Mob         | 4
11           | no     | Worm (CCW)                  | Enemy       | Mob         | 4
12           | no     | Apple (Yellow)              | Collectable | Float Apple | -
12.5         | no     | Apple (Yellow) (Hidden)     | Collectable | Float Apple | -
13           | no     | Purple Mob                  | Enemy       | Mob         | 4 / 0
80           | no     | Lift (Horizontal)           | Dynamic     | Dynamic     | 0
81           | no     | Lift (Vertical)             | Dynamic     | Dynamic     | 0
82           | no     | Masher / Crusher            | Dynamic     | Dynamic     | 0
83           | yes    | Burtha (?)                  | Dynamic     | Dynamic     | 4
84           | no     | Burtha                      | Dynamic     | Dynamic     | 4
"key1"       | no     | Key                         | Collectable | Collect     | -
"mega apple" | no     | Apple (Red)                 | Collectable | Collect     | -
"SPIDER"     | yes    | Spider Boss / Micro Manager | Enemy       | Boss1       | -

### footnotes
[^1]: fun fact: the blinking eyelid that appears for these tiles is actually a separate entity that gets spawned in! so is the actual eye that follows the player around! you can confirm this yourself by inspecting the "Mob - Eye" sprite.