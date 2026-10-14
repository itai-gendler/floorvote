---
{
  "entities": [
    {
      "entity": "feed-activity",
      "shows": [
        "Kind",
        "Actor",
        "Details",
        "Bills",
        "When"
      ]
    },
    {
      "entity": "bill",
      "shows": [
        "Bill number",
        "Title",
        "Priority",
        "Summary"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Feed.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/feed.ts"
    }
  ]
}
---

# Feed

The team's activity on its bills, newest first, grouped by bill and day: bills added and matched, status changes, hearings, priorities, positions and comments.
