---
description: Capture a thought into the GTD inbox instantly
argument-hint: <thought>
---

Capture the following into `inbox.md`:

$ARGUMENTS

Rules:
- If nothing was given, ask "What do you want to capture?" and capture the reply.
- Append one line per distinct item at the end of `inbox.md`, in the format `- <text> (captured YYYY-MM-DD)` using today's date. If the input clearly contains several separate items (separate lines, or a list), capture each as its own line. Keep the user's wording; do not rewrite.
- Do not clarify, organize, categorize, or ask follow-up questions. Capture must be instant.
- Reply with one line: how many items were captured and how many are now in the inbox.
