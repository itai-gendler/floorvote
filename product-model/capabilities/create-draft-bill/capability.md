---
{
  "availability": [
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
      "target": "api/src/lib/draftNumber.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/DraftBills.tsx"
    }
  ]
}
---

# Create draft bill

An admin starts tracking a bill before it is filed. A draft may be untitled and gets the next DRAFT number when none is given; its year defaults to the current session, or the next one once the current session has ended. Creating it opens the new draft's page.
