# Creative Coding Major Project 
Siyun's individual part 


## How to Interact
### Keyboard interaction    
- Press **D**: spawn a new circle from top
- Press **C**: change palettes of all circles
- Press **Z**: clear all circles
- Press **Space**: pause / resume animation
- **Mouse clicks**:wave ripples are generated；and when the mouse approaches a circle, its animation pauses.

## My Individual Approach to Animation
- This project is user input project,which let user's input influence how the graphics appear on the canvas.Compared with the others in my group, my version is defined by a fully user-driven output, where all visual changes depend on clicks and key interactions.

### Visual Inspiration
- The falling effect of the circles is inspired by: [Snowflakes in p5.js](https://p5js.org/examples/classes-and-objects-snowflakes/)
  - This gave me the idea to make the circles keep falling and let users control the animation, which makes the visuals feel more dynamic.
- The mouse interaction is inspired by:
  - ![water ripple](readmeImages/water-ripple_image.jpg)
  - This ripple effect gave me the idea to add mouse interaction to make the experience and visuals more engaging.

### Technical Overview
- Keyboard control is mainly achieved through the keyPressed() function together with conditional statements `(if (key === ...))`.
  - Press **D**, `spawnRingFromTop()` is called to create a new circle at a random location above the canvas.
  - Press **C**，`randomizePalettes()` is called to loop through all circles and give each one a new random color palette.
  - Pressing **Z** clears the canvas by setting the `rings` array to an empty array；
  - Press **Space** to pause or resume the animation by toggling the global isPaused variable
- Mouse interaction
  - A mouse click adds a ripple object to clickRipples at (`mouseX`, `mouseY`). During `drawClickRipples()`, each ripple’s radius growth and alpha fading are driven by its `life / maxLife` ratio, producing a water-ripple visual effect.
  - In `fallAndReset()`, the program checks the distance between the mouse and each circle using `dist(mouseX, mouseY, ring.x, ring.y)`. If the mouse is close enough, the circle stops updating its `y` position and temporarily stops falling.

### External Code / Techniques:
  - The effect of water ripples mainly refers to this YouTube tutorial: [water ripples tutorial](https://www.youtube.com/watch?v=9lEaYKP7yV0)
  
### Modifications to Group Code
- Deleted `generateLayout()` from the group version to disable automatic circle generation
- Change the background color to improve the visual effect

### References & Acknowledgments
- Used p5.js documentation for `map()` and array `slice()` to support ripple fading and colour selection.
- The main code is derived from classroom materials