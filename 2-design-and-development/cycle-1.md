# 2.2.1 Cycle 1

## Design

### Objectives

In the first cycle, my objectives are to create the html webpage and then to add the layers and sprites. Completing the steps in this order should lay out a strong, progressive structure for my game. The layers don't need to be too detailed at this point, graphics quality improvements can be adjusted later on.

* [x] Set up the HTML and Javascript in Repl.it
* [x] Set up the layers on the screen
* [x] Implement boundaries
* [x] Add the player (can be a simple shape for now)
* [x] Implement gravity into the game

### Usability Features

Contrasting colours will be used to show clear boundaries and will help me to split the development into specific sectionsas discussed in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).

Boundaries will be used to prevent the player from falling out of the map. This should allow the user to focus on the game objective and not have to worry about accidental movements.



### Key Variables

| Variable Name | Use                                        |
| ------------- | ------------------------------------------ |
| setGravity    | Defines the value for gravity used.        |
| bulletSpeed   | Defines the value for player bullet speed. |

### Pseudocode

```
import kaboom

define(gravity)

load(player)
place(player)

render(platform)

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



### Challenges

Some challenges I faced during this cycle:

* Implemending the boundaries at different orientations.
* Assigning the common key bindings to the movement actions.

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions  | What I expect                                             | What actually happens | Pass/Fail |
| ---- | ------------- | --------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.     | The game to start, boundaries rendered, player placed.    | As expected           | Pass      |
| 2    | Watch Player. | The player is pulled downwards due to artificial gravity. | As expected           | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
