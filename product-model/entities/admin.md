---
{
  "kind": "person",
  "acts": "external",
  "relations": [
    {
      "entity": "member-account",
      "verb": "holds",
      "cardinality": "one-to-one"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/middleware/auth.ts"
    }
  ]
}
---

# Admin

The permission level that manages the instance: members, roles, settings and notifications, and the team's priorities, official positions, draft bills and calendar events.
