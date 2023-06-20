# 2.2.3 Cycle 3

## Design

### Objectives

In the third cycle, my objectives are to implement hostile enemies into the game. For now, I will only be adding the Grunt as detailed in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents). At this point, the Grunts don't need to be too detailed, a simple shape or image will do. I will also add a cooldown for the Player's jump ability otherwise, the Player is able to fly.

* [ ] Cooldown for jump ability.
* [ ] Add Grunts as specified in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents).
* [ ] Grunts should damage or kill the player.

### Usability Features

The Player's movement will be significantly more realistic since they will not be able to fly. Their jump cooldown will be around 0.5 - 1.0 seconds depending on further testing. The Player will also have to avoid the Grunts since they will cause the Player's character to end the game.



### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |

### Pseudocode

```
```

## Development

### Outcome

* The player is no longer able to fly using the jump keys, the code for this can be viewed below:

```
```

### Challenges

Some challenges I faced during this cycle:

*
*

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                 | What I expect                                                                               | What actually happens | Pass/Fail |
| ---- | ---------------------------- | ------------------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                    | The game to start, boundaries rendered, player and Grunt placed.                            | As expected           | Pass      |
| 2    | Jump key repeatedly pressed. | The Player's character is unable to fly upwards and has a short cooldown between each jump. | As expected           | Pass      |

### Evidence

