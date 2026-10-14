---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-field",
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
      "target": "api/src/routes/customFieldsApi.ts"
    }
  ]
}
---

# Only admins and owners delete custom fields

Deleting a custom field deletes every bill's value for it.
