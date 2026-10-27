# Development Notes

Pixel Game is developed iteratively with gameplay logic, visual assets, and collision configuration kept as separate concerns.

## Player Loop

```text
Input -> Direction -> Velocity -> Collision -> Animation
                  \-> Combat State -> Attack / Projectile
```

## Asset Workflow

Aseprite is used for character and animation artwork. Exported assets are imported into Godot and configured independently from player logic, allowing artwork to change without rewriting movement code.

## Current Focus

The project is progressing from foundational movement and animation toward combat, projectiles, HUD systems, player resources, and progression.

## Portfolio Scope

The working game repository remains separate. This showcase focuses on the systems and development process without publishing the complete project source.
