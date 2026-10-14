---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "facts": [
        "Priority"
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
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/bulkRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/middleware/auth.ts"
    }
  ]
}
---

# Only admins and owners change a bill's priority

Setting or clearing a priority, on one bill or in bulk, is refused to standard members. Clearing every priority is part of an owner clearing the team's activity.
