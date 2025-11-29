---
name: optimize-visual-fidelity
description: Enhances raw concepts with professional cinematic terminology, lighting setups, and material textures to ensure high-quality generation.
---

# Optimize Visual Fidelity

## Overview
This skill acts as a "Cinematography Specialist". It takes a basic scene description and injects high-fidelity keywords related to lighting, camera gear, texture, and color grading. It is designed to maximize the aesthetic output of models like Sora 2.

## When to Use
Use this skill before calling `create-video-prompt` or `generate-storyboard` when:
- The user's description is too simple (e.g., "A woman standing in a room").
- The user specifically asks for "High Quality," "Realistic," or "Cinematic" results.
- You want to ensure the lighting and texture details are physically accurate.

## Workflow

### Step 1: Analyze the Base Concept
-   Identify the core subject and action.

### Step 2: Apply the "Cinematic Layer" (The 4 Pillars)
Add details for the following four categories:

1.  **Photography Gear**:
    -   **Camera**: Alexa 65, IMAX 70mm, Red Komodo (for action).
    -   **Lens**: Panavision C-Series (anamorphic flares), Leica Noctilux (creamy bokeh), Macro 100mm.
    -   **Film Stock**: Kodak Vision3 500T (grainy, warm), Fujifilm Eterna (soft, desaturated).

2.  **Lighting & Atmosphere**:
    -   **Technique**: Rembrandt lighting, Chiaroscuro, Volumetric God Rays, Practical lighting.
    -   **Environment**: Dust motes, humidity haze, rain slick, subsurface scattering on skin.

3.  **Material & Texture**:
    -   Describe specific fabrics (silk, distressed leather, heavy wool).
    -   Describe surfaces (oxidized copper, brushed aluminum, peeling paint).

4.  **Camera Movement Dynamics**:
    -   Specific moves: "Slow push-in," "Orbit," "Dutch angle," "Handheld shaker."

### Step 3: Format Output
-   Return a refined text block that can be directly fed into the mega-prompt template.

## Output Structure

```markdown
### Visual Upgrade
**Gear**: [Camera, Lens, Film Stock]
**Lighting**: [Technique, Environment]
**Texture**: [Material details]
**Action**: [Movement dynamics]
```

## Example Execution

**Input**: "A cyberpunk samurai drawing his sword in the rain."

**Result**:
```markdown
### Visual Upgrade
**Gear**: Arri Alexa LF with Panavision Auto-Panatar lenses (anamorphic blue flares).
**Lighting**: Neon-noir aesthetic. Key light from a flickering magenta neon sign, rim light is cool cyan. Heavy volumetric fog diffusion.
**Texture**: The samurai's armor is brushed carbon fiber with water beading off the surface. The sword is Damascus steel, reflecting the neon city.
**Action**: 120fps slow motion capture. Raindrops are frozen in mid-air as the blade cuts through them.
```
