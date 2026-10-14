---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-bill-priority"
    },
    {
      "type": "capability",
      "id": "change-official-position"
    },
    {
      "type": "capability",
      "id": "edit-custom-field-values"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/bulkRoutes.ts"
    }
  ]
}
---

# A bulk edit changes at most 1,000 bills

A bulk edit by selection or by the current filter is refused when it would change more than 1,000 bills.
