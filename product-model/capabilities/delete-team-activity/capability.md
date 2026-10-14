---
{
  "availability": [
    {
      "place": "instance-web::settings"
    }
  ],
  "domain": "config",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Config.tsx"
    }
  ]
}
---

# Delete team activity

An owner permanently deletes the team's votes, comments, reactions, personal notes, official positions, bill priorities and feed history, keeping members, bills and AI summaries.
