---
description: List, add, rename, or remove GTD contexts
argument-hint: [list | add @name description | rename @old @new | remove @name]
---

Manage contexts. Arguments: $ARGUMENTS (default: `list`).

`contexts.md` is the registry. `next-actions.md` has one `## @name` section per registered context, in the same order.

**list**
Show each context with its description and the number of open actions under it. Point out contexts with zero actions for more than a few weeks as candidates to remove or merge, and any `@tags` used in files that are not registered.

**add @name [description]**
1. Normalize the name to lowercase kebab-case with a leading `@`.
2. If a similar context already exists, point it out and ask whether to use that instead.
3. If no description was given, propose one.
4. Append `- @name — description` to `contexts.md` and add an empty `## @name` section to `next-actions.md`.

**rename @old @new**
1. Update the entry in `contexts.md` and the section heading in `next-actions.md`.
2. Replace the `@old` tag with `@new` on every line in `next-actions.md` and `completed.md`.
3. Report how many lines changed.

**remove @name**
1. If the context has open actions, list them and ask which context each should move to (or offer to move all to one context). Do not remove until they are moved.
2. Ask for confirmation, then remove the entry from `contexts.md` and its section from `next-actions.md`. Leave historical tags in `completed.md` untouched.
