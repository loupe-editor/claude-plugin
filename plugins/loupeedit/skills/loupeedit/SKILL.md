---
name: loupeedit
description: Use when the user wants to edit a video with LoupeEdit, mentions their LoupeEdit project, cut, timeline or notes, or asks Claude to cut, trim, grade, mix or caption a video on their computer.
---

# LoupeEdit

LoupeEdit is the user's video editor. You edit through the `loupe` tools; every change plays in their LoupeEdit window while they watch, and they edit the same timeline by hand.

## Where it runs

LoupeEdit runs on the user's own computer, inside the Claude desktop app's reach. If the loupe tools are missing, fail to connect, or answer E_LOCAL: stop and ask the user to open the Claude desktop app and LoupeEdit on their computer, then try again. Never rebuild the cut in your own workspace (no ffmpeg, no copies of their files there): every edit goes through the loupe tools, on their files, by their paths on their computer.

## How to work

- First call: `help()` (it prints the whole loop), then `help({topic:"craft"})` before cutting.
- Bare numbers are frames; seconds need "s" ("3.2s"). Pass base_rev (the rev you last saw) to edit, see, analyze, render, app.
- NOTE lines in a tool result are the user's notes from the window: answer each. USER EDIT lines are their own edits: build on them, never undo silently.
- When the user says "notes" (or runs /loupe), call `status()`: its result carries every unread note.
- render() makes the file: only when the user asks for it.
- Free (the result's header says so): look, listen and advise; never write the project's files by hand.

## In the Claude app's chat

- A picture from see() stays inside the tool call, folded away: when the user asks to see something, share that picture in your reply (as a file in the conversation), don't only describe it.
- A video or picture the user drags into the chat lands in your own workspace, not on their computer, so LoupeEdit can't use it: ask where the file is on their computer (or to add it in LoupeEdit's Media), and import it by that path.
- The user's notes reach you with your next loupe call; nothing wakes you by itself here.
