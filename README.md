# Pixel Game

**A top-down 2D pixel-art action RPG built in Godot with custom assets created in Aseprite.**

Pixel Game is an ongoing game-development project focused on building the core systems of a top-down action RPG from the ground up: character movement, animation, collisions, world building, player resources, combat, abilities, and progression.

> **Portfolio Showcase** — Active development is maintained separately. This repository documents the game, technical systems, art pipeline, and development process.

## Current Build

The current playable build includes a top-down outdoor environment with a controllable player character, environmental props, terrain variation, collisions, and an RPG-style HUD.

### Implemented

- WASD player movement
- Diagonal movement
- Shift-to-run
- Directional idle and walk animations
- Player/world collision
- Scaled environment and prop assets
- Top-down tile-based world
- Player HUD
- Health bar
- Mana/resource bar
- Stamina/resource bar
- Level display
- EXP tracking
- Custom pixel-art character and environment workflow

### In Development

- Directional melee fist attacks
- Ki/energy projectile attacks
- Combat state handling
- Damage and health interactions
- Expanded RPG progression
- Enemies and encounters
- Additional maps and environmental assets
- Menus and additional UI

## Tech Stack

| Area | Technology |
| --- | --- |
| Game Engine | Godot |
| Programming | GDScript |
| Pixel Art | Aseprite |
| Version Control | Git / GitHub |
| Art | Custom 2D pixel-art assets |
| Genre | Top-down action RPG |

## Gameplay Systems

### Player Controller

The player controller handles movement input, velocity, running, direction, animation selection, and interaction with the collision system.

```text
Keyboard Input
     |
Movement Vector
     |
Direction / Speed
     |
CharacterBody
     |
Collision Response
     |
Animation State
```

Diagonal input is supported while directional animations resolve to the appropriate sprite state.

### Animation System

Character animation is organized around player state and direction.

```text
Player State
├── Idle
│   ├── Up
│   ├── Down
│   ├── Left
│   └── Right
│
├── Walk / Run
│   ├── Up
│   ├── Down
│   ├── Left
│   └── Right
│
└── Combat
    ├── Melee
    └── Projectile
```

### Collision & World Interaction

Visual scale and collision are handled independently so character and environment art can be resized without coupling gameplay collision directly to sprite dimensions.

World props such as trees, terrain boundaries, and other obstacles can therefore have collision shapes tuned separately from their artwork.

## RPG HUD

The HUD is being built around the core resources needed for an action RPG:

- **HP** — player health
- **Mana / Energy** — ability resource
- **Stamina** — movement and physical-action resource
- **EXP** — progression toward the next level
- **Level** — current player level

Keeping these systems separate from the character artwork makes them reusable as combat and progression systems expand.

## Combat Direction

Combat is being designed around two complementary systems.

**Melee combat** uses directional fist attacks tied to the player's facing direction and animation state.

**Projectile combat** supports abilities such as a ki blast. The projectile is its own game object: the attack animation triggers the ability, while Godot handles projectile movement, collision, lifetime, and damage independently.

```text
Player Input
     |
Attack State
   /     \
Melee   Ability
 |         |
Hitbox   Spawn Projectile
 |         |
Damage   Velocity
           |
        Collision
           |
         Damage
```

## Aseprite → Godot Art Pipeline

Game artwork is created and edited in **Aseprite**, then imported into **Godot**.

```text
Aseprite
   |
Draw / Animate
   |
Sprite Sheet
   |
Export
   |
Godot Import
   |
SpriteFrames / Animation
   |
Game State
```

This workflow keeps source artwork separate from gameplay logic and makes it straightforward to replace or expand animations without rewriting the player controller.

### Typical Asset Workflow

1. Draw or edit the asset in Aseprite.
2. Build animation frames for the required directions.
3. Export the sprite sheet.
4. Import the texture into Godot.
5. Configure animation frames.
6. Connect the animation to player state.
7. Configure gameplay collision/hitboxes separately.

## Project Architecture

```text
                       GAME
                        |
          +-------------+-------------+
          |                           |
        Player                       World
          |                           |
   +------+------+              +-----+------+
   |      |      |              |            |
Movement Stats  Combat        Terrain      Props
   |      |      |              |            |
Animation|   Melee/Projectile  Tiles      Collision
          |
     HP / Mana /
    Stamina / EXP
          |
         HUD
```

## Development Goals

The project is intentionally being built system-by-system rather than from a complete RPG framework. That provides hands-on experience with how the individual parts of a game interact.

Areas being developed include:

- Player-state management
- Animation state transitions
- Physics and collision
- Combat hitboxes
- Projectile lifecycle
- Character stats
- Experience and levelling
- UI synchronization
- Enemy behaviour
- World interaction
- Asset pipelines

## What This Project Demonstrates

- Godot game development
- GDScript programming
- 2D movement and physics
- State-driven animation
- Collision design
- RPG HUD implementation
- Combat-system architecture
- Projectile design
- Custom sprite-sheet workflows
- Aseprite pixel-art production
- Git-based iterative development
- Separating visual assets from gameplay systems

## Repository Structure

```text
pixel-game-showcase/
├── README.md
└── docs/
    ├── DEVELOPMENT.md
    └── GAME-SYSTEMS.md
```

## Roadmap

The next major milestones are completing directional melee combat, implementing the ki-blast projectile system, connecting HP/resource systems to gameplay, adding enemies, and expanding the playable world.

## Project Status

**Active development.**

The working game project remains separate while this repository acts as a public engineering and game-development case study.

---

**Godot · GDScript · Aseprite · Pixel Art · Action RPG**
