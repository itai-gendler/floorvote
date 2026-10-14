---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "saved-view",
      "effect": "changes"
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
      "target": "api/src/routes/savedViewsApi.ts"
    }
  ]
}
---

# Only admins and owners rename, update or reorder saved views

Changes to a saved view apply for everyone.
