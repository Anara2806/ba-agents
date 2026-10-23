---
description: After story approval, dry-run then create the issues in Jira
argument-hint: [jira-project-key]
---

Publish the approved stories to Jira. Project key: $ARGUMENTS (if empty, ask me; do not guess).

1. Confirm `outputs/04-stories/approved.json` exists. If not, stop and tell me to finish GATE 2 first.
2. Confirm `JIRA_BASE_URL`, `JIRA_EMAIL` and `JIRA_API_TOKEN` are set, and that a Jira MCP server is available. Never print the values. If anything is missing, stop and explain how to set it.
3. Run `jira-publisher` in **dry-run mode**. It writes the planned issues to `outputs/04-stories/publish-log.md` without creating anything.
4. **GATE 3**: show me the plan (project, epics, story count, titles, duplicates found). Wait for my explicit approval.
5. After approval only, run `jira-publisher` in **create mode**. It creates epics first, then stories linked to their epic, and records the Jira keys in `publish-log.md`.
6. Add the Jira keys next to the IDs in `approved.json` (keep the original IDs). Report created/failed counts.

If any creation fails, stop, report which issues were created, and do not retry without asking.
