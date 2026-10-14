---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "creates",
      "to": "Draft"
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
    }
  ]
}
---

# Only admins and owners create draft bills

Draft bills are created by admins and owners only.
