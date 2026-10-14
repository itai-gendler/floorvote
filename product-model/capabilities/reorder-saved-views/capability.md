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

# Reorder saved views

An admin drags saved views into the order the team should see them in.
