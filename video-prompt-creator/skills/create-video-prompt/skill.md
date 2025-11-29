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
-   Determine if a specific **Style Preset** (e.g., Cyberpunk, Ghibli) applies.

### Step 2: Assemble Middle Artifacts
1.  **Style Config**:
    -   If a preset exists (e.g., `../templates/styles/cyberpunk.json`), load it.
    -   Otherwise, generate a custom style config (camera, lighting, color).
2.  **Content Generation**:
    -   Define `environment`, `character`, and the 15s `timeline`.
    -   Ensure the timeline has 3-4 distinct shots covering the 15s duration.
3.  **Audio Config**:
    -   Select ambient music and SFX.
    -   If the user requested a voice-over, write a short script (max 20 words for 15s).

### Step 3: Fill Schema
-   Load `../templates/prompt-schema.json`.
-   Populate all fields with the generated content.
-   Ensure `meta` fields (fps, resolution) are set correctly.

## Output Structure

Return a single JSON code block:

```json
{
  "meta": { ... },
  "content": { ... },
  "style_config": { ... },
  "audio_config": { ... }
}
```

## Example Execution

**Input**: "A cyberpunk detective walking in the rain."

**Result**:
```json
{
  "meta": {
    "topic": "Cyberpunk Detective",
    "style_preset": "Cyberpunk Noir",
    "duration_seconds": 15
  },
  "content": {
    "environment": {
      "description": "Futuristic Tokyo street, wet pavement...",
      ...
    },
    ...
  },
  "style_config": {
    "camera_movement": "Smooth tracking shots...",
    ...
  },
  "audio_config": {
    "ambient_music": "Synthwave, rain ambience...",
    ...
  }
}
```
