---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-field",
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
      "target": "api/src/routes/customFieldsApi.ts"
    }
  ]
}
---

# Only admins and owners create custom fields

Custom fields are the instance's own, defined in Config.
