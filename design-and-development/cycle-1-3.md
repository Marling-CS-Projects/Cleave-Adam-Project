# 2.2.4 Cycle 4

## Design

### Objectives

In the fourth cycle, my objectives are to implement the first level into the game. Completing the steps in this order should lay out a strong, progressive structure for my game. The level doesn't need to be too detailed at this point, graphics quality improvements can be adjusted later on.

* [ ] Implement the first level design.
* [ ] Utilise basic colours to depict a tropical environment as specified in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).

### Usability Features

Implementing my tropical level design into the project. This will allow the user to become more engaged in the game as discussed in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).



### Key Variables

| Variable Name   | Use                                              |
| --------------- | ------------------------------------------------ |
| sprite("Bean")  | Is used to render the bean in the level.         |
| sprite("Grass") | Is used to render the grass blocks in the level. |
| sprite("Coin")  | Is used to render the coins in the level.        |
| sprite("Spike") | Is used to render the spikes in the level.       |

### Pseudocode

```
```

## Development

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
			sprite("Grass"),
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

This code generates the first level completely differently to the code beforehand. Instead of using simple blocks and rectangles, it now utilises variables for each block type (grass blocks, spikes, coins).

### Challenges

Some challenges I faced during this cycle:

* Finding the correct blocks to create a tropical appearance.

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions | What I expect                                                                                          | What actually happens | Pass/Fail |
| ---- | ------------ | ------------------------------------------------------------------------------------------------------ | --------------------- | --------- |
| 1    | Run code.    | The game to start, boundaries still rendered, player placed into tropical environment for first level. | As expected           | Pass      |

### Evidence

The screenshot below shows the rendered sprite after moving from its original position, it completes the following tasks for this cycle:

* [ ] Implement the first level design.
* [ ] Utilise basic colours to depict a tropical environment as specified in [<mark style="color:blue;">1.5 Success Criteria</mark>](../1-analysis/1.5-success-criteria.md).
