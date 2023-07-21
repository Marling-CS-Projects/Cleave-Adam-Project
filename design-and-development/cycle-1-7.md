# 2.2.8 Cycle 8

## Design

### Objectives

In the eighth cycle, my objectives are to implement the background music as specified in the Systems Diagram in [<mark style="color:blue;">2.1 Design Frame</mark>](../2-design-and-development/systems-diagram.md). The aim for this is for it to be catchy and memorable, this will encourage people to play the game and try to keep in in their minds.

* [x] Implement background game music.
* [x] The music must fit the style of the game.
* [x] The music should be catchy.

### Usability Features

The music will stay in the Player's heads if it is catchy. Therefore they will think about the game a lot and enjoy playing it.



### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |

### Pseudocode

The pseudocode for the new level and its detail is shown below:

```
// Music Coin
On collision with "Coin":
    Destroy the "Coin" object
    Play the "Background Music" with no additional parameters
    Increment the number of coins collected (coins += 1)
End on collision
```

## Development

### Outcome

* Write here... , the code for this can be viewed below:

```javascript
// Music Coin
	player.onCollide("Coin", (c) => {
		destroy(c)
		play("Background Music", {
		})
		coins += 1
	})
```

### Challenges

Some challenges I faced during this cycle:

* At first, I tried to implement a method for the music to be toggled on and off however, it proved to be very difficult.
* I then tried to use two different keys to turn on and off the music however, that was incredibly difficult too.

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                                     | What I expect                                                                                   | What actually happens | Pass/Fail |
| ---- | ------------------------------------------------ | ----------------------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                                        | The game to start, boundaries rendered, player, Grunts placed and teleporter avaliable for use. | As expected           | Pass      |
| 2    | Move the Player's character into the teleporter. | The Player is moved to the second platform which contains a detailed forest environment.        | As expected           | Pass      |

### Evidence

The screen recording below shows the catchy background music implemented into the game, it completes the following tasks for this cycle:

* [x] Implement background game music.
* [x] The music must fit the style of the game.
* [x] The music should be catchy.

{% embed url="https://www.youtube.com/watch?v=EEXK5nVRlf0" %}
