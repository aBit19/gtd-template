---
description: Mark an action complete, log it, and keep its project moving
argument-hint: <action text or keywords>
---

Mark this as done: $ARGUMENTS

Steps:
1. If nothing was given, ask what was completed.
2. Search open items in `next-actions.md`, `waiting-for.md`, and `calendar.md` for the best match (keywords are enough). If there are several plausible matches, list them numbered and ask which one. If there is no match, ask whether to log it as an unplanned completion.
3. Remove the matched line from its file and append it to `completed.md` under a `## YYYY-MM-DD` heading for today (create the heading at the top of the log if missing; newest date first). Keep its `@context` and `+project` tags, and drop the checkbox and date metadata.
   - Exception, `Buy items on the shopping list`: first ask which items were bought ("all" is fine) and remove them from `lists/shopping.md`. If items remain on the list, keep the action open instead of moving it to `completed.md`.
4. If the item had a `+slug` tag:
   - Add `- YYYY-MM-DD Done: <action>` to the `## Log` section of `projects/<slug>.md`.
   - Check whether the project still has any other open item tagged `+slug` in `next-actions.md`, `waiting-for.md`, or `calendar.md`.
   - If not, ask: "What's the next action for <project>, or is the project complete?"
     - New action: add it to `next-actions.md` in the proper format.
     - Complete: set `Status: completed`, add a log entry, move the file to `projects/archive/`, and add `- Project completed: <name> +slug` to today's section in `completed.md`.
5. Reply in one or two lines.
