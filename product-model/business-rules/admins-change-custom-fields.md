---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-field",
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
      "target": "api/src/routes/customFieldsApi.ts"
    }
  ]
}
---

# Only admins and owners edit or reorder custom fields

Changes apply to every bill.
