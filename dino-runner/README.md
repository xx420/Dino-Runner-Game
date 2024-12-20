# Explain - CHow the Code Works?

## 1. **Setting the Cursor Position:**

```
lcd.setCursor(0, runnerPosition);
```
Explanation: This line sets the position of the cursor on the LCD screen. It places the cursor at column 0 and the row indicated by the runnerPosition variable. The runnerPosition determines whether the dinosaur is at the bottom (runnerPosition = 1) or at the top (runnerPosition = 0) for the jump action.

The T-Rex Runner Game code creates a simple LCD-based game that controls the movement of a dinosaur and obstacles. The primary logic centers around the interaction between the runner (dinosaur) and the obstacle (cactus).

Initially, the LCD screen is set up using lcd.begin(16, 2);, and custom characters representing the dinosaur, cactus, and other game elements are created with lcd.createChar(). These custom characters are then drawn to the screen during the game loop to represent the runner and obstacles.

The dinosaur’s position is controlled by the variable runnerPosition, which can either be at the bottom row (when not jumping) or at the top row (while jumping). The jump is triggered when the player presses a button connected to pin 10. The condition if (digitalRead(buttonJumpPin) == LOW && !isJumping && runnerPosition == 1) checks if the jump button is pressed and the dinosaur is on the ground. Upon pressing, the runner moves upwards, simulating a jump, and after a set duration (jumpDuration), it returns to the ground.

Obstacles move from right to left, controlled by the variable obstaclePosition. Every time the interval passes, the cactus moves left by one position. If the cactus reaches the left edge, it resets, and the score increments by 1. Collision detection checks if the obstacle overlaps with the runner’s position when it's on the ground. If the runner and the obstacle collide, the game ends and displays "Game Over."

Overall, the code implements simple game mechanics like jumping, moving obstacles, and scoring while managing the timing and collision detection using basic conditional statements.
