---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "from": "Deactivated"
    }
  ],
  "permits": [
    {
      "actors": [
        "admin"
      ],
      "when": [
        {
          "fact": "Permission level",
          "is-not": "Owner"
        }
      ]
    },
    {
      "actors": [
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

# Only admins and owners reactivate members, and only owners reactivate an owner

A deactivated member cannot reactivate themselves.
