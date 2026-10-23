# BA Agents

Turns source documents into reviewed Jira-ready epics and stories (and an optional clickable prototype) using Claude Code, with human approval at every gate.

## One-time setup

1. **Rename `dot-claude/` to `.claude/`** (Claude Code only reads the dot-name). In Terminal: `mv dot-claude .claude`.
2. Create empty `inputs/` and `outputs/` folders (`mkdir -p inputs outputs`).
3. Install Claude Code and open a terminal in this folder, then run `claude`.
4. For Jira publishing only: add a Jira MCP server (`claude mcp add ...`, see docs.claude.com for current syntax) and set these environment variables in your shell (never in files):
   `JIRA_BASE_URL`, `JIRA_EMAIL`, `JIRA_API_TOKEN`.
   Then check that the server name matches `mcp__atlassian` in `.claude/agents/jira-publisher.md` and `.claude/settings.json`; change both if yours differs.
5. Set the real Jira project key in `CLAUDE.md` (Defaults).

## Daily use

1. Put source files in `inputs/`.
2. `/analyze <epic-name>`: runs intake, extraction, analysis, stories, review. Stops at Gate 1 (your answers) and Gate 2 (your story approval).
3. `/publish-stories <PROJECT-KEY>`: dry run, then Jira creation after your approval.
4. `/build-prototype`: builds the prototype; deployment to GitHub Pages only with your approval.

## Confidentiality

Check your company policy before putting real client documents into any AI tool. Mask personal data in samples. `inputs/` and `outputs/` are git-ignored by default.

## Layout

See `CLAUDE.md` (orchestrator), `.claude/agents/` (7 specialists), `.claude/commands/` (3 commands), `templates/`, `docs/conventions.md`.
