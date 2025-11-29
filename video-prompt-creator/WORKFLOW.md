# Video Prompt Creator Workflow

This document outlines the step-by-step workflow for using the Video Prompt Creator plugin to generate cinematic video prompts for Sora 2.

## Prerequisites
- Ensure the plugin is registered in your `.claude-plugin/marketplace.json`.
- You have access to the **Video Prompt Architect** agent.

## Workflow Steps

### 1. Ideation & Research
Start with a rough idea or ask for inspiration.
*   **Example Input**: "I want a video of a cyberpunk detective walking in the rain."
*   **Research**: If you're stuck, ask the agent: "Research some cool sci-fi concepts for a video series." The agent will use the `research-story-topic` skill to give you visual ideas.

    *   **Example**: "The detective walks down the street, sees a clue, picks it up, and looks around suspiciously."
2.  Ask the agent: "Generate an episode storyboard for this sequence."
3.  The agent will use the `generate-storyboard` skill to break this down into **7-10 distinct clips**, each representing a 15-second segment.
4.  It will output a numbered list of clips (Clip 1, Clip 2, etc.).
5.  **Production**: You will generate each clip individually in Sora 2 using the descriptions provided.

### 5. Production (Sora 2)
1.  Copy the generated prompt (from Step 3) or the individual clip descriptions (from Step 4).
2.  Paste them into the Sora 2 interface.
3.  Generate your video!
4.  **Stitch**: Combine the generated 15s clips in your video editor to form the full episode.

## Tips
- **Be Specific**: The more details you give the agent about mood and style, the better the result.
- **Iterate**: Use the agent to tweak specific parts, like "Change the time of day to sunset" or "Use a wide-angle lens."
