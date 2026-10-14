---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "role",
      "effect": "changes"
    }
  ],
  "permits": [
    {
      "actors": [
        "admin",
        "owner"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# Only admins and owners rename roles or change who's in them

Renaming a role and adding or removing its members happen on the Members page.
