---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "saved-view",
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
      "target": "api/src/routes/savedViewsApi.ts"
    }
  ]
}
---

# Only admins and owners delete saved views

Deleting a saved view removes it for everyone.
