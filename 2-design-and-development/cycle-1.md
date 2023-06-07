# 2.2.1 Cycle 1

## Design

### Objectives

In the first cycle, my objectives are to create the html webpage and then to add the layers and sprites. Completing the steps in this order should lay out a strong, progressive structure for my game. The layers don't need to be too detailed at this point, graphics quality improvements can be adjusted later on.

* [x] Set up the HTML and Javascript in Visual Studio Code
* [x] Set up the layers on the screen
* [x] Implement boundaries
* [x] Add the player (can be a simple shape for now)
* [x] Implement gravity into the game

### Usability Features

Implementing my simple game controls into the project. This will allow the user to move their character around the map.

Contrasting colours will be used to show clear boundaries and will help me to split the development into specific sections.



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

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions  | What I expect     | What actually happens | Pass/Fail |
| ---- | ------------- | ----------------- | --------------------- | --------- |
| 1    | Run code      | Thing happens     | As expected           | Pass      |
| 2    | Press buttons | Something happens | As expected           | Pass      |

### Evidence
