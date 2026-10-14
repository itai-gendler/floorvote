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
      "target": "web/src/pages/BillList/SaveViewButton.tsx"
    }
  ]
}
---

# Save bill view

An admin saves the Bills page's current filters as a named view that every member sees in the switcher.
