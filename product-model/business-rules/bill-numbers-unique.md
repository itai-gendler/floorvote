---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-draft-bill"
    },
    {
      "type": "capability",
      "id": "edit-draft-bill"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/draftNumber.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    }
  ]
}
---

# A bill number is unique within its state and year

Creating or renumbering a draft, or moving it to another state or year, is refused when another bill already has that number there.
