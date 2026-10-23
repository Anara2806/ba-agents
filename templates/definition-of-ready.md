# Definition of Ready and Story Quality Checklist

A story passes only if every "must" is satisfied. Edit to match your team's DoR.

## INVEST

- **Independent:** can be delivered without another unfinished story, or dependencies are explicit.
- **Negotiable:** describes the need, not the implementation.
- **Valuable:** the "so that" states real business or user value.
- **Estimable:** clear enough for the team to size.
- **Small:** fits in one sprint.
- **Testable:** every acceptance criterion can be verified.

## Must

1. Follows the story template (role, capability, value).
2. Summary is verb-first and under 80 characters.
3. At least 2 acceptance criteria in Given/When/Then, including one negative or edge case.
4. No vague words without a measure ("fast", "user-friendly", "easy", "etc.", "as appropriate").
5. Business rules are stated explicitly and numbered.
6. Source references present (requirement IDs, file, section/timestamp).
7. Assumptions and open questions listed, none hidden in the description.
8. Dependencies identified.
9. Out-of-scope stated where scope could be misread.
10. No duplicate of another story in the batch or an existing Jira issue.

## Should

- Non-functional requirements captured (performance, security, audit, accessibility, localisation).
- UI stories link to a prototype or wireframe.
- Data and integration needs noted (fields, systems, volumes).
- Priority rationale given.

## Review output format

For each story:

```
ST-xx  PASS | FAIL
Failed checks: <numbers>
Fixes: <specific, minimal edits>
```

End with a summary: counts of pass/fail and the top 3 recurring problems.
