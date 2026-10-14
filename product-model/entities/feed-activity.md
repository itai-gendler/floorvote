---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/feed.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/feedUtils.ts"
    }
  ]
}
---

# Feed activity

One entry in the team's feed: something that happened on a tracked bill or in the team, who did it and when.

## Information kept

- **Kind** — Bill added, Bill matched, Bill updated, Priority set, Position set, Comment added, Hearing added, Hearing changed or Hearing cancelled
- **Actor** — the member who acted, or the instance itself
- **Details** — what changed: the priority or position set, a comment preview, the changed bill facts, or the hearing's date and place
- **Bills** — the bill the entry is about, or the bills a bulk edit changed
- **When** — when it happened
