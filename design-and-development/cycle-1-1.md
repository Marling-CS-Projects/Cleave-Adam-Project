# 2.2.2 Cycle 2

## Design

### Objectives

In the second cycle, my objectives are to implemend the basic controls and allow the player's character to move around the screen. Completing the steps in this order should lay out a strong, progressive structure for my game. The layers don't need to be too detailed at this point, graphics quality improvements can be adjusted later on.

* [x] Implement Player movement
* [x] Utilise basic controls for the movement as specified in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).

### Usability Features

Implementing my simple game controls into the project. This will allow the user to move their character around the map as discussed in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).



### Key Variables

| Variable Name | Use                                          |
| ------------- | -------------------------------------------- |
| setGravity    | Defines the value for gravity used.          |
| moveSpeed     | Defines the value for player movement speed. |
| bulletSpeed   | Defines the value for player bullet speed.   |

### Pseudocode

```
import kaboom

define(gravity)

load(player)
place(player)

render(platform)


define(moveSpeed)
if up arrow pressed: { 
  move player up by moveSpeed
};
if left arrow pressed: {
  move player left by moveSpeed
};
if down arrow pressed: {
  move player down by moveSpeed
};
if right arrow pressed: {
  move player right by moveSpeed
};


define(bulletSpeed)
load(bullet)
place(bullet)

if left mouse pressed: {
  spawn bullet at bulletSpeed
  };
```

## Development

### Outcome

* I now have a functioning boundary around the edge of the screen, the code for this can be viewed below:

```
// Boundaries and Collisions

// Add a platform to be bottom boundary
add([
	rect(width(), 48),
	outline(4),
	area(),
	pos(0, height() - 25),
	// Give objects a body() component if you don't want other solid objects pass through
	body({ isStatic: true }),
])

// Add a platform to be top boundary
add([
    rect(width(), 48), // Adjusted the width and height to create a horizontal rectangle
    outline(4),
    area(),
    pos(0, 0),
    // Changed the position to start from the top-left corner of the screen
    body({ isStatic: true }),
]);

// Add a platform to be left boundary
add([
    rect(48, height()), // Adjusted the width and height to create a vertical rectangle
    outline(4),
    area(),
    pos(0, 0),
    // Changed the position to start from the bottom-left corner of the screen
    body({ isStatic: true }),
]);
```



* The player is now able to be controlled once they have been rendered, the code for this can be viewed below:

```
// MOVEMENT

// Define player movement speed (pixels per second)
const moveSpeed = 320

// jump when player presses "space" key
onKeyDown("space", () => {
    // .jump() is provided by the body() component
    player.jump()
})

// jump when player presses "up" key
onKeyDown("up", () => {
	player.jump()
})

// onKeyDown() registers an event that runs every frame as long as user is holding a certain key
onKeyDown("left", () => {
	// .move() is provided by pos() component, move by pixels per second
	player.move(-moveSpeed, 0)
})

onKeyDown("right", () => {
	player.move(moveSpeed, 0)
})

onKeyDown("down", () => {
	player.move(0, moveSpeed)
})
```

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions  | What I expect                                                                    | What actually happens | Pass/Fail |
| ---- | ------------- | -------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code      | The game to start, boundaries rendered, player placed.                           | As expected           | Pass      |
| 2    | Press buttons | The player is able to move in all directions. This includes the ability to jump. | As expected           | Pass      |

### Evidence
