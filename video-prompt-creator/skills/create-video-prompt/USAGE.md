# Create Video Prompt - Usage Guide

This skill is the "Builder" of the system. It generates the final, executable JSON prompt for Sora 2 using the **Mega Prompt V2** structure.

## Key Features

### 1. Mega Prompt V2 Structure
The output is a structured JSON object designed for physical simulation engines.
-   **Meta**: Technical specs (Camera, Lens, Film Stock).
-   **Content**: Detailed environment and character descriptions with *Fabric Physics* and *Skin Texture*.
-   **Timeline**: Precise 15s orchestration.

### 2. Dynamic Pacing Strategy
The skill automatically calculates the best rhythm based on your content:
-   **Fast Cuts** (Action/Thriller): `0-3s` (Hook) -> `3-12s` (Fight) -> `12-15s` (End)
-   **Slow Burn** (Drama/Atmosphere): `0-8s` (Build-up) -> `8-13s` (Reveal) -> `13-15s` (Fade)
-   **Balanced** (Standard): `0-5s` -> `5-10s` -> `10-15s`

### 3. Style Library Integration
The skill has access to `style-library.json` containing high-fidelity presets:
-   `cyberpunk_noir`
-   `studio_ghibli_realism`
-   `analog_horror`
-   `wes_anderson_symmetrical`
-   `epic_fantasy`

## How to Use

**Basic Command**:
> "Create a video prompt for a cyberpunk detective."

**Advanced Command (with Style & Pacing)**:
> "Create a video prompt for a samurai duel. Use the 'Kurosawa' style (High Contrast B&W) and make it 'Fast Cuts' for high action."

**What Happens**:
1.  The Agent selects the style (or creates a custom one).
2.  It determines the Pacing Strategy (Fast Cuts).
3.  It fills the Mega Prompt V2 template.
4.  It outputs the JSON code block.
