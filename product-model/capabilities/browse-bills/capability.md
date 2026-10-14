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
      "target": "api/src/routes/billsApi/listRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/query.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillList/index.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillList/FilterPanel.tsx"
    }
  ]
}
---

# Browse bills

A member browses every bill in the instance's covered states on the Bills page, tracked bills first, and narrows the list with search, filters, saved views and personal scopes. Admins also get the New matches worklist.
