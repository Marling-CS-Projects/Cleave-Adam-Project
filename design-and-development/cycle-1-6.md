# 2.2.7 Cycle 7 - Second Level

## Design:

### Objectives

In the seventh cycle, my objectives are to develop the second level of my game and add some detail to it. This will help the Player to feel immersed in the environment and positively impact my game.

* [x] Develop second level structure.
* [x] Add sufficient detail to the second level.

### Usability Features

The Player will feel more immersed in the environment that they are placed into. Therefore, making my game feel more exciting and enjoyable.



### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |

### Pseudocode

The pseudocode for the new level and its detail is shown below:

```
// Define above code
const levelConf = {
    // The size of each grid
    tileWidth: 64,
    tileHeight: 64,
    // Define what each symbol means (in components)
    tiles: {
        "@": () => [
            add sprite("Bean"),
            add area(),
            add body(),
            add anchor("bot"),
            add "player" component,
        ],

        "=": () => [
            add sprite("Sand"),
            add area(),
            add body({ isStatic: true }),
            add anchor("bot"),
            add offscreen({ hide: true }),
            add "Platform" component,
        ],

        "$": () => [
            add sprite("Coin"),
            add area(),
            add anchor("bot"),
            add "coin" component,
        ],

        "^": () => [
            add sprite("Spike"),
            add area(),
            add anchor("bot"),
            add "danger" component,
        ],

        ">": () => [
            add sprite("Grunt"),
            add area(),
            add anchor("bot"),
            add body(),
            add Patrol() component,
            add offscreen({ hide: true }),
            add "enemy" component,
        ],

        "#": () => [
            add sprite("Forest"),
            add area(),
            add body({ isStatic: true }),
            add anchor("bot"),
            add offscreen({ hide: true }),
            add "Platform" component,
        ],

        "~": () => [
            add sprite("Portal"),
            add area({ scale: 0.5 }),
            add anchor("bot"),
            set position to (0, -12),
            add offscreen({ hide: true }),
            add "Portal" component,
        ],
    },
}

```

## Development:

### Outcome

* The player is now faced with another level after completing the first, the code for this can be viewed below:

```javascript
[
        "                                              ",
        "#     #   #   #   #   #                 ##    ",
        "#    ##               #                       ",
        "#   ###   >           # ^^  ^^  ^^           ~",
        "##############################################",
    ],

// Define above code
const levelConf = {
    // The size of each grid
    tileWidth: 64,
    tileHeight: 64,
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
            offscreen({hide:true}),
            "Platform",
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
        ">": () => [
			sprite("Grunt"),
			area(),
			anchor("bot"),
			body(),
			Patrol(),
			offscreen({ hide: true }),
			"enemy",
        ],
        "#": () => [
            sprite("Forest"),
            area(),
			body({ isStatic: true }),
			anchor("bot"),
            offscreen({hide: true}),
            "Platform",
        ],
        "~": () => [
            sprite("Portal"),
            area({scale: 0.5}),
            anchor("bot"),
            pos(0, -12),
            offscreen({hide: true}),
            "Portal",
        ],
	},
}
```

### Challenges

Some challenges I faced during this cycle:

* Detail was difficult to add since it required me to do some photo editing which I had no real experience of doing.

## Testing:

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                                     | What I expect                                                                                   | What actually happens | Pass/Fail |
| ---- | ------------------------------------------------ | ----------------------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                                        | The game to start, boundaries rendered, player, Grunts placed and teleporter avaliable for use. | As expected           | Pass      |
| 2    | Move the Player's character into the teleporter. | The Player is moved to the second platform which contains a detailed forest environment.        | As expected           | Pass      |

### Evidence

The screen recording below shows the Player's Character in the new environment / level, it completes the following tasks for this cycle:

* [x] Develop second level structure.
* [x] Add sufficient detail to the second level.



{% embed url="https://youtu.be/LxZKQ-L4KAg" %}
