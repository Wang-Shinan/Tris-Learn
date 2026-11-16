# Tris-Learn (T-Learn)

Tris-Learn, or **T-Learn**, is the project name. Install it as `t-learn` and invoke it with `$t-learn`.

An AI learning skill grounded in primary material, sustained questions, examination of the learner's explanations, and comparison of designs, with raw-log handoff and a companion session-review workflow.

When studying a complex structure, spontaneous questions may connect new knowledge to an existing explanatory framework. This skill follows those questions, tests the learner's ideas, and helps return to the main thread.

## Studying together

- Start at the learner's current page, figure, or question, adjusting the pace to their understanding.
- Present primary material faithfully before explaining it. Translate by default when the material's language differs from the user's current language; otherwise present it directly. Distinguish source content, explanation, and correction without silently repairing the source.
- Examine analogies and assumptions, identifying what holds and what needs revision. Reuse the learner's own analogies when they remain useful.
- When the learner proposes a design, run an example through it and compare the existing design's constraints and tradeoffs.
- When an explanation fails, locate confusion about objects, units, timing, or roles again.
- Remember the starting point and unresolved questions during explorations, reducing the burden of thinking while tracking the route.
- Respond naturally rather than quiz after every turn or infer mastery from “I understand” alone.
- At the end, provide a verified raw-log path or export and wait for the user to arrange review. If the original record is unavailable, say so rather than substitute a summary.

The instructions are in English to reduce instruction-token overhead. Conversation and translation follow the user's current language or explicit preference, not the language of the skill file.

## Reviewing together

Hand off the log when learning ends; the user decides when to begin review. Review is a companion phase of the same skill, usable in the original or another chat. Providing a log does not automatically start it.

Read the record, offer a few grounded observations and one useful question, then revisit excerpts and revise interpretations with the learner's responses. Examine changes in understanding, effective interactions, and unresolved questions without delivering a verdict for the learner to approve. Discuss changes when useful; a review need not produce new rules.

## Files

- [SKILL.md](SKILL.md): study principles, phase routing, and extension guidance.
- [references/session-review.md](references/session-review.md): the companion workflow, loaded when a learning-session review is requested.
- [notes/learning-cases.md](notes/learning-cases.md): five original learning cases for maintainers to revisit the skill's development; not default execution context.
- [agents/openai.yaml](agents/openai.yaml): display metadata and the default invocation prompt.

`notes/` holds maintenance material and is not linked for reading from `SKILL.md`. The repository root remains the skill directory: placing cases in `notes/` separates their purpose, not their physical location outside the skill. The original Chinese case notes are preserved. The skill applies to textbooks, slides, papers, and technical concepts beyond the computer-architecture examples in those notes.

## Using it in Codex

Place the repository contents in `~/.codex/skills/t-learn/`, with `SKILL.md` directly inside that directory. With a custom `CODEX_HOME`, use its `skills/t-learn/` directory. If the directory already exists, compare its contents before updating.

In a session that can discover the skill, for example:

> Use $t-learn to study these slides with me, starting at my current page. I'll describe my understanding; help me check it.

Or begin with an idea:

> Use $t-learn to examine this design with me. Let's run my version first, then compare why the course material does it differently.

After learning:

> Use $t-learn to review this learning session with me. Here is the raw-log path. Start with a few key observations, and let's discuss them together.

## Extending the skill

Start with actual learning excerpts: the earlier understanding, an ineffective explanation, the example that changed the discussion, evidence of change, and scope.

Prefer revising existing guidance. Principles supported across cases belong in `SKILL.md`; their history, personal cases, and requested unvalidated observations belong in `notes/` without automatically becoming execution rules. Add a minimal contrasting example only when actual misuse shows a need for calibration.

Keep log handoff separate from skill revision. Raw records stay locally or in supported export locations; they are not automatically committed here or sent to another chat. The user arranges review and then decides whether to revise the skill.
