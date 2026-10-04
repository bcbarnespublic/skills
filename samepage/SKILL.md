---
name: samepage
description: Use only when the user explicitly invokes samepage; mentioning, reviewing, or editing the skill does not invoke it. Align the agent with the user about the current project or in-progress work through three rounds of multiple-choice questions targeting consequential uncertainty, answered with compact letter codes.
---

# samepage

Get on the same page as the user about the current project or the work in progress in this session. Ask three rounds of multiple-choice questions about what you understand least and what would most change your actions if you have it wrong. The user should be able to answer each round in a few keystrokes.

Do not modify files or resume other work while running this skill.

## Orient first

Learn what you can without the user. Finding facts is your job; spend the user's attention on intent, priorities, judgment, and facts recorded nowhere you can reach.

- If this session has work in progress, the subject is that work and the conversation is your primary source. Otherwise the subject is the project as a whole.
- Skim cheaply: project instructions and README, version-control status and recent history, recently changed files, and any plan or notes the conversation points to. This is orientation, not an audit; stop once further reading would not change which questions you ask.
- If the user included text with the invocation, treat it as the focus.

## Choose questions

List the beliefs your next actions depend on: goals and intent, scope and non-goals, what done looks like, current status, priorities, constraints, preferred tradeoffs, and the meaning of key terms. Ask about those where you are least certain and where a wrong belief would most change what you do. Skip anything you could verify yourself, anything whose answers would all lead to the same action, and anything the user has already settled.

Each question asks one thing. Offer two to four substantive options, labeled consecutively from A. They are concrete, plausible, mutually exclusive, and lead to different actions. Vary which letter holds your best guess. Always include E for misunderstood / not applicable.

Ask up to five questions per round; a few sharp questions beat padding. Always run all three rounds, with at least one question each. Later rounds may build on earlier answers, but each round should ask whatever questions are most pressing at that point. When initial uncertainties are resolved, use later rounds to explore consequential tradeoffs, implications, and previously unexamined assumptions rather than repeating settled questions. Treat an E answer as evidence that your framing is wrong; rethink that area before asking about it again.

## Present each round

Before round 1, briefly state your current read of the project or work, short enough that the user can spot errors at a glance.

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
