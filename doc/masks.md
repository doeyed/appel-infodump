<!--
    created: June 17th, 2024
    updated: June 18th, 2024
-->

# tile masks

a **tile mask** is a short string that mostly defines tile collision data, but may also define other properties about the tile, including triggering events upon any player collision with itself. every tile mask can be found in the global "MASK" list, with each item in the list having a corresponding tile ID that matches its index.

as an example of a tile mask, we'll use a basic ground tile that looks like this:

![a basic green ground tile](../res/green-8.svg)

this specific tile (with an ID of 2) in the game has the mask "`5555   1h`," so we'll begin to note down a few interesting things about this tile, such as:

- it's entirely solid
    - the first four characters being all fives will make each [quarter tile](./glossary.md#quarter-tile) solid for a player, making the whole tile solid as well
        - for more information, take a look at  the [character index table](#character-index-table)
- it'll definitely be visible in-game
    - the sixth character being a single space (` `) will make it visible
- it'll appear in the first brush category in the level editor
    - the eigth character is just the number one, as this tile is supposed to go in the first brush category
        - the same rule applies for any brush category
        - if you didn't want a tile to be placeable in the level editor, you may use any character that isn't a number (e.g. the letter X being used for tiles with the "BIG" costume)
- it'll have its hue tinted to match the level's hue.
    - the ninth and last character in the mask being present as the letter H makes this true

this is all possible to know simply by itering through each character in the mask one-by-one, from the start of the mask, to end of it, and taking notes along the way.

while itering through the mask, make sure to also keep track of where and what that character is, as you'll need to refer to the [tables](#tables) below.

# tables
## characters
character | unused | player compatible | mob compatible | [entity](./glossary.md#entity) compatible (excluding mobs) | description
--------- | ------ | ----------------- | -------------- | ---------------------------------------------------------- | -----------
` `       | no     | yes               | yes            | yes                                                        | blank character, but can serve more than one purpose, like marking quarter tiles as non-solid
`n > 4`   | no     | yes               | yes[^1]        | yes[^1]                                                    | mark a quarter tile as solid ground
`*`       | yes    | -                 | -              | -                                                          | mostly speculation, might've used to function similarly to the sixth row in this table, but for things like yellow/red apples. currently acts as non-solid
`.`       | no     | yes               | no[^2]         | no[^2]                                                     | if the tile is a spike, mark a quarter tile as spikey[^3], and if touched by the player, kill the player
`7`       | no     | yes               | no             | no                                                         | if the tile is a conveyor belt, mark a quarter tile as part of the belt
`6`       | no     | yes               | no             | no                                                         | mark a quarter tile as one that can "activate" the full tile[^4], upon player collision
`h`       | no     | -                 | -              | -                                                          | presumably short for hue, see the description for character index #9 in the table below

## character indexes
for the first four rows, it's safe to assume that most tiles will have these all set to a [solid threshold](./glossary.md#solid-threshold) of five, so most entities (including mobs & the player) aren't able to pass through them.

character index  | unused | description
---------------- | ------ |-----------
#1               | no     | the type of the bottom-left quarter tile (solid, spikey, etc.)
#2               | no     | the type of the top-left quarter tile
#3               | no     | the type of the top-right quarter tile
#4               | no     | the type of the bottom-right quarter tile
#5               | no     | the type (character #5 + character #6) of the entity to spawn in, if character #5 isn't a space (` `)
#6               | no     | the tile's visiblity. if character #6 is a space (` `), it'll be visible. otherwise, it'll be invisible
#7               | yes    | currently unknown, as no tile masks make use of it
#8               | no     | the tile's brush category for the level editor
#9               | no     | whenever or not to tint the hue of the full tile by the level's hue. if you wanted this, you'd put the letter H in this spot

### footnotes
[^1]: most entities will be capable with passing the [solid check.](./glossary.md#solid-check) however, if an entity has a solid threshold greater than the number, it'll stopping treating the quarter tile as solid ground, and likely pass through it. we may pretend the player has a solid threshold of four, though the player doesn't really use a regular solid check.

[^2]: entities, other than the player, like to pretend that spikes simply don't exist

[^3]: fun fact: normally, the spikey quarter tiles of a full spike tile aren't actually solid, but mobs (and other entities) can choose to ignore this, and treat it as regular solid ground

[^4]: this doesn't affect activation tiles, as their behavior is hardcoded into the "Player" sprite, and aren't determined by their tile masks. something similar is also in place for collectibles, checkpoints, flag poles, etc. (flag poles, checkpoints, yellow apples, and such are valid tiles, but collectibles, like red keys/apples, are technically entities)