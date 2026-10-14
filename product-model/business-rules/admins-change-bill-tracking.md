---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "from": "Untracked"
    },
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "from": "Matched"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    }
  ]
}
---

# Only admins and owners change which bills the instance tracks

An untracked bill starts being tracked when an admin or owner prioritizes it or saves keywords that match it, and a keyword match stops being tracked, or is kept as added by hand, only when an admin or owner saves new keywords. New bills arriving as keyword matches are tracked by the instance itself.
