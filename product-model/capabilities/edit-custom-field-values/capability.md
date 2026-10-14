---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "domain": "bills",
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
      "target": "api/src/lib/customFieldValues.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/CustomFieldsSection.tsx"
    }
  ]
}
---

# Edit custom field values

An admin fills in the instance's custom fields on a bill, or on many bills at once from the Bills page.
