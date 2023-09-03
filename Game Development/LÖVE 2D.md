Entry point: `main.lua`

## Lifecycle
- `love.load()`
	- Called at the start of the game
- `love.update(deltaTime)`
	- Called every frame
- `love.draw()`
	- Renders to screen
## Taking input from user
- [`love.keypressed(key, scancode, isrepeat)`](https://love2d.org/wiki/love.keypressed)
- [love.keyreleased(key, scancode)](https://love2d.org/wiki/love.keyreleased)
- [Scancodes](https://love2d.org/wiki/Scancode)