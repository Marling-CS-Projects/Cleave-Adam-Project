# 2.2.4 Cycle 4 - First Level

## Design:

### Objectives

In the fourth cycle, my objectives are to implement the first level into the game. Completing the steps in this order should lay out a strong, progressive structure for my game. The level doesn't need to be too detailed at this point, graphics quality improvements can be adjusted later on.

* [x] Implement the first level design.
* [x] Utilise basic colours to depict a tropical environment as specified in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).

### Usability Features

Implementing my tropical-level design into the project. This will allow the user to become more engaged in the game as discussed in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).



### Key Variables

| Variable Name   | Use                                             |
| --------------- | ----------------------------------------------- |
| sprite("Bean")  | Is used to render the bean in the level.        |
| sprite("Sand")  | Is used to render the sand blocks in the level. |
| sprite("Coin")  | Is used to render the coins in the level.       |
| sprite("Spike") | Is used to render the spikes in the level.      |

### Pseudocode

The pseudocode for the new level generation is shown below:

```
level = addLevel([
    "=       ",
    "=   ^ $$",
    "==============",
], {
    tileWidth: 64,
    tileHeight: 64,
    pos: vec2(100, 200),
    tiles: {
        "@": function() {
            /* Create a player object with components */
            return [
                sprite("Bean"),
                area(),
                body(),
                anchor("bot"),
                "player",
            ];
        },
        "=": function() {
            /* Create a sand object with components */
            return [
                sprite("Sand"),
                area(),
                body({ isStatic: true }),
                anchor("bot"),
            ];
        },
        "$": function() {
            /* Create a coin object with components */
            return [
                sprite("Coin"),
                area(),
                anchor("bot"),
                "coin",
            ];
        },
        "^": function() {
            /* Create a spike object with components */
            return [
                sprite("Spike"),
                area(),
                anchor("bot"),
                "danger",
            ];
        },
    },
});
```

## Development:

### Outcome

* The player is now placed into a basic environment for the first level, the code for this can be viewed below:

```javascript
const level = addLevel([
	// Design the level layout with symbols
    "=       ",
	"=   ^ $$",
	"==============",
], {
	// The size of each grid
	tileWidth: 64,
	tileHeight: 64,
	// The position of the top left block
	pos: vec2(100, 200),
	// Define what each symbol means (in components)
	tiles: {
		"@": () => [
			sprite("Bean"),
			area(),
			body(),
			anchor("bot"),
			"player",
		],
		"=": () => [
			sprite("Sand"),
			area(),
			body({ isStatic: true }),
			anchor("bot"),
		],
		"$": () => [
			sprite("Coin"),
			area(),
			anchor("bot"),
			"coin",
		],
		"^": () => [
			sprite("Spike"),
			area(),
			anchor("bot"),
			"danger",
		],
	},
})
```

This code generates the first level completely differently from the code beforehand. Instead of using simple blocks and rectangles, it now utilises variables for each block type (Sand blocks, spikes, coins).

### Challenges

Some challenges I faced during this cycle:

* Finding the correct blocks to create a tropical appearance.

## Testing:

Tests performed in this cycle are evidenced below, they were a crucial aspect of my development.

### Tests

| Test | Instructions | What I expect                                                               | What actually happens | Pass/Fail |
| ---- | ------------ | --------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.    | The game to start, player placed into tropical environment for first level. | As expected           | Pass      |

### Evidence

The screenshot below shows the first level design with the tropical environment blocks, it completes the following tasks for this cycle:

* [x] Implement the first level design.
* [x] Utilise basic colours to depict a tropical environment as specified in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).

<figure><img src="../.gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>
