---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "facts": [
        "Voting"
      ]
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

# Only admins and owners restrict or allow a member's voting

Restricting voting does not sign the member out.
