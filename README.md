# Pixel Game

A 2D pixel-art action/adventure game built with Godot, featuring custom character art, movement, combat systems, collisions, and RPG-style player mechanics.

> **Portfolio Showcase** — The active game source is maintained separately. This repository highlights the project's design, systems, tooling, and development work.

## Overview

Pixel Game is an ongoing game-development project focused on building a 2D action/adventure experience from the ground up rather than relying on a prebuilt game template.

The project combines programming in Godot with original pixel-art workflows in Aseprite.

## Current Systems

- WASD player movement
- Diagonal movement
- Walk and idle animations
- Directional character states
- Shift-to-run movement
- Collision handling
- Environmental props and collision boundaries
- Melee fist combat animations
- Projectile / ki-blast system design
- Player HP system
- EXP and progression UI
- Stamina and mana systems
- HUD and menu development

## Technology

| Area | Technology |
| --- | --- |
| Engine | Godot |
| Programming | GDScript |
| Pixel Art | Aseprite |
| Version Control | Git / GitHub |
| Art Style | 2D Pixel Art |

## Game Architecture

```text
Player Input
     |
Player Controller
     |
 +---+-------------------+
 |           |           |
Movement   Combat       Stats
 |           |           |
Animation  Melee /     HP / EXP
State      Projectiles Stamina / Mana
 |           |           |
 +-----------+-----------+
             |
          Game World
             |
       Collision / Props
```

## Character System

The player controller manages movement direction, running speed, animation state, and collision behaviour. Directional animations support up, down, left, right, and diagonal movement.

Combat is designed around close-range fist attacks with support for ranged abilities such as energy projectiles.

## Art Pipeline

Character and game assets are created and edited in Aseprite before being imported into Godot as sprites and animation frames.

The workflow includes:

1. Create or edit pixel-art assets in Aseprite.
2. Export sprite sheets.
3. Import assets into Godot.
4. Configure SpriteFrames / animations.
5. Connect animation states to player movement and combat.
6. Configure collision shapes separately from visual sprites.

This keeps gameplay logic independent from the underlying artwork.

## RPG Systems

The HUD is being designed around four core player resources:

- **HP** — player health
- **EXP** — character progression
- **Stamina** — physical actions
- **Mana** — abilities and energy-based attacks

These systems provide the foundation for future combat, progression, enemies, and abilities.

## What This Project Demonstrates

- Godot game development
- GDScript programming
- State-driven animation
- 2D collision systems
- Player-controller design
- Sprite-sheet workflows
- Custom pixel-art asset creation
- Combat and projectile architecture
- UI/HUD implementation
- Git-based iterative development

## Roadmap

Planned development includes expanded combat, enemies, abilities, progression, world interaction, menus, and additional custom assets.

## Screenshots

Gameplay screenshots, sprite sheets, and short GIF demonstrations can be added here as development progresses.

---

An ongoing project combining software engineering, game systems, and original pixel-art development.
