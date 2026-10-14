---
{
  "relations": [
    {
      "entity": "reaction",
      "verb": "collects",
      "cardinality": "one-to-many"
    },
    {
      "entity": "notification",
      "verb": "causes",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/commentsApi.ts"
    }
  ]
}
---

# Comment

A member's message in a bill's discussion, which can @-mention members, roles, or everyone.

## Information kept

- **Content** — the formatted message, at most 10 KB
- **Mentions** — the members, roles or everyone the comment mentions
- **Posted at** — when the comment was posted
