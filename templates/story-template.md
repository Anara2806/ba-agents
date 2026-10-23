# Jira Story Template

Adjust fields to match your team's Jira configuration.

## Hierarchy

Epic → Story → Sub-task (only if the team uses them)

## Epic

- **Summary:** short outcome-oriented title
- **Description:** business goal, scope in/out, stakeholders, success measures
- **Labels:** theme, source-system
- **Sources:** list of source documents

## Story

- **Summary:** verb-first, under 80 characters (e.g. "Export monthly invoice report as PDF")
- **Description:**

```
As a <role>
I want <capability>
So that <business value>

Context: <1-3 sentences of background>
Business rules:
- BR-xx: <rule>
Out of scope: <items>
```

- **Acceptance criteria** (Given/When/Then, each testable):

```
AC1
Given <precondition>
When <action>
Then <observable result>
```

Include at least one negative or edge case and any relevant non-functional criteria (performance, security, accessibility).

- **Priority:** Highest / High / Medium / Low (MoSCoW rationale in a comment)
- **Estimate:** story points suggestion (marked "suggested, team to confirm")
- **Labels:** theme, release
- **Dependencies:** linked story keys or IDs
- **Source references:** `REQ-xxx` IDs with file and section/timestamp
- **Assumptions / Open questions:** anything unresolved
- **Attachments:** link to prototype page (after deployment)

## Sub-task (optional)

Summary and 1-2 line description only: analysis, UI, API, test, documentation.

## JSON shape (used between agents)

```json
{
  "epics": [
    {
      "id": "EP-01",
      "summary": "",
      "description": "",
      "labels": [],
      "sources": [],
      "stories": [
        {
          "id": "ST-01",
          "summary": "",
          "description": "",
          "acceptance_criteria": [{"id": "AC1", "given": "", "when": "", "then": ""}],
          "priority": "Medium",
          "estimate_suggestion": null,
          "labels": [],
          "dependencies": [],
          "requirement_ids": ["REQ-001"],
          "assumptions": [],
          "open_questions": [],
          "status": "draft"
        }
      ]
    }
  ]
}
```
