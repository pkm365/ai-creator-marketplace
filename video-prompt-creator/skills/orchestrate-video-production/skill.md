---
name: orchestrate-video-production
description: The main entry point for the Video Prompt Creator system. Orchestrates the entire workflow from ideation to final prompt generation by coordinating specialized skills and the Creative Director agent.
---

# Orchestrate Video Production

## Overview
This is the **Master Workflow** skill. It does not generate content itself but coordinates the execution of other skills to ensure a professional, consistent, and high-quality output. It enforces the "Director's Workflow".

## When to Use
Use this skill when:
- The user wants to create a video from scratch.
- The user has a vague idea and needs a full production pipeline.
- You need to ensure all quality checks (Visual Lock, Pacing, Fidelity) are applied.

## Workflow

### Step 0: Project Setup
1.  **Create Project Directory**:
    -   Format: `./video-projects/[project_name]/`
    -   Example: `./video-projects/cyberpunk_detective_01/`
    -   **ALL** subsequent artifacts must be saved here.

### Step 1: Ideation & Research (Optional)
If the user doesn't have a concrete concept:
1.  Invoke `research-story-topic`.
2.  Goal: Identify a unique angle and visual style.
3.  Save output to: `[project_dir]/research.md`

### Step 2: Creative Direction (The Polish)
**MANDATORY**: Before planning, consult the **Creative Director**.
1.  Invoke the `creative-director` subagent.
2.  Task: "Optimize the visuals for this concept. Define the camera gear, lighting, and style."
3.  Output: A set of "Cinematography Notes" (The 4 Pillars).
4.  Save output to: `[project_dir]/cinematography_notes.md`

### Step 3: Storyboard & Consistency (The Plan)
1.  Invoke `generate-storyboard`.
2.  Input: The concept + The Creative Director's notes.
3.  **Constraint**: Tell the skill to save output to `[project_dir]/storyboard.md`.
4.  Goal: Create a **Master Visual Lock** and a 7-10 clip shot list.

### Step 4: Production (The Build)
For each clip in the storyboard:
1.  Invoke `create-video-prompt`.
2.  Input:
    -   Clip details from the storyboard.
    -   **Master Visual Lock** details.
    -   **Pacing Strategy**.
3.  **Constraint**: Tell the skill to save output to `[project_dir]/prompts.json` (append mode or single file).
4.  Output: A structured JSON prompt for Sora 2.

## Output Structure
The final output should be a **Production Report** saved to `[project_dir]/production_report.md` containing:
1.  **Project Title**
2.  **Master Visual Lock**
3.  **Episode Plan**
4.  **Ready-to-Use Prompts**

## Example Command
> "Orchestrate a video production for a sci-fi thriller about a rogue AI. Save everything to ./video-projects/rogue_ai/"
