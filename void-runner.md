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


# Expanded

# VOID-RUNNER: Expanded Design Document

## 1. Narrative: The Ghost in the Machine

**The Setting:** The "Aethelgard Mainframe," a god-like supercomputer that once managed an entire civilization's digital consciousness, has begun to undergo "The Great Defragmentation"—a catastrophic system collapse. As the system deletes itself to preserve core functions, a chaotic void of corrupted data is consuming everything.

**The Protagonist:** You are an **Echo**, a fragmented remnant of a high-level administrator's consciousness. You have no physical form, only a digital avatar composed of pure light and logic.

**The Objective:** You must descend through the collapsing layers of the mainframe, from the polished upper-tier directories to the raw, unstable Kernel at the center. Your goal is to reach the "Source Core" to initiate a hard reboot of the system, potentially saving the remaining digital souls or erasing the corruption forever.

---

## 2. Bestiary (Enemies)

Enemies are categorized by their visual "Glitch" intensity. High-intensity enemies flicker more violently on the screen.

### 2.1 Fodder (Low Threat)
* **Bit-Flies:** Small, fast-moving clusters of pixels. They don't deal much damage but attempt to swarm the player, making movement difficult.
* **Null-Walkers:** Slow, shambling humanoid silhouettes. They move toward the player and deal moderate contact damage.

### 2.2 Combatants (Medium Threat)
* **Buffer-Snipers:** Stationary or slow-moving units that fire slow-moving, high-damage "Data Packets" (large glowing projectiles). They require the player to use the Dash mechanic to dodge.
* **Glitch-Shades:** Erratic enemies that "stutter" across the screen. They utilize short-range teleportation (flickering out of existence and reappearing) to close the gap.

### 2.3 Elites & Bosses (High Threat)
* **Logic-Crushers:** Massive, heavy-duty geometric shapes (cubes/pyramids). They act as tanks, absorbing significant damage and performing wide-area "Shockwave" attacks.
* **The Firewall Sentinel (Sector Boss):** A massive, multi-segmented entity that guards the transition between sectors. It fires patterned laser grids that the player must navigate through using precise movement.

---

## 3. Arsenal & Abilities

### 3.1 Base Weapons (Found via Data Terminals)
* **Pulse Carbine:** The standard-issue weapon. Rapid-fire, low recoil, medium damage.
* **Ion Repeater:** Fires heavy, slow-moving bolts that pierce through multiple enemies.
* **Plasma Scatter:** A short-range "shotgun" style weapon that fires a cone of high-intensity particles, excellent for clearing Bit-Flies.

### 3.2 Neural Augments (Abilities)
* **Phase Dash:** Upgrades the standard dash. At higher levels, the dash leaves a trail of "Static Damage" that hurts enemies.
* **Overclock:** A temporary burst mode. For 5 seconds, the player's movement speed and fire rate are doubled, but they take 25% more damage afterward due to "System Heat."
* **Kinetic Shield:** Generates a circular barrier around the player that absorbs a set amount of damage before shattering.

---

## 4. Environments & Themes

To optimize the Atari 800's hardware, environments are defined by distinct color palettes and tile-set behaviors.

### 4.1 Sector 1: The Neon Core (The Upper Tiers)
* **Visuals:** High-contrast Cyan and Magenta. Clean, geometric architecture. Smooth, scrolling backgrounds.
* **Atmosphere:** Organized but frantic. The feeling of a high-speed data highway.

### 4.2 Sector 2: The Data Graveyard (The Sub-Directories)
* **Visuals:** Darker tones. Deep Purples and Lime Greens. The background features "debris"—flickering, broken tiles and floating, non-interactive sprites to simulate a junkyard.
* **Atmosphere:** Claustrophobic and decaying.

### 4.3 Sector 3: The Kernel Abyss (The Core)
* **Visuals:** Monochromatic/High-Intensity. Harsh Whites and Reds on Pitch Black. The environment itself feels unstable, with tiles occasionally shifting or "glitching" out of place.
* **Atmosphere:** Pure digital chaos. High difficulty, high reward.

---

## 5. Interactable Objects

* **Data Terminals:** The primary source of upgrades. Interacting with one pauses the combat loop and presents the player with three randomized Augment choices.
* **Fragment Nodes:** Glowing orbs of light. Collecting these grants "Data Fragments" (XP) used for both mid-run upgrades and meta-progression.
* **Firewall Gates:** Large, indestructible barriers that block progress. These must be destroyed by defeating a specific number of enemies or by finding a "Decryption Key" drop.
* **System Stabilizers:** Rare, interactable objects that, when activated, temporarily clear all "Bit-Flies" from the screen and restore a small amount of player health.
