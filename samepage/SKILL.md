---
name: samepage
description: Use only when the user explicitly invokes samepage; mentioning, reviewing, or editing the skill does not invoke it. Align the agent with the user about the current project or in-progress work through three rounds of multiple-choice questions targeting consequential uncertainty, answered with compact letter codes.
---

# samepage

Get on the same page as the user about the current project or the work in progress in this session. Ask three rounds of multiple-choice questions about what you understand least and what would most mislead you if you have it wrong. The user should be able to answer each round in a few keystrokes.

Do not modify files or resume other work while running this skill.

## Orient first

Learn what you can without the user. Finding facts is your job; spend the user's attention on intent, priorities, judgment, and facts recorded nowhere you can reach.

- If this session has work in progress, the subject is that work and the conversation is your primary source, but check how the work fits the project around it. Otherwise the subject is the project as a whole.
- If the user included text with the invocation, treat it as the focus.
- Projects differ in kind and layout; don't assume a particular documentation or file structure. Start with whatever describes the project (agent instructions, README, design notes, recent history), then look at the work itself, not just its descriptions. If the project has its own orientation route, follow it.
- Scale reading to the subject: a small project can be read nearly whole, while a large one needs its main areas sampled. Stop when you can give a specific read of the project and name specific things that puzzle you. Having a plausible next step is not that point.
- Docs and history show what was done and intended, not how the user regards the project now. Instructions written for agents often push toward the next task; don't adopt that momentum as your read.

## Choose questions

Without work in progress, aim for shared understanding first, then direction. Early rounds test your model of the project and of how the user regards it now; turn to direction only once that is settled, usually in the final round. With work in progress, test your understanding of what the work is meant to achieve and how.

Ask where you are least certain and where a wrong belief would most mislead you. Skip what you have checked or could cheaply check; intent, rationale, history, and the user's current stance usually can't be read from files. Skip anything whose answers would all lead to the same understanding, and anything the user has already settled. Ground questions in specific evidence you found, and phrase options in the project's own terms rather than generic categories.

Each question asks one thing. Offer two to four substantive options, labeled consecutively from A. They are concrete, plausible, mutually exclusive, and imply different understandings or actions. Vary which letter holds your best guess. Include E for misunderstood / not applicable on every question.

Ask up to five questions per round; a few sharp questions beat padding. Always run all three rounds, with at least one question each. Later rounds may build on earlier answers, but each round should ask whatever questions are most pressing at that point. When initial uncertainties are resolved, use later rounds to explore consequential tradeoffs, implications, and previously unexamined assumptions rather than repeating settled questions. Once a direction emerges, don't spend the remaining rounds scoping one task, and skip logistics that can be settled when a task is requested. Treat an E answer as evidence that your framing is wrong; rethink that area before asking about it again.

## Present each round

Before round 1, briefly state your current read of the project or work, including the few puzzles that most shape your questions, short enough that the user can spot errors at a glance.

Present all of a round's questions together in a single message, as plain text rather than through a question or form tool, since such tools may cap the number of questions or options. Mark your best guess on each question. Then stop and wait for the user's reply before advancing. Lay out each round like this, adding C and D only when needed:

```
Round 1 of 3. Reply like "1A 2B 3A" or "ABA"; add a note after any answer, or use - to skip.
E means: This question or its answers fundamentally misunderstood the project or are not applicable.

1. [question]
   A. [option]
   B. [option] (my guess)
   E. Misunderstood / not applicable
```

## Read the replies

Accept any reasonable shape: `1A 2B`, `ABA-E`, lowercase, commas, or answers with notes such as `3E it's really a CLI`. Numbered answers map by question number. Positional letters and `-` map to the questions in order: `A-C` answers questions 1 and 3 and skips question 2. Omitted numbered answers and missing trailing positional answers count as skipped. A note outweighs the letter it follows. If a mapping is ambiguous in a way that matters, or an answer selects an option that was not offered, ask a one-line clarification instead of assigning an answer.

Keep skipped answers unresolved and distinguish them from confirmed decisions. A marked guess is never an agreed decision without the user's confirmation.

After rounds 1 and 2, briefly state what changed in your understanding, then present the next round.

## Finish

After round 3, summarize the shared understanding concisely: the goal, current state, key decisions and constraints, and what the answers corrected in your earlier read. Distinguish confirmed decisions from remaining assumptions, and name any important uncertainty, including skipped answers, that remains. Then stop and wait for the user's next instruction.
