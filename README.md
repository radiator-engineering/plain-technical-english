# Plain Technical English

An agent skill for clear prose. It applies George Orwell's six rules and
ASD-STE100 Simplified Technical English when an agent drafts or revises
text. It keeps the writer's meaning, tone and constraints, and it keeps every
hedge, caveat and verification step that carries a fact.

The skill is in `skills/plain-technical-english/SKILL.md`.

## Install

Claude Code:

```
/plugin marketplace add radiator-engineering/plain-technical-english
/plugin install plain-technical-english@plain-technical-english
```

Any agent that the skills CLI supports:

```
npx skills add radiator-engineering/plain-technical-english
```

Or copy `skills/plain-technical-english` into `~/.claude/skills/`.

## Evals

`skills/plain-technical-english/evals/` holds six cases: a jargon memo, a
passive runbook, a literary passage whose voice must survive, a README whose
code must not change, a Diátaxis how-to, and a breaking-change email. Each case
has a prompt, an input where one applies, and `checks.json` with banned
phrases, strings that must survive, a length ratio and a passive-voice limit.
`evals.json` lists the expectations a grader scores. The checks match strings;
the `judge_focus` field covers what string matching cannot.
