# User Story: Basic Combat Mechanics
## Story
As a player,
I want to shoot at incoming fish with my submarine's bubbles,
So that I can defend myself and score points in an engaging way.
## Acceptance Criteria
### Submarine Controls
* Submarine rotates smoothly when using arrow keys/gamepad
* Submarine moves forward when thrust is applied
* Submarine maintains momentum after thrust is released
* Submarine wraps around screen edges
* Submarine position updates at 60 FPS
### Shooting Mechanics
* Spacebar/gamepad button releases bubble projectile
* Bubbles travel in direction submarine is facing
* Maximum of 5 bubbles on screen at once
* Bubbles disappear after 2 seconds if no collision
* Bubbles wrap around screen edges
* Visual feedback when shooting (flash/animation)
* Sound effect plays when shooting
### Fish Interaction
* Bubbles destroy fish on collision
* Fish split into two smaller fish when hit
* Score increases by 100 points per large fish hit
* Score increases by 200 points per medium fish hit
* Score increases by 300 points per small fish hit
* Visual effect plays on fish destruction
* Sound effect plays on fish destruction
### Performance Requirements
* All animations maintain 60 FPS
* Input lag under 50ms
* Collision detection accurate within 5 pixels
* No visual stuttering during wraparound
* Audio plays without delay
## Testing Notes
* Test on minimum spec device
* Verify on touch screens
* Check gamepad compatibility
* Validate scoring system
* Confirm visual feedback clarity
## Dependencies
* Physics engine implementation
* Sprite assets completed
* Sound effects created
* Score system implementation
