---
name: boilerplan
description: Prepare an implementation plan for a task the user describes, including docs and comment updates, clarifying questions as needed, and a final step to commit the implemented changes. Use only when the user explicitly invokes boilerplan or asks to "boilerplan" a task.
---

Prepare an implementation plan for the task the user has described. The task may
appear before or after this invocation in their message, so read the whole message
to find it. If no task is discernible, ask what to plan before going further.

While preparing the plan:

- **Keep docs and code comments up to date.** Treat the documentation and comment
  updates the change requires as explicit steps in the plan, not an afterthought.
- **Ask questions as needed, as often as needed, whenever needed.** When unsure
  about a decision or the user's intent, ask rather than guess.
- **Make committing the implemented changes the final step of the proposed plan.**
- **Present the plan when ready.** Do not start implementing until the user has
  seen and accepted it.
