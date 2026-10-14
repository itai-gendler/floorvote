---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "instance-settings",
      "effect": "changes",
      "facts": [
        "Account deletion"
      ]
    }
  ],
  "permits": [
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

# Only owners turn account deletion on or off

Admins see the account deletion setting but cannot change it.
