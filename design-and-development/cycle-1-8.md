# 2.2.9 Cycle 9

## Design

### Objectives

In the nineth cycle, my objectives are to implement the second type of hostile enemy into the game. As with the previous enemy, the Twines don't need to be too detailed, a simple shape or image will do.

* [x] Add Twines as specified in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents).
* [x] Twines should damage or kill the player.

### Usability Features

The Player will have to avoid the Twine since they will cause the Player to die and the game to end. This will add excitement into the game since there is now a larger risk factor.



### Key Variables

| Variable Name | Use                                                                                |
| ------------- | ---------------------------------------------------------------------------------- |
| ENEMY\_SPEED  | Used to control the speed of the Twines if I wish to make them move in the future. |
| BULLET\_SPEED | Used to control the speed of the bullets that the Twine shoots.                    |

### Pseudocode

The pseudocode for the hostile Twine is shown below:

```
// Twine

const ENEMY_SPEED = 0
const BULLET_SPEED = 800

let twine

On collision with "enemy":
    if not colliding from the bottom:
        Go to "lose" scene
End on collision

twine = add entity with:
    - sprite "Twine"
    - position (2688, -60)
    - anchor "center"
    - initial state "move" with possible states: "idle", "attack", "move"

On entering state "idle":
    Wait for 0.5 seconds
    Change twine state to "attack"
End on entering state "idle"

On entering state "attack":
    if player exists:
        Calculate direction as unit vector from twine position to player position

        add bullet entity with:
            - position twine position
            - move in direction with speed BULLET_SPEED
            - rectangle shape (12, 12)
            - area
            - offscreen behavior with destruction
            - anchor "center"
            - color BLUE
            - "bullet" component
        
    Wait for 1 second
    Change twine state to "move"
End on entering state "attack"

On entering state "move":
    Wait for 2 seconds
    Change twine state to "idle"
End on entering state "move"

During state "move":
    if player exists:
        Calculate direction as unit vector from twine position to player position
        Move twine in the direction scaled by ENEMY_SPEED
End during state "move"
```

## Development

### Outcome

* The player is now faced with the Twine opponent later on in the game, the code for this can be viewed below:

```javascript
// Twine

    const ENEMY_SPEED = 0;
    const BULLET_SPEED = 800;

    let twine;

    player.onCollide("enemy", (e, col) => {
        if (!col.isBottom()) {
            go("lose");
        }
    });

    twine = add([
        sprite("Twine"),
        pos(2688, - 60),
        anchor("center"),
        state("move", ["idle", "attack", "move"])
    ]);
    
    twine.onStateEnter("idle", async () => {
        await wait(0.5);
        twine.enterState("attack");
    });

    twine.onStateEnter("attack", async () => {
        if (player.exists()) {
            const dir = player.pos.sub(twine.pos).unit();

            add([
                pos(twine.pos),
                move(dir, BULLET_SPEED),
                rect(12, 12),
                area(),
                offscreen({destroy: true}),
                anchor("center"),
                color(BLUE),
                "bullet"
            ]);
        }

        await wait(1);
        twine.enterState("move");
    });

    twine.onStateEnter("move", async () => {
        await wait(2);
        twine.enterState("idle");
    });

    twine.onStateUpdate("move", () => {
        if (!player.exists()) return;
        const dir = player.pos.sub(twine.pos).unit();
        twine.move(dir.scale(ENEMY_SPEED));
    });
```

### Challenges

Some challenges I faced during this cycle:

* The positioning of the Twine was difficult to implement because they wouldn't comply with the array level format.
* The Twine wouldn't shoot consistantly or in the correct direction.

## Testing

Tests performed in this cycle are evidenced below, they were a crucial aspect to my development.

### Tests

| Test | Instructions                                             | What I expect                                                           | What actually happens | Pass/Fail |
| ---- | -------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------- | --------- |
| 1    | Run code.                                                | The game to start, boundaries rendered, player, Grunt and Twine placed. | As expected           | Pass      |
| 2    | Collide the Player's character with the Twine's bullets. | The Player loses the game and the game is reset.                        | As expected           | Pass      |

### Evidence

The screen recording below shows the Player being defeated by the hostile Twine, it completes the following tasks for this cycle:

* [x] Add Twine as specified in [<mark style="color:blue;">1.4a Features of Proposed Solution</mark>](../1-analysis/1.4a-features-of-the-proposed-solution.md#opponents).
* [x] Twine should damage or kill the player.

