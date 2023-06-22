# 2.2.3 Cycle 3

## Design

### Objectives

In the third cycle, my objectives are to implement hostile enemies into the game. For now, I will only be adding the Grunt as detailed in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents). At this point, the Grunts don't need to be too detailed, a simple shape or image will do. I will also add a cooldown for the Player's jump ability otherwise, the Player is able to fly.

* [x] Cooldown for jump ability.
* [ ] Add Grunts as specified in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents).
* [ ] Grunts should damage or kill the player.

### Usability Features

The Player's movement will be significantly more realistic since they will not be able to fly. Their jump cooldown will be around 0.5 - 1.0 seconds depending on further testing. The Player will also have to avoid the Grunts since they will cause the Player's character to end the game.



### Key Variables

| Variable Name | Use                                                        |
| ------------- | ---------------------------------------------------------- |
| jumpForce     | Defines the force value used when jump function is called. |
| jumpProcedure | Boolean variable used to run jump function and cooldown.   |

### Pseudocode

The pseudocode for the new jumping procedure is shown below:

```
Define jump force jumpForce = 800

// Define jump() function
Function jump():
 If player is grounded:
  Call player.jump(jumpForce)

// Jump when 'space' is pressed
 jumpProcedure = false
 On key down "space": 
  If jumpProcedure is not true:
   Set jumpProcedure to true Call jump()
   Wait for 0.8 seconds, then:
    Set jumpProcedure to false

// Jump when 'up' is pressed On key down "up":
 If jumpProcedure is not true:
  Set jumpProcedure to true Call jump()
  Wait for 0.8 seconds, then:
   Set jumpProcedure to false
```

## Development

### Outcome

* The player is no longer able to fly using the jump keys, the code for this can be viewed below:

```javascript
//Define jump force
const jumpForce = 800

// Define jump() function
function jump() {
	// these 2 functions are provided by body() component
	if (player.isGrounded()) {
		player.jump(jumpForce)
	}
}


// Jump when 'space' is pressed
let jumpProcedure = false;

onKeyDown("space", () => {
  if (!jumpProcedure) {
    jumpProcedure = true;
    // run jump function
    jump();
    // wait duration
    wait(0.8, () => {
      jumpProcedure = false;
    });
  }
});

// Jump when 'up' is pressed

onKeyDown("up", () => {
  if (!jumpProcedure) {
    jumpProcedure = true;
    // run jump function
    jump();
    // wait duration
    wait(0.8, () => {
      jumpProcedure = false;
    });
  }
});
```

### Challenges

Some challenges I faced during this cycle:

* I had to rewrite the entire jumping procedure and include a loop which called a function.

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                       | What I expect                                                                               | What actually happens | Pass/Fail |
| ---- | ---------------------------------- | ------------------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                          | The game to start, boundaries rendered, player and Grunt placed.                            | As expected           | Pass      |
| 2    | Both jump keys repeatedly pressed. | The Player's character is unable to fly upwards and has a short cooldown between each jump. | As expected           | Pass      |

### Evidence

The code snippet below shows the Javascript for the jump cooldown, it completes the following tasks for this cycle:

* [x] Cooldown for jump ability.

```javascript
// Define jump() function
function jump() {
	// these 2 functions are provided by body() component
	if (player.isGrounded()) {
		player.jump(jumpForce)
	}
}


// Jump when 'space' is pressed
let jumpProcedure = false;

onKeyDown("space", () => {
  if (!jumpProcedure) {
    jumpProcedure = true;
    // run jump function
    jump();
    // wait duration
    wait(0.8, () => {
      jumpProcedure = false;
    });
  }
});

// Jump when 'up' is pressed

onKeyDown("up", () => {
  if (!jumpProcedure) {
    jumpProcedure = true;
    // run jump function
    jump();
    // wait duration
    wait(0.8, () => {
      jumpProcedure = false;
    });
  }
});
```
