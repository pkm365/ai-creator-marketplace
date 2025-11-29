---
name: create-video-prompt
description: Generates a detailed video prompt based on the "Mega Prompt" template.
---

# Create Video Prompt

## Overview
This skill generates a high-fidelity, cinematic video prompt for Sora 2, packaged as a structured JSON object. It assembles various "middle artifacts" (Style Config, Audio Config, Content) to ensure a complete and production-ready prompt.

## When to Use
Use this skill when:
- The user wants to generate a single video clip.
- You need a structured output that includes metadata, style settings, and audio cues.
- You are integrating with a system that parses JSON prompts.

## Workflow

### Step 1: Analyze Request
-   Identify the core **Topic**, **Style**, and key **Elements**.
-   Determine if a specific **Style Preset** (e.g., `cyberpunk_noir`, `wes_anderson_symmetrical`) applies.

### Step 2: Assemble Middle Artifacts
1.  **Technical Specs (The Look)**:
    -   Load `templates/styles/style-library.json`.
    -   If a preset is selected, apply its `camera_system`, `lens_choice`, `film_stock`, `lighting_setup`, and `atmospherics`.
    -   If no preset matches, manually define these specs based on the user's description.
    -   Define **FPS** (usually 24fps for cinematic, 30/60 for digital).
2.  **Content Generation**:
    -   **Environment**: Lighting setup, atmospherics (fog, dust).
    -   **Character**: Skin texture details, wardrobe, and **Fabric Physics**.
    -   **Pacing Strategy**: Determine the rhythm based on the topic.
        -   *Fast Cuts* (Action/Thriller): `0-3s`, `3-12s`, `12-15s`.
        -   *Slow Burn* (Drama/Atmosphere): `0-8s`, `8-13s`, `13-15s`.
        -   *Balanced* (Standard): `0-5s`, `5-10s`, `10-15s`.
    -   **Timeline**: Create exactly 3 segments using the calculated time ranges.
        -   *Segment 1 (Hook)*: Establishing shot + Camera Move.
        -   *Segment 2 (Development)*: Action + **Physics Interaction** + VFX.
        -   *Segment 3 (Climax)*: Resolution + Final Camera Move.
3.  **Audio Config**:
    -   Ambient sound, specific SFX, and musical mood.

### Step 3: Fill Schema
-   Load `templates/prompt-schema.json`.
-   Populate all fields with the generated content.

## Output Structure

Return a single JSON code block:

```json
{
  "meta": { "camera_system": "...", "lens_choice": "...", ... },
  "content": {
    "character": { "fabric_physics": "...", ... },
    "timeline": [ ... ]
  },
  ...
}
```

## Example Execution

**Input**: "A cyberpunk detective walking in the rain."

**Result**:
```json
{
  "meta": {
    "topic": "Cyberpunk Detective",
    "pacing_strategy": "Slow Burn",
    "camera_system": "Arri Alexa 65",
    "lens_choice": "Panavision C-Series Anamorphic",
    "film_stock": "Digital with Kodak 2383 emulation",
    ...
  },
  "content": {
    "character": {
      "description": "Detective in a trench coat...",
      "skin_texture": "Wet skin, raindrops beading on stubble, subsurface scattering from neon lights",
      "fabric_physics": "Heavy synthetic leather coat weighed down by water, stiff movement",
      ...
    },
    "timeline": [
      {
        "time_range": "00s - 08s",
        "type": "Establishing",
        "action": "Walking through a neon-lit alley...",
        "camera_move": "Slow dolly back",
        "focus": "Rack focus from rain on lens to detective's face"
      },
      ...
    ]
  },
  ...
}
```
