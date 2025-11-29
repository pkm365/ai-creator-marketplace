---
name: research-story-topic
description: Research and brainstorm interesting, visually compelling topics for video episodes.
---

# Research Story Topic

## Overview
This skill acts as a creative engine for video episodes. It combines web research (for trends and tropes) with creative brainstorming to generate unique, visually striking story concepts suitable for Sora 2's capabilities.

## When to Use
Use this skill when:
- The user asks for ideas or inspiration (e.g., "Give me some sci-fi ideas").
- You need to find specific visual tropes for a genre (e.g., "What does Wuxia look like?").
- The user wants to explore a new topic before committing to a script.

## Workflow

### Step 1: Analyze Request
-   Determine the genre, theme, or mood requested.
-   If the request is open-ended, pick a trending or visually rich category.

### Step 2: Web Research (Optional)
-   If needed, use `search_web` to find:
    -   Visual aesthetics (colors, lighting).
    -   Common tropes and themes.
    -   Trending topics in short-form video.

### Step 3: Brainstorm Concepts
-   Generate 3 distinct concepts.
-   **Criteria**:
    -   **Visual**: Must look good in AI video (lighting, texture, motion).
    -   **Episodic**: Must have enough depth for 7-10 clips.
    -   **Feasible**: Avoid overly complex interactions that AI struggles with.

### Step 4: Format Output
-   Present the ideas clearly with titles, loglines, and visual hooks.

## Output Structure

```markdown
1. **[Title]**
   *   **Logline**: [One sentence summary]
   *   **Visual Hook**: [Key visual elements]
   *   **Episode Potential**: [How it spans multiple clips]
```

## Example Execution

**Input**: "Horror ideas."

**Result**:
1. **The Mirror World**
   *   **Logline**: A person discovers their reflection moves independently.
   *   **Visual Hook**: Glitching reflections, dark bathrooms, flickering neon.
   *   **Episode Potential**: Escalating creepiness, breaking the mirror, escape.
