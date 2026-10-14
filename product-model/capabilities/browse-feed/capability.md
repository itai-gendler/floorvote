---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/feed.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Feed.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/feedUtils.ts"
    }
  ]
}
---

# Browse feed

A member reads the team's activity on bills, newest first. The default feed shows the team's own activity and everything on prioritized bills; a second scope shows all activity on analyzed bills. Reading the feed clears its unread dot.
