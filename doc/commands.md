<!--
    created: July 3rd, 2024
-->

# commands

# list of commands
letter | unused | parameter        | description
------ | ------ | ---------------- | -----------
`H`    | no     | frames           | sets the delay for when the first action will be taken, after activation
`D`    | no     | frames           | sets the delay for each action taken, after activation(?)
`G`    | no     | group #          | assigns an entity into the activation group with the corresponding number -- if the group is activated, all entities assigned to the group will also activate
`X`    | no     | momentum         | sets the amount of horizontal momentum
`Y`    | no     | momentum         | sets the amount of vertical momentum
`S`    | no     | pixels per frame | sets the speed of dynamic entities
`A`    | no     | percent / 100    | sets the acceleration for dynamic entities
`M`    | no     | half-tiles       | sets the maximum extent for mashers
`V`    | no     | variant #        | sets the lift variant
`R`    | yes    | frames(?)        | if present, resets the position of a lift after player death