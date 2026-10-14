---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
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

# Only admins and owners invite people

Accounts come into being only through an invitation by an admin or owner, as a Standard member or an Admin.
