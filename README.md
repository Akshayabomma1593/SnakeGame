

# **Snake Game in Java**  

## **Description**  
This is a **classic Snake Game** implemented in **Java** using the **Swing framework** for GUI. The game follows the traditional mechanics:  
- The player controls a snake that moves across the screen.  
- The snake must eat randomly placed food to grow longer.  
- The game ends when the snake **collides** with itself or the game boundaries.  
- The player's score increases as the snake consumes food.  

The project is structured into multiple Java classes to handle different aspects of the game, such as **game logic, rendering, user input handling, and event-driven movement**.

---

## **Features**
✔️ **Simple and Classic Gameplay** – Move the snake using arrow keys and eat food to grow.  
✔️ **Random Food Placement** – The food appears at random locations after being eaten.  
✔️ **Collision Detection** – The game stops when the snake crashes into itself or the walls.  
✔️ **Score Tracking** – The game displays the player's score.  
✔️ **Smooth Animations** – Movement is handled using Java’s `Timer`.  
✔️ **Keyboard Controls** – Uses key events to change the snake’s direction.  
✔️ **Graphical User Interface (GUI)** – Implemented using `JPanel` and `JFrame`.  

---

## **Technologies Used**
- **Java (JDK 8 or later)**
- **Swing (JPanel, JFrame, Timer)**
- **AWT (Graphics, KeyEvent, Dimension, Random)**  

---

## **Project Flow (Step-by-Step Execution)**  

### **1. Program Execution Begins (GamePlayer.java)**
- The game starts from the `GamePlayer` class, which contains the **main method**.
- It **creates and displays** the game window by calling `GameFrame.Frame()`.

### **2. Setting Up the Game Window (GameFrame.java)**
- The `GameFrame` class extends `JFrame` and sets up the game window.  
- It initializes the `SnakePanel` where the game is played.  
- The window is set to **500x500 pixels** and is **centered on the screen**.  
- The `SnakePanel` is added to the frame, and `pack()` ensures the window resizes correctly.  

### **3. Initializing Game Components (SnakePanel.java)**
- The `SnakePanel` class extends `JPanel` and handles **game rendering and logic**.
- The constructor:  
  - Initializes the game board (`500x500` pixels).  
  - Sets background color and adds a key listener (`MyKey.java`).  
  - Calls `playGame()` to start the game.  

### **4. Game Starts (playGame Method)**
- The `playGame()` method initializes:
  - The snake with a default length of **5 units**.  
  - Places the first food randomly using `addFood()`.  
  - Starts a **timer** (`Timer(130, this)`) that triggers `actionPerformed()` every 130 milliseconds.  

### **5. Game Loop (actionPerformed Method)**
- This method is triggered by the timer.  
- It continuously **updates the game state** by:  
  - Moving the snake (`move()`).  
  - Checking if the snake **eats food** (`checkFood()`).  
  - Checking if the snake **collides** (`checkHit()`).  
  - Calling `repaint()` to **redraw the screen** with updated positions.  

### **6. Handling Movement (move Method)**
- Moves the snake by shifting each part of its body forward.  
- Updates the head position based on the current **direction** (`L`, `R`, `U`, `D`).  
- The direction is **controlled via keyboard input** (`MyKey.java`).  

### **7. Handling Keyboard Input (MyKey.java)**
- The `MyKey` class listens for **arrow key presses**.  
- Ensures the snake **cannot reverse direction** (e.g., if moving right, it can't turn left instantly).  

### **8. Checking for Food Collision (checkFood Method)**
- If the snake's head reaches the **food’s coordinates**, it:  
  - **Increases** the snake length.  
  - **Increases** the player's score.  
  - Calls `addFood()` to generate **new food** at a random location.  

### **9. Checking for Collisions (checkHit Method)**
- If the snake’s head collides with:  
  - **Its own body** → `running = false`, game over.  
  - **The game boundaries** → `running = false`, game over.  
- If the game ends, the timer stops.  

### **10. Drawing Graphics (draw & paintComponent Methods)**
- The `draw()` method renders the game:  
  - **Food** → Drawn as a red oval.  
  - **Snake** → The head is white, and the body is purple.  
  - **Score** → Displayed on the screen.  
- When `gameOver()` is triggered:  
  - Displays `"Game Over"` in the center.  
  - Displays the **final score**.  

---

## **Project Structure**

 ├── Game.java           # Interface defining core game methods

 ├── GameFrame.java      # JFrame setup for the game window

 ├── GamePlayer.java     # Main entry point of the game

 ├── MyKey.java          # Key listener for controlling the snake

 ├── SnakePanel.java     # Core game logic and rendering


---

## **Installation & Running the Game**
1. Ensure you have **Java JDK 8+** installed.
2. Clone this repository:
   
    "git clone https://github.com/yourusername/snake-game.git"
  
3. Navigate to the project folder:
   
     "cd snake-game"
   
4. Compile the Java files:
   
      "javac main/*.java"
   
5. Run the game:
   
     "java main.GamePlayer"
   

---

## **Controls**
| Key        | Action       |
|------------|-------------|
| ⬆️ Up      | Move Up     |
| ⬇️ Down    | Move Down   |
| ⬅️ Left    | Move Left   |
| ➡️ Right   | Move Right  |

---

## **Future Enhancements**
- Add **different difficulty levels**.  
- Implement **sound effects** for eating and collisions.  
- Improve **graphics and animations**.  
- Store **high scores** and allow leaderboard tracking.  

---

## **License**
This project is open-source under the **MIT License**.  

---

Enjoy playing the **Snake Game!** 🚀  

---



