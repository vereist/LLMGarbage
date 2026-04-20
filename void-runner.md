# Prompt
Create a one to two page game design document for a game that would run on an Atari 800. Don't make a text-based adventure like Zork. You can use whatever combination of input devices you want (keyboard, mouse, joystick, paddles), but the keyboard shouldn't be used for typing out text commands. Assume a top spec unit with 48K of memory and writable storage (floppy disk, cassette tape). As long as they fit the hardware constraints, modern game mechanics should be preferred. You can pick any theme you'd like.

# Game Design Document: VOID-RUNNER

**Title:** VOID-RUNNER  
**Platform:** Atari 800 (48K RAM, Floppy Disk Drive)  
**Genre:** Top-Down Action Roguelite  
**Theme:** Cyberpunk / Synthwave  

---

## 1. Executive Summary
VOID-RUNNER is a fast-paced, top-down action game where the player navigates a procedurally generated digital labyrinth. Unlike traditional Atari arcade shooters, VOID-RUNNER incorporates modern "roguelite" elements: permanent progression through collected data, randomized power-ups, and high-difficulty combat loops. The aesthetic focuses on high-contrast neon colors against black backgrounds to maximize the visual impact of the Atari’s color palette while minimizing processing overhead.

## 2. Gameplay Mechanics

### 2.1 Core Loop
1. **Enter Sector:** The player starts in a randomly generated room.
2. **Combat & Collect:** Defeat "glitch" enemies to collect "Data Fragments" (XP).
3. **Upgrade:** Upon clearing a room or finding a terminal, the player chooses one of three randomized "Neural Augments" (e.g., increased fire rate, dash distance, or shield strength).
4. **Permadeath:** If the player's integrity reaches zero, the run ends. Data fragments collected are converted into "Core Credits" used for permanent stat boosts in the main menu.

### 2.2 Movement and Combat
* **Dash Mechanic:** A short-range, invulnerability-frame burst of speed. This allows for the "dodge-roll" style gameplay found in modern action titles.
* **Directional Shooting:** The player shoots in the direction of movement or via a secondary aiming axis.
* **Procedural Generation:** To stay within the 48K limit, the game uses a "chunk-based" generation system. Pre-designed room layouts (tiles) are stitched together using a seed-based algorithm, ensuring variety without requiring massive amounts of RAM for map data.

### 2.3 Progression Systems
* **Roguelite Meta-progression:** Between runs, players use Core Credits at the "Mainframe" (Title Screen) to increase base health or starting weapon power.
* **Augment Synergy:** Certain augments interact. For example, "Electric Rounds" combined with "Chain Lightning" creates a massive area-of-effect attack.

## 3. Controls

The game is designed for a combination of a standard Atari Joystick and the Keyboard for high-precision input.

* **Joystick:** 
    * **Directional Pad:** Movement of the player character.
* **Keyboard:**
    * **Spacebar:** Primary Fire.
    * **Left Shift:** Dash (utilizing the dash-invulnerability mechanic).
    * **'E' Key:** Interact (with terminals or loot).
    * **'Esc' Key:** Pause/Menu.

## 4. Visual and Audio Style

### 4.1 Visuals
* **Graphics Mode:** Uses a combination of Player-Missile Graphics (PMG) for smooth enemy and player movement and bitmapped Playfield graphics for the environment.
* **Color Palette:** Limited to high-saturation "Neon" colors: Cyan, Magenta, Lime Green, and White on a Pitch Black background. This creates a "glow" effect and keeps the CPU focused on sprite movement rather than complex background rendering.
* **UI:** Minimalist HUD at the top of the screen showing Health (a colored bar) and Data Fragments (numeric count).

### 4.2 Audio
* **Music:** Utilizing the POKEY chip, the game features a driving, multi-channel synthwave soundtrack with heavy bass rhythms and arpeggiated melodies.
* **Sound Effects:** High-frequency "bit-crunch" sounds for laser fire, low-frequency thuds for explosions, and a distinct melodic "ping" when an upgrade is selected.

## 5. Technical Specifications (Atari 800 Constraints)

* **Memory Management:** 
    * **RAM (48K):** The bulk of the memory is dedicated to the "Current Sector" state (enemy positions, projectile vectors) and the "Augment Table." 
    * **Storage (Floppy):** Level chunks and the permanent "Core Credit" save file are stored on the disk.
* **CPU Optimization:** By using PMG for all moving entities, the game avoids the heavy processing cost of full-screen bitmap manipulation, allowing for a high frame rate even when many projectiles are on screen.
* **Randomization:** A pseudo-random number generator (PRNG) seeded by the system clock will drive the procedural layout and loot drops.
