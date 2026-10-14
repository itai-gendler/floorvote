---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "facts": [
        "Custom field values"
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
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/bulkRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/customFieldsApi.ts"
    }
  ]
}
---

# Only admins and owners fill in a bill's custom fields

Standard members see custom field values and filter on them, but cannot set them.
