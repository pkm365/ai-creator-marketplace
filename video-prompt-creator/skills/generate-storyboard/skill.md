---
name: generate-storyboard
description: Creates a detailed storyboard or shot list for a video sequence (Episode).
---

# Generate Storyboard

## Overview
This skill breaks down a narrative script or sequence description into a structured "Episode" of 7-10 distinct video clips. Each clip is designed to be 15 seconds long, ensuring continuity and narrative flow for Sora 2 generation.

## When to Use
Use this skill when:
- The user wants to tell a story longer than 15 seconds.
- You need to plan a sequence of events (e.g., a chase scene, a dialogue, a montage).
- The user provides a script or a rough plot outline.

## Workflow

### Step 1: Analyze Narrative
-   Read the provided `script` or description.
-   Identify the **Season Theme** (if part of a larger arc) and **Episode Theme**.
-   Determine the overall **Atmosphere** and **Voice Over** style (e.g., "minimalist", "documentary tone").

### Step 2: Break Down into Clips
-   Divide the story into 7-10 segments (Clips).
-   Ensure each segment can be visually told in ~15 seconds.
-   **Continuity**: Check that the end of Clip N flows logically into the start of Clip N+1.

### Step 3: Define Shot Details
For each clip, define:
-   **Shot Type**: WS (Wide), MS (Medium), CU (Close Up), etc.
-   **Action**: What happens? (Movement, lighting changes).
-   **Atmosphere/Lighting**: Specific mood for this shot.
-   **Sound/VO**: Ambient sounds or specific voice-over lines.
-   **Goal**: Why is this shot here? (Establish setting, show emotion, climax).

### Step 4: Format Output
-   Follow the structure in `../templates/cinematic-sequence.md`.
-   Include a header with **Episode Theme**, **Atmosphere**, and **Voice Over** summary.

## Output Structure

```markdown
### Episode: [Title]
**Theme**: [Theme description]
**Atmosphere**: [Mood description]
**Voice Over Style**: [Style description]

1. **Clip 1: [Type] / [Lens]**
   [Description of action and environment]
   *Atmosphere*: [Specific mood]
   *Sound/VO*: [Audio cues]
   *Goal*: [Narrative purpose]

2. **Clip 2: [Type] / [Lens]**
   ...
```

## Example Execution

**Input**: "A hero finds a magic sword in a cave."

**Result**:
1. **Clip 1: Establishing / WS / 24mm**
   Dark cave entrance, hero silhouettes against the light.
   *Goal*: Establish the danger.
2. **Clip 2: Discovery / MS / 50mm**
   Hero walks towards a glowing pedestal. The sword hums.
   *Goal*: Build anticipation.
...
