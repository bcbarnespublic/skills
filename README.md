# Skills

Four agent skills using the portable `SKILL.md` format for agent harnesses, including OpenAI Codex, Pi coding agent, Claude Code, Google Antigravity, tau, and OpenCode. Each skill lives in its own directory as a `SKILL.md` file, ready to copy into a harness's skills location.

## Compatibility

This repository owns the skill definitions only. Harness-specific installation instructions and compatibility checks are owned by an external skill-installer project and are intentionally not duplicated here.

## [boilerplan](boilerplan/SKILL.md)

`boilerplan` turns a described task into an implementation plan, carrying the standing instructions that would otherwise be retyped every time: keep docs and code comments current, ask clarifying questions freely rather than guessing, end the plan with a git commit, and present the plan before implementing anything.

Used in place of restating the same planning boilerplate at the end of every request.

## [docpass](docpass/SKILL.md)

`docpass` audits all project documentation against the underlying codebase implementation, treating the code as the ground truth. It inventories Markdown files, source code comments, docstrings, and configuration metadata to identify stale, contradictory, missing, or dead information. Findings are reported with specific file and line numbers, followed by an option to generate targeted documentation fixes.

Used occasionally to deal with documentation drift.

## [professor](professor/SKILL.md)

`professor` conducts a rigorous, persona-driven evaluation of the codebase in the style of a grumpy, skeptical Ph.D. professor. The review progresses through a structured 15-step checklist evaluating correctness, simplicity, security, and usability. It concludes by assigning a letter grade and providing a prioritized, actionable list of recommendations categorized by severity.

Used after major milestones for insightful, in-depth, and sometimes entertaining project reviews.

## [trust-but-verify](trust-but-verify/SKILL.md)

`trust-but-verify` provides an independent verification of whether a recently proposed plan was correctly executed. It compares the plan's checklist against the actual file changes, git logs, and command outputs to classify tasks as completed, partial, or missing. It also highlights any out-of-scope modifications without modifying any files.

Used when you really need to know the agent did what you asked it to do.

## License

Released under the MIT License. See [LICENSE](LICENSE) for the full text.
