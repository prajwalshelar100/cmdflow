# CMDflow (Command Session Maintainer)

A small idea for a developer tool that helps collect, organize, and export
shell commands while reading documentation, blogs, or repositories.

---

## Status: Proposal / Paused

This repository does **not** contain an implementation yet.

It exists to document an idea, the thinking behind it, and a possible
architecture. I’m intentionally not building it yet—I want to understand
whether this is a real pain point for others, not just for me.

If this problem resonates with you, starring the repo or opening an issue
to describe your workflow would be genuinely helpful.


---
_This is an open-source project proposal intended for community discussion and validation._

## The Problem

When reading documentation or blog posts, I often need to:

- Copy **multiple commands**, not just one
- Keep them in the **right order**
- Make small edits or add notes before running them
- Export them as something I can reuse later

What exists today doesn’t fit this moment very well:

- Clipboard managers are too generic and noisy
- Note-taking tools are too heavy during execution
- Terminal history exists only *after* commands are run
- Browser copy–paste has no memory or structure

There’s a gap during the *execution phase*—between reading and doing.

---

## The Idea

**CMDflow** is a temporary, session-based tool meant to live in that gap.

The core idea is simple:

1. Capture only executable commands from a page
2. Keep a live, ordered list while working on a task
3. Allow small edits, comments, and reordering
4. Export the result as `.sh`, `.md`, or `.txt`
5. Discard the session when the task is done

This is meant to be **disposable by default**, not a knowledge base or a
long-term storage system.

---

## What This Tool Is Not

This project is intentionally narrow.

- ❌ Not a note-taking app
- ❌ Not a learning platform
- ❌ Not a clipboard manager replacement
- ❌ Not cloud-first or account-based

Keeping the scope small is a design goal, not a limitation.

---

## Proposed Features (MVP)

- Detect code blocks on web pages
- “Add to Session” button for commands
- Editable list of collected commands
- Enable / disable commands
- Automatic context (page title + source URL)
- Export options:
  - `.sh` — runnable shell script
  - `.md` — documentation-style output
  - `.txt` — plain text

---

## Architecture (Proposed)

Target platform: **Cross-browser WebExtension**

Supported browsers:
- Chrome
- Firefox
- Edge
- Brave

### High-level components

- **Content script**
  - Injects capture buttons
  - Extracts command text only

- **Background service**
  - Maintains session state
  - Handles export logic

- **Popup UI**
  - Displays and edits the session
  - Designed to be keyboard-friendly

- **Storage**
  - Local browser storage
  - No cloud sync by default

---

## Design Principles

- Commands are first-class
- Sessions are temporary by default
- Low friction over completeness
- Keyboard-friendly interactions
- Avoid feature creep

---

## Why This Repository Exists

This repository exists to:

- Validate whether this is a real, shared problem
- Collect feedback before writing code
- Avoid building something nobody needs
- Document architectural thinking clearly

If enough people find this useful, it can be built properly.

---

## How You Can Help

- ⭐ Star the repo if you’d use a tool like this
- 🗣 Open an issue describing your workflow or pain points
- 💡 Suggest ideas (please keep scope in mind)
- 🔍 Share similar tools if you know of them

---

## Author

Prajwal Shelar  

Website: https://www.prajwalshelar.online  
GitHub: https://github.com/prajwalshelar100  
LinkedIn: https://www.linkedin.com/in/prajwalshelar  
Email: shelar.prajwal.99@gmail.com

---

## License

MIT
