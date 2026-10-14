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
      "target": "api/src/routes/savedViewsApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillList/ViewSwitcher.tsx"
    }
  ]
}
---

# Edit saved view

An admin renames a saved view or replaces its filters.
