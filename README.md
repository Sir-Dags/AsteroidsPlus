# ☄️ AsteroidsPlus

An enhanced take on the classic arcade game *Asteroids*, built in **Processing (Java)** with the Sprites library. Pilot your ship, blast asteroids into smaller pieces, grab shield power-ups, and survive two levels to win.

Created by **Team 08** for a Fundamentals of Programming course.

---

## 🚀 Project Overview

AsteroidsPlus extends a provided Asteroids starter framework with new team features. The project was used to practice:
* **Object-Oriented Design:** Building game entities (ship, asteroids, missiles, explosions, power-ups) as subclasses of a shared abstract `GameObject` sprite class.
* **State Machine Architecture:** Moving between Start, Level 1, Level 2, Win and Lose screens with a `GameState` enum and a central `nextLevelStateMachine()`.
* **Real-Time Input Handling:** Tracking held keys with a `KeyboardController` so movement, rotation and firing work smoothly together.
* **Collision Detection & Game Rules:** Handling ship–asteroid, missile–asteroid and missile–power-up collisions, plus health, energy, shields and lives.
* **Multimedia Integration:** Adding sprite sheets, animated banners, background music and sound effects through Processing's Sound library.
* **Team Git Workflow:** Building the game together and tracking changes with version control.

---

## ✨ Team Features

| Feature | Description |
| :--- | :--- |
| **Ship Selection Menu** | After pressing Start, choose one of three ship designs (`1`, `2`, `3`). |
| **Health Bar** | The ship has 100 health. Small asteroids deal 20 damage and big asteroids deal 30. A green health bar appears once the ship is damaged. |
| **Lives System** | The player starts with 3 lives. When health reaches 0, the ship explodes and respawns until no lives are left. |
| **Pause Screen** | Press `P` to pause and resume the game and the background music. |
| **Background Music** | A retro soundtrack plays during gameplay. |
| **Custom Sound Effects** | Each event has its own sound: missile launches, large and small asteroid explosions, and the ship exploding. |

---

## 📂 Directory Structure

```
.
├── .gitignore                                  # Ignores Processing export folders
├── README.md                                   # Project documentation (this file)
├── Screenshot 2026-10-04 125624.png            # Proof of Dates
├── Screenshot 2026-10-04 141914.png            # Gameplay screenshot
├── Team 08 Asteroids Project Team Features.docx  # Team feature write-up
└── AsteroidsPlus/                              # Processing sketch folder
    ├── AsteroidsPlus.pde        # Main sketch: setup, draw loop, level state machine
    ├── AsteroidsGameLevel.pde   # Shared level logic: updates and collisions
    ├── AsteroidsLevels.pde      # Level 1 and Level 2 definitions
    ├── GameLevel.pde            # GameState enum, base level, Start/Win/Lose levels
    ├── GameObject.pde           # Abstract sprite base class
    ├── Ship.pde                 # Player ship and missiles
    ├── Asteroid.pde             # Big and small asteroids
    ├── PowerUps.pde             # Power-up base class and shield power-up
    ├── Explosion.pde            # Large and small explosion animations
    ├── Banners.pde              # Animated "Game Over" and "Oh Yea" banners
    ├── Buttons.pde              # Clickable Start button
    ├── KeyboardController.pde   # Key-state tracking and pause handling
    ├── SoundPlayer.pde          # Loads and plays sound effects
    └── data/                    # Images (.png/.jpg) and audio (.wav) assets
```

---

## ⚙️ Requirements

| Requirement | Specification |
| :--- | :--- |
| **Language** | Processing (Java mode) |
| **IDE** | [Processing 4.x](https://processing.org/download) |
| **Libraries** | **Sprites** (S4P, by Peter Lager) and **Sound** (The Processing Foundation) |
| **Window Size** | 1000 × 700 pixels |
| **Input** | Keyboard and mouse |

---

## 🛠️ Build and Run

1. **Install Processing** from [processing.org](https://processing.org/download).

2. **Install the required libraries** in the Processing IDE:
   `Sketch → Import Library → Manage Libraries…`, then search for and install **Sprites** and **Sound**.

3. **Open the sketch:**
   `File → Open…` → `AsteroidsPlus/AsteroidsPlus.pde`
   (The folder name must stay `AsteroidsPlus` so it matches the main `.pde` file.)

4. **Run** the game with the ▶️ **Run** button or `Ctrl + R` (`Cmd + R` on macOS).

---

## 🎮 Controls

| Key / Input | Action |
| :--- | :--- |
| **Mouse Click** | Press the Start button |
| `1` / `2` / `3` | Choose your ship on the selection menu |
| `↑` (Up Arrow) | Thrust forward |
| `←` / `→` (Left / Right Arrows) | Rotate the ship |
| `Space` | Fire a missile (uses energy) |
| `P` | Pause / resume |

---

## 🧭 Gameplay & Examples

### Example 1: Starting a Game
1. Click the **Start** button on the title screen.
2. The ship selection menu appears. Press `1`, `2`, or `3` to choose a ship.
3. Level 1 begins with two large asteroids and the background music starts.

### Example 2: Combat & Survival
* Shoot a **big asteroid** and it breaks into **three small asteroids**.
* Each missile uses ship **energy** (white bar). Energy refills over time.
* A **shield power-up** appears every 10 seconds. **Shoot it** to get a 15-second shield (red bar and red glow) that blocks asteroid damage.
* When asteroids hit you, your **health** (green bar) drops. When it reaches 0 you lose a life and respawn.

### Example 3: Winning & Losing
* Clear every asteroid in **Level 1** to move on to **Level 2** (four large asteroids and faster missiles).
* Clear **Level 2** to reach the **Win** screen, with an animated "Oh Yea!" banner and a victory sound.
* Lose all **3 lives** to reach the **Game Over** screen.
* Both screens return to the title screen when their sound finishes.

### Screenshots

![Gameplay screenshot 1](Screenshot%202026-10-04%20125624.png)
![Gameplay screenshot 2](Screenshot%202026-10-04%20141914.png)

---

## 📄 File Summary

| File / Folder | Purpose |
| :--- | :--- |
| `.gitignore` | Specifies Processing export folders to ignore |
| `README.md` | Repository documentation, controls, and build guide |
| `Team 08 Asteroids Project Team Features.docx` | Team write-up describing the added features |
| | |
| `AsteroidsPlus.pde` | Entry point: `setup()`, `draw()`, input callbacks, and level transitions |
| `AsteroidsGameLevel.pde` | Abstract gameplay level: object lists, updates, collisions, health and lives |
| `AsteroidsLevels.pde` | `AsteroidsLevel1` and `AsteroidsLevel2`: asteroid spawns, power-ups, missiles, ship selection |
| `GameLevel.pde` | `GameState` enum, `GameLevel` base class, `StartLevel`, `WinLevel`, `LoseLevel` |
| `GameObject.pde` | Sprite base class with collision, active/inactive state, and bar drawing |
| `Ship.pde` | Player `Ship` (movement, energy, shield, health) and `Missile` |
| `Asteroid.pde` | `BigAsteroid` and `SmallAsteroid` classes |
| `PowerUps.pde` | Abstract `PowerUp` and `ShieldPowerup` |
| `Explosion.pde` | `ExplosionLarge` and `ExplosionSmall` animations |
| `Banners.pde` | Animated `GameOver` and `OhYea` banners |
| `Buttons.pde` | Abstract `Button` and `StartButton` |
| `KeyboardController.pde` | Tracks arrow and space key state and handles pausing |
| `SoundPlayer.pde` | Loads and plays all sound effects |
| `data/` | Sprite sheets, backgrounds, banners, and `.wav` audio files |
