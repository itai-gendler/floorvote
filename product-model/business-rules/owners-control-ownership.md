---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "facts": [
        "Permission level"
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

# Only owners change an owner's permission level or make someone an owner

Admins change standard members and admins between those two levels. Making someone an Owner, or changing an Owner's level, is refused to anyone but an owner.
