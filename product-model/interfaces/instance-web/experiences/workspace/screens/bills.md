---
{
  "entities": [
    {
      "entity": "bill",
      "shows": [
        "Bill number",
        "Title",
        "State",
        "Session",
        "Status",
        "Stage",
        "Summary",
        "Tags",
        "Relevance score",
        "Priority",
        "Official position",
        "Custom field values",
        "Vote tally",
        "New match"
      ]
    },
    {
      "entity": "saved-view",
      "shows": [
        "Name",
        "Filters"
      ],
      "collects": [
        "Name"
      ]
    },
    {
      "entity": "member-vote",
      "shows": [
        "Position"
      ]
    },
    {
      "entity": "custom-field",
      "shows": [
        "Name",
        "Type",
        "Options"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/bills"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillList/index.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/listRoutes.ts"
    }
  ]
}
---

# Bills

Every bill in the instance's covered states, tracked bills first, with search, filters, saved views, the New matches worklist and bulk editing.
