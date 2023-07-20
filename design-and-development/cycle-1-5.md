# 2.2.6 Cycle 6

## Design

### Objectives

In the sixth cycle, my objectives are to clean up and comment my existing code. This will be useful when debugging in the future. I am also going to implement the transition to the next level, it doesn't have to be detailed for now, a simple platform will do.

* [x] Comment and tidy up code.
* [x] Implement a basic change to the next platform.

### Usability Features

The code will be easier to read and understand for all viewers. The commenting will also prove useful for the debugging.

The change to the next level further develops the game and makes it more entertaining.



### Key Variables

| Variable Name | Use                                        |
| ------------- | ------------------------------------------ |
| levelId       | Corresponds to a specific level design.    |
| LEVELS        | The variable containing all level designs. |

### Pseudocode

The pseudocode for the Portal between the two levels is shown below:

```
On collision with "Portal":
    if (levelId + 1) is less than the number of levels (LEVELS.length):
        Go to "game" scene with parameters:
            - levelId: levelId + 1
            - coins: coins
    else:
        Go to "win" scene
End on collision
```

## Development

### Outcome

* The player is now faced with another level after completing the first, the code for this can be viewed below:

```javascript
// Portal
	player.onCollide("Portal", () => {
		if (levelId + 1 < LEVELS.length) {
			go("game", {
				levelId: levelId + 1,
				coins: coins,
			})
		} else {
			go("win")
		}
	})
```

### Challenges

Some challenges I faced during this cycle:

* The platform change was difficult to implement since moving the Sprite to the correct position was difficult.

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                                     | What I expect                                                                                   | What actually happens | Pass/Fail |
| ---- | ------------------------------------------------ | ----------------------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                                        | The game to start, boundaries rendered, player, Grunts placed and teleporter avaliable for use. | As expected           | Pass      |
| 2    | Move the Player's character into the teleporter. | The Player is moved to the second platform which will later contain more enemies.               | As expected           | Pass      |

### Evidence

The screenshots below shows the commented code, it completes the following tasks for this cycle:

* [x] Comment and tidy up code.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>



The screen recording below shows the teleporter moving the player to the next level after the first has been completed, it completes the following tasks for this cycle:

* [x] Implement a basic change to the next platform.



{% embed url="https://youtu.be/nyLMTrpXnKU" %}
