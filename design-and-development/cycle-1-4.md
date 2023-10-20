# 2.2.5 Cycle 5 - Grunts

## Design:

### Objectives

In the fifth cycle, my objectives are to implement hostile enemies into the game. For now, I will only be adding the Grunt as detailed in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents). At this point, the Grunts don't need to be too detailed, a simple shape or image will do.

* [x] Add Grunts as specified in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents).
* [x] Grunts should damage or kill the player.

### Usability Features

The Player will have to avoid the Grunts since they will cause the Player to die and the game to end. This will add excitement to the game since there is now a risk factor.



### Key Variables

| Variable Name | Use                                                                        |
| ------------- | -------------------------------------------------------------------------- |
| FALL\_DEATH   | Determines the 'y value' for death when the Player's character is falling. |

### Pseudocode

The pseudocode for the hostile Grunts is shown below:

```
// Grunts

// Custom component controlling enemy patrol movement
function patrol(speed = 60, dir = 1):
    return {
        id: "patrol",
        require: [ "pos", "area" ],
        add():
            this.on("collide", (obj, col) =>
                if (col.isLeft() or col.isRight()):
                    dir = -dir
                end if
            )
        end add

        update():
            this.move(speed * dir, 0)
        end update
    }
end function

// DEATH and DANGER

// Grunts
player.onCollide("enemy", (e, col) =>
    // if it's not from the top, die
    if (not col.isBottom()):
        go("lose")
        alert("You died! Please try again!")
        // Refresh the page
        if (player.pos.y > FALL_DEATH):
            window.location.reload()
        else:
            window.location.href = "https://a-level-project.adamcleave.repl.co"
        end if
    end if
end function

```

## Development:

### Outcome

* The player is now faced with the Grunt opponents when the game begins, the code for this can be viewed below:

```javascript
// Grunts

// Custom component controlling enemy patrol movement
function patrol(speed = 60, dir = 1) {
	return {
		id: "patrol",
		require: [ "pos", "area" ],
		add() {
			this.on("collide", (obj, col) => {
				if (col.isLeft() || col.isRight()) {
					dir = -dir
				}
			})
		},
		update() {
			this.move(speed * dir, 0)
		},
	}
}

// DEATH and DANGER

// Grunts
player.onCollide("enemy", (e, col) => {
  // if it's not from the top, die
  if (!col.isBottom()) {
    go("lose");
    alert("You died! Please try again!");
    // Refresh the page
    if (player.pos.y > FALL_DEATH) {
      window.location.reload();
    } else {
      window.location.href = "https://a-level-project.adamcleave.repl.co";
    }
  }
});
```

### Challenges

Some challenges I faced during this cycle:

* The Grunts movement was difficult to implement because they wouldn't comply with the gravity which was set.

## Testing:

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                                   | What I expect                                                    | What actually happens | Pass/Fail |
| ---- | ---------------------------------------------- | ---------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                                      | The game to start, boundaries rendered, player and Grunt placed. | As expected           | Pass      |
| 2    | Collide the Player's character with the Grunt. | The Player loses the game and the game is reset.                 | As expected           | Pass      |

### Evidence

The screen recording below shows the rendered sprite after moving from its original position, it completes the following tasks for this cycle:

* [x] Add Grunts as specified in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents).
* [x] Grunts should damage or kill the player.



{% embed url="https://youtu.be/WUfvGfy4c2s" %}
