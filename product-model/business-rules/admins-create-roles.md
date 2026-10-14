---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "role",
      "effect": "creates"
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

# Only admins and owners create roles

Every member can see roles and mention them; only admins and owners define them.
