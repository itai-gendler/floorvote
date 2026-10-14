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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/owners.ts"
    }
  ]
}
---

# Owner

The permission level that can do everything an Admin can, and also manages owners, the account deletion policy and clearing the team's activity.
