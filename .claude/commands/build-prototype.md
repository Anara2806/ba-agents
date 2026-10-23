---
description: Build a clickable static prototype from approved stories, then (with approval) deploy to GitHub Pages
argument-hint: [epic-id or screen focus]
---

Build a prototype from the approved stories. Focus: $ARGUMENTS (if empty, cover all UI-relevant stories).

1. Confirm `outputs/04-stories/approved.json` exists. If not, stop and tell me to finish GATE 2 first.
2. Run `prototype-builder`. It writes a static site (HTML/CSS/JS, mock data only) to `outputs/05-prototype/`.
3. **GATE 4**: tell me how to preview it locally (open `outputs/05-prototype/index.html` in a browser, or run a simple local server from that folder) and list which stories each screen covers. Stop and wait for my feedback. If I request changes, re-run `prototype-builder` with my feedback.
4. Only after I explicitly approve deployment: add a GitHub Pages workflow file at `.github/workflows/pages.yml` that publishes `outputs/05-prototype/`, show me the file, then ask once more before committing and pushing.
5. After a successful deployment, offer to add the prototype link to the Jira epic. Do this only with my approval.

Rules: no git push or deployment without approval; the prototype must contain no real data or credentials.
