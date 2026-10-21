# Skills

Agent skills for planning, reviewing, fixing, and verifying project work, using the portable `SKILL.md` format. Each skill lives in its own directory, ready to copy into a harness's skills location.

## Using skills together

Use the skills individually or combine them as the work calls for it. For example:

- **Review, plan, verify:** Use `/professor` to review a project, then `/boilerplan` to plan fixes for the findings you want to address. After accepting and implementing the plan, use `/trust-but-verify` to check that everything landed.
- **Check work as you go:** Use `/deslop` after a chunk of work or when taking over someone else's—or another agent's—codebase to find stale assumptions, unnecessary complexity, and weak verification.
- **Fix until stable:** Use `/bughunter` when you want material bugs found and fixed rather than reviewed. It repeats passes until one finds nothing worth fixing.
- **Plan with review standards in mind:** Start with an idea and tell `/boilerplan`: “This work will eventually be evaluated by `/professor` or `/deslop`. Read those skills and account for their review standards in the plan.”

These are examples, not a required sequence. The slash notation names the skills; invocation syntax depends on your harness.

## Compatibility

This repository owns the skill definitions only. Harness-specific installation instructions and compatibility checks are owned by an external skill-installer project and are intentionally not duplicated here. The skills work from local evidence and reach outside resources, such as the web or third-party services, only for targeted checks in sessions that already do so.

## [boilerplan](boilerplan/SKILL.md)

`boilerplan` turns a described task into an implementation plan: keep docs and code comments current, ask clarifying questions as needed, check the plan for wrong, risky, or oversized steps, and make a git commit the final implementation step. The agent presents the plan and waits for acceptance before implementing it.

Used in place of restating the same planning boilerplate at the end of every request.

## [bughunter](bughunter/SKILL.md)

`bughunter` finds and fixes material bugs: wrong results, lost data, broken workflows, and crashes in the project's supported use. It reads all the code on each pass, fixes only confirmed bugs without adding tests or hardening, and repeats until a pass finds nothing worth fixing. A gitignored `.bughunter.md` file logs the run's progress, fixes, and open decisions.

Used when repeated reviews keep turning up different issues and you want to reach a stable end state instead.

## [deslop](deslop/SKILL.md)

`deslop` reviews code and project material for stale assumptions, unnecessary complexity, duplicate concepts, and weak verification. That includes dead or speculative (YAGNI) code, duplicate helpers, abandoned or unmaintained dependencies, and code or dependencies that redo what the standard library or platform already provides. It prioritizes recommendations backed by evidence and is read-only unless you request remediation.

Used after chunks of work or when taking over an unfamiliar codebase, regardless of who or what wrote it.

## [docpass](docpass/SKILL.md)

`docpass` audits project documentation against the implementation, treating code as the ground truth. It checks Markdown files, comments, docstrings, and configuration metadata for stale, contradictory, redundant, missing, dead, or verbose information. Findings include file and line references; targeted fixes can be requested.

Used occasionally to deal with documentation drift.

## [professor](professor/SKILL.md)

`professor` evaluates a project in the style of a grumpy, skeptical Ph.D. professor. Its structured review prioritizes correctness, then elegance, simplicity, and speed, while also examining security, usability, tests, and documentation. It concludes with a letter grade and actionable recommendations prioritized by severity.

Used after major milestones for insightful, in-depth, and sometimes entertaining project reviews.

## [samepage](samepage/SKILL.md)

`samepage` gets the agent on the same page as you about the current project or work in progress. After orienting itself, it asks three rounds of multiple-choice questions about what it understands least and what would most mislead it, which you answer with a compact reply such as `1A 2B 3A`. It checks its understanding before turning to direction, then summarizes what was confirmed and what remains open.

Used at the start of a session, after a long or compacted session, or whenever the agent seems to be working from the wrong picture.

## [trust-but-verify](trust-but-verify/SKILL.md)

`trust-but-verify` checks whether an implemented plan matches what was promised. It compares the plan against actual artifacts, version history, and action records to classify items as done, partial, missing, or unverified. It also highlights changes outside the plan. The audit is read-only and relies on evidence rather than the implementing agent's self-report.

Used when you really need to know the agent did what you asked it to do.

## License

Released under the MIT License. See [LICENSE](LICENSE) for the full text.
