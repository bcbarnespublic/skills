---
name: samepage
description: Gets the agent on the same page as the user about the current project or in-progress session work through three rounds of multiple-choice questions targeting the agent's highest-uncertainty, highest-leverage assumptions. The user answers each round with compact letter codes. Use only when the user explicitly invokes samepage.
disable-model-invocation: true
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

Each question asks one thing. Options A–D are concrete, plausible, mutually exclusive, and lead to different actions. Vary which letter holds your best guess so position carries no signal.

Ask up to five questions per round; a few sharp questions beat padding. Always run all three rounds, with at least one question each. Later rounds may build on earlier answers, but each round should ask whatever questions are most pressing at that point. Treat an E answer as evidence that your framing is wrong; rethink that area before asking about it again.

## Present each round

Before round 1, briefly state your current read of the project or work, short enough that the user can spot errors at a glance.

Present all of a round's questions together in a single message, as plain text rather than through a question or form tool, since such tools may cap the number of questions or options. Mark your best guess on each question. Then stop and wait for the user's answers to the whole round. Lay out each round like this:

```
Round 1 of 3. Reply like "1A 2D 3C" or "ADC"; add a note after any answer, or use - to skip.
E means: This question or its answers fundamentally misunderstood the project or are not applicable.

1. [question]
   A. [option]
   B. [option] (my guess)
   C. [option]
   D. [option]
   E. Misunderstood / not applicable
```

## Read the replies

Accept any reasonable shape: `1A 2D`, `ADCAE`, lowercase, commas, or answers with notes such as `3E it's really a CLI`. A bare string of letters maps to the questions in order. A note outweighs the letter it follows. If a reply is ambiguous in a way that matters, ask a one-line clarification instead of guessing.

After rounds 1 and 2, briefly state what changed in your understanding, then present the next round.

## Finish

After round 3, summarize the shared understanding concisely: the goal, current state, key decisions and constraints, and what the answers corrected in your earlier read. Name any important uncertainty that remains. Then stop and wait for the user's next instruction.
