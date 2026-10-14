---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "saved-view",
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
      "target": "api/src/routes/savedViewsApi.ts"
    }
  ]
}
---

# Only admins and owners save bill views

Saved views are shared with the whole team, so only admins and owners create them; every member can use them.
