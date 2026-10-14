---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "role",
      "effect": "removes"
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

# Only admins and owners delete roles

Deleting a role takes every member out of it.
