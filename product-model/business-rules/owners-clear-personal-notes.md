---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "personal-note",
      "effect": "removes"
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

# Only owners remove members' personal notes

Personal notes are removed in bulk only when an owner clears the team's activity, or with the account that wrote them.
