---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "from": "Draft"
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

# Only admins and owners edit draft bills

A draft's number, title, year, state, sponsor, summary and text are edited by admins and owners only.
