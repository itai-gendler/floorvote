---
{
  "availability": [
    {
      "place": "instance-web::workspace"
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
      "target": "web/src/pages/BillDetail.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/BillPicker.tsx"
    }
  ]
}
---

# Link draft bill

Once a draft is filed, an admin links it to its filed bill: the draft's votes, position, comments, notes, custom field values and calendar events move to the filed bill, and the draft is deleted. Where both carry the same engagement, the filed bill's wins.
