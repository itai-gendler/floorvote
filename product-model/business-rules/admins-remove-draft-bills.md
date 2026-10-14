---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "removes"
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

# Only admins and owners delete or link draft bills

A draft leaves the instance only when an admin or owner deletes it or links it to its filed bill. Filed bills are never deleted.
