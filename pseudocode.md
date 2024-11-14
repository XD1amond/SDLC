START PROGRAM UnderwaterAsteroids

// INITIALIZATION
Initialize game window
Initialize score = 0
Initialize lives = 3
Initialize level = 1

// OBJECT DEFINITIONS
Define Submarine:
    Properties:
        position (x, y)
        velocity (dx, dy)
        rotation
        isInvulnerable = false
        torpedoes = []
    Methods:
        Move()
        Rotate()
        FireTorpedo()
        CheckCollision()

Define Fish:
    Properties:
        position (x, y)
        velocity (dx, dy)
        size
        type (large, medium, small)
    Methods:
        Move()
        Split()
        CheckCollision()

Define Torpedo:
    Properties:
        position (x, y)
        velocity (dx, dy)
        lifespan
    Methods:
        Move()
        CheckCollision()

// MAIN GAME LOOP
WHILE game is running:
    // INPUT HANDLING
    IF key pressed is LEFT:
        Rotate submarine counter-clockwise
    IF key pressed is RIGHT:
        Rotate submarine clockwise
    IF key pressed is UP:
        Apply thrust to submarine in current direction
    IF key pressed is SPACE:
        FireTorpedo()

    // UPDATE GAME OBJECTS
    FOR each game object:
        Update position based on velocity
        Wrap position around screen edges
        
    // COLLISION DETECTION
    FOR each torpedo:
        FOR each fish:
            IF torpedo collides with fish:
                Remove torpedo
                Split fish into smaller fish OR remove if smallest
                Increase score based on fish size
                
    FOR each fish:
        IF fish collides with submarine AND NOT submarine.isInvulnerable:
            Decrease lives
            IF lives > 0:
                Reset submarine position
                Set submarine.isInvulnerable = true for 3 seconds
            ELSE:
                END GAME
                
    // LEVEL PROGRESSION
    IF no fish remain:
        Increase level
        Spawn new wave of fish
        Number of fish = level * 2
        Fish speed = base_speed * (1 + level * 0.1)

    // DISPLAY UPDATES
    Clear screen
    Draw ocean background
    Draw submarine
    Draw all fish
    Draw all active torpedoes
    Display score, lives, and level
    Update screen

    // FRAME TIMING
    Wait for next frame

// GAME OVER HANDLING
IF game over:
    Display "GAME OVER" screen
    Display final score
    IF new high score:
        Save high score
    Display "Press SPACE to play again"
    IF SPACE pressed:
        Reset game state
    IF ESC pressed:
        Quit game

END PROGRAM
