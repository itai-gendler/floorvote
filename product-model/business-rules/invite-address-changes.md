---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "facts": [
        "Email"
      ]
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

# Admins change a pending invite's address, and only owners an owner's

Only a pending invite's address can change, never a signed-in member's and never the admin's own.
