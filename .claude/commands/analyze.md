---
description: Run the full analysis pipeline (intake, extract, analyze, write, review) up to the story review gate
argument-hint: [epic-name]
---

Run the analysis pipeline for: $ARGUMENTS

Follow the workflow and gate rules in CLAUDE.md exactly.

1. Check `inputs/` has files. If empty, stop and tell me. Create the `outputs/` subfolders if missing.
2. **Intake**: run `intake-normalizer` for each file in `inputs/` (in parallel).
3. **Extract**: run `requirements-extractor`.
4. **Analyze**: run `conflict-gap-analyzer`.
5. **GATE 1**: show me the conflicts and open questions from `outputs/03-analysis/`. Wait for my answers or my explicit acceptance of the assumptions. Save them to `outputs/03-analysis/decisions.md`.
6. **Write**: run `story-writer`, using "$ARGUMENTS" as the epic theme if given.
7. **Review**: run `story-reviewer`. If any story fails, have `story-writer` revise once and re-review once.
8. **GATE 2**: summarise pass/fail counts and point me to `outputs/04-stories/stories.md`. Stop. Create `approved.json` only after I say the stories are approved.

Rules: pass data only through files in `outputs/`; no Jira writes, git pushes or deployments; report any agent problem to me instead of continuing.
