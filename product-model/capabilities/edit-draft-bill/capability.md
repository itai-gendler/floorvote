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
    }
  ]
}
---

# Edit draft bill

An admin changes a draft's number, title, year, state, sponsor, summary or text on its page. Filed bills' data comes from the legislature and cannot be edited.
