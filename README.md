# Tetris Game
This is a custom Java implementation of the classic Tetris game. This version is an adaption of a prior team project 
and therefore still under construction. The game features a graphical user interface, smooth gameplay, and various 
game modes.

## Project Structure
```
TetrisGame/
├── src/
│   ├── main/
│   ├── model/
│   ├── resources/
│   ├── ui/
│   └── util/
```

### Main
- `Main.java`: Entry point to the application, handles the game loop and other game-related logic.

### Model
- `Game.java`: Manages game state, updates, and overall control.
- `Score.java`: Handles scoring logic.
- `TetrisShape.java`: Defines the shapes and their rotations.
- `TetrisShapeInstance.java`: Represents a specific instance of a Tetris shape in the game.

### Resources
- `images/`: Stores image resources like Tetris block images.

### UI
![image](https://github.com/user-attachments/assets/989910a6-6b1d-467e-ba2e-7e3327004abf)

- `field/`
  - `FieldPane.java`: Panel that displays the game field (interactive area of game).
- `panel/`
  - `ConfigurePanel.java`: Allows user configuration or settings.
  - `GamePanel.java`: Displays the main game interface which nests the FieldPane.
  - `HighScorePanel.java`: Shows high scores.
  - `MainPanel.java`: The main panel that might include menus or game start options.
  - `SplashPanel.java`: The initial screen shown when the game starts.
- `MainFrame.java`: The main application window/frame which triggers different pannels and holds the main game state to share data.
- `UIGenerator.java`: Helper class for generating UI components (needs refactoring)

### Util
- `CommFun.java`: Contains common utility functions used throughout the application. (needs refactoring)

## Getting Started

1. Clone the repository
2. Open the project in your preferred Java IDE
3. Run `Main.java` to start the game

## Features

- Smooth Tetris Gameplay, with a potential future optional feature of discrete Tetromino movement.
- High score tracking 
- Configurable settings 
- AI Gameplay
- Multiplayer 
- Splash screen on startup
