---
{
  "id": "floorvote",
  "summary": "Legislative tracking for teams: keyword-matched bills with AI summaries, member voting and official positions, comments, a shared hearing calendar and email notifications, in a private instance per team.",
  "category": "legislative-tracking",
  "tags": [
    "legislation",
    "bill-tracking",
    "advocacy",
    "teams",
    "calendar"
  ],
  "authors": [
    {
      "name": "FloorVote project",
      "url": "https://github.com/floorvote/floorvote"
    }
  ],
  "license": "AGPL-3.0",
  "languages": [
    "en"
  ],
  "limitations": [
    "Each team's instance is a separate deployment with its own database, members, bills, feed and calendar; instances share nothing with each other.",
    "People join an instance only by an admin's invitation; asking for a sign-in link with an address the instance doesn't know sends nothing.",
    "Members sign in with a link emailed to them; there are no passwords.",
    "An instance gets its legislative data from the operator's central service and its providers, LegiScan by default, and never calls a legislative data provider itself.",
    "AI analysis runs only on the bills an instance tracks, never on every bill in its covered states."
  ],
  "references": [
    {
      "kind": "doc",
      "role": "intent",
      "target": "README.md",
      "title": "FloorVote README"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "docs/content/overview/what-can-it-do.md",
      "title": "What can FloorVote do?"
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "CONTEXT.md",
      "title": "FloorVote glossary"
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "docs/content/architecture/index.md",
      "title": "Architecture"
    }
  ]
}
---

# FloorVote

FloorVote is an open, self-hostable bill tracker for teams that follow legislation. Each team gets its own instance, which watches every bill in the states (and Congress) it covers, picks out the bills matching the team's keywords, and has AI summarize, tag and score them by the team's own instructions. Members vote support, oppose or neutral, discuss bills in comments with mentions and reactions, keep personal notes, and follow hearings on a shared calendar they can subscribe to; admins set priorities, the team's official positions and custom fields, triage new matches, and manage members, roles and settings. Email keeps members in the loop with sign-in links, mention and reply emails, a digest of activity on prioritized bills and a week-ahead preview of hearings.

## Intent

Instead of everyone on a team monitoring bills on their own and comparing notes over email or in meetings, FloorVote gives the whole team one shared place to watch, discuss, and respond to the bills that matter to them. It surfaces those bills automatically, filtered by the team's keywords and summarized and tagged by AI according to the team's instructions, and it is meant to run for about $5-7 a month in infrastructure, with each team's data in a private, isolated deployment.
