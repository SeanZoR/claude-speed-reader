---
description: Launch RSVP speed reader for text
argument-hint: [text to read]
allowed-tools: Write, Bash, Read
---

# Speed Reader

Launch the RSVP speed reader to display text one word at a time with Spritz-style ORP (Optimal Recognition Point) highlighting.

## Instructions

1. **Get the text:**
   - If arguments provided below, use that text
   - Otherwise, extract the main content from your **previous response** in this conversation (the assistant message before the user ran /speed)

2. **Prepare the content:**
   - Strip markdown formatting (headers, bold, links, code blocks)
   - Keep clean, readable prose
   - Escape quotes (`"` → `\"`) and backslashes (`\` → `\\`) for JavaScript string

3. **Write and launch:**
   - Read the HTML file at `~/.claude/skills/speed/data/reader.html`
   - Find the line `<!-- CONTENT_PLACEHOLDER -->`
   - Insert a script tag BEFORE it with the content:
     ```html
     <script>window.SPEED_READER_CONTENT = "your escaped text here";</script>
     ```
   - Write the modified HTML back to the same file
   - Run: `open ~/.claude/skills/speed/data/reader.html`

4. **Confirm:** Tell the user it's opening. Mention `Space` to play/pause, arrows to adjust speed.

## Arguments
$ARGUMENTS
