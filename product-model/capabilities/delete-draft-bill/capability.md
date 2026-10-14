---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    },
    {
      "place": "instance-web::settings"
    }
  ],
  "domain": "draft-bills",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/DraftBills.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillDetail.tsx"
    }
  ]
}
---

# Delete draft bill

An admin deletes a draft nobody engaged with. A draft with votes, a position, comments or notes must be linked to its filed bill instead.
