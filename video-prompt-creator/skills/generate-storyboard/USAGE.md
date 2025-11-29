# Generate Storyboard - Usage Guide

This skill is the "Planner" of the system. It structures longer narratives into episodes of 15s clips, ensuring **Visual Consistency**.

## Key Features

### 1. Consistency Lock (Master Visual Lock)
Before generating any clips, this skill defines a `🔐 Master Visual Lock`. This block contains immutable details about:
-   **Protagonist**: Wardrobe, features, accessories.
-   **Environment**: Lighting key, weather.
-   **Style**: The chosen aesthetic.

**Why it matters**: It prevents the AI from "hallucinating" different clothes or lighting for the same character across different clips.

### 2. Episode Structure
It breaks the story into **7-10 distinct clips**. Each clip is designed to be exactly 15 seconds long, fitting Sora 2's generation window.

## How to Use

**Command**:
> "Generate a storyboard for a 2-minute video about a robot discovering a flower."

**What Happens**:
1.  The Agent defines the **Master Visual Lock** (e.g., "Robot: Rusty Unit 734, moss on shoulder").
2.  It outlines the **Shot List** (Clip 1 to Clip 8).
3.  It ensures every clip references the Master Lock details.

**Output Example**:
```markdown
#### 🔐 Master Visual Lock
> **Protagonist**: Unit 734, rusty beige metal, glowing yellow eye, moss patch on left shoulder.
...

#### Shot List
1. **Clip 1**: Unit 734 (see Master Lock) wakes up in the rubble...
2. **Clip 2**: Unit 734 walks...
```
