# Game Systems

This document tracks the major technical systems in Pixel Game and distinguishes implemented foundations from systems still being developed.

## Player Movement

The player controller supports cardinal and diagonal movement, with a separate run modifier. Movement direction feeds the animation state so the visual character tracks gameplay direction.

## Animation

Idle and movement animations are direction-aware. Artwork is authored in Aseprite and exported for use in Godot's animation workflow.

Combat animation is being expanded around directional melee attacks and ranged abilities.

## Collision

Player and environmental collision are configured independently from sprite scale. This makes it possible to tune the visual presentation without making collision boundaries depend directly on artwork dimensions.

## HUD & Player Resources

The current interface establishes the visual foundation for:

- Health
- Mana / energy
- Stamina
- Experience
- Player level

The next stage is connecting these UI elements more deeply to gameplay events such as damage, ability use, running, and experience gain.

## Melee Combat

Directional fist combat is planned around an attack state, directional animation, temporary attack hitbox, and damage interaction.

```text
Attack Input
   |
Facing Direction
   |
Attack Animation
   |
Enable Hitbox
   |
Detect Target
   |
Apply Damage
   |
Disable Hitbox
```

## Projectile Abilities

Ranged abilities are designed as separate scene objects rather than animation frames that manually travel across the screen.

```text
Player
  |
Ability Input
  |
Attack Animation
  |
Instantiate Projectile
  |
Direction + Velocity
  |
Collision Detection
  |
Damage / Despawn
```

This keeps the player animation, projectile visuals, and projectile physics independently maintainable.

## Art Pipeline

Aseprite is the source tool for pixel-art creation and animation. Godot is responsible for runtime animation, movement, collision, gameplay state, and effects.

This separation allows the same art workflow to support characters, attacks, projectiles, enemies, props, and future world assets.
