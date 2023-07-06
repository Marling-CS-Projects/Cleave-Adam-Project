# Spare Code

Code for player shooting:

```javascript
const bulletSpeed = 1000

function spawnBullet(p) {
		add([
			circle(12),
			area(),
			pos(p),
			anchor("center"),
			color(127, 127, 255),
			outline(4),
			move(mousePos(), bulletSpeed),
			offscreen({ destroy: true }),
			// Strings here means a tag
			"bullet",
		])
	}

onMousePress("left", () => {
		spawnBullet(player.pos.sub(-16, 0))
		})
```
