---
name: generate-storyboard
description: Creates a detailed storyboard or shot list for a video sequence (Episode), ensuring strict visual consistency.
---

# Generate Storyboard (Consistency Locked)

## Overview
This skill breaks down a narrative script into a structured "Episode" of 7-10 distinct video clips. Crucially, it defines a "Master Visual Lock" first to ensure the character and environment remain identical across all clips.

## When to Use
Use this skill when:
- The user wants to tell a story longer than 15 seconds.
- You need to plan a sequence of events where character consistency is critical.

## Workflow

### Step 1: Define Master Visual Lock (The Consistency Anchor)
Before breaking down the story, define the immutable details:
-   **Character**: Exact wardrobe, age, ethnicity, key features (e.g., "scar on left cheek").
-   **Environment**: Lighting key, weather, primary colors.
-   **Style**: Reference to a specific Style Preset (e.g., `cyberpunk_noir`).

This block will be repeated or referenced in every clip prompt.

### Step 2: Break Down into Clips (Narrative Flow)
-   Divide the story into 7-10 segments.
-   Ensure narrative flow: Clip N end -> Clip N+1 start.

### Step 3: Define Shot Details
For each clip, define:
-   **Shot Type & Lens**: Mix wide/medium/close-up for rhythm.
-   **Action**: What happens?
-   **Physics/Transition**: How does this clip visually connect to the next?

## Output Structure

```markdown
### Episode: [Title]

#### 🔐 Master Visual Lock (Consistency Data)
> **Protagonist**: [Name], [Specific Details & Wardrobe]
> **Environment**: [Location & Lighting State]
> **Style**: [Reference to Style Preset]

---

#### Shot List
1. **Clip 1: [Type] / [Lens]**
   * **Subject**: [Protagonist Name] (Refer to Master Lock)
   * **Action**: [Action Description]
   * **Atmosphere**: [Specific mood]

2. **Clip 2: [Type] / [Lens]**
   ...
```

## Example Execution

**Input**: "A hero finds a magic sword."

**Result**:
```markdown
### Episode: The Sword of Aeons

#### 🔐 Master Visual Lock
> **Protagonist**: Kael, tall, weathered leather armor, red scarf, glowing blue amulet on chest.
> **Environment**: Bioluminescent cave, damp, teal ambient light.
> **Style**: Epic Fantasy

---

#### Shot List
1. **Clip 1: Establishing / Wide Angle**
   * **Subject**: Kael (wearing leather armor, red scarf) stands at the cave mouth.
   * **Action**: He steps tentatively into the teal light, hand on his dagger.
   * **Atmosphere**: Eerie silence, water dripping.

2. **Clip 2: Medium Shot / 50mm**
   * **Subject**: Kael scans the room.
   * **Action**: His eyes widen as he spots the sword on a pedestal.
   ...
```
