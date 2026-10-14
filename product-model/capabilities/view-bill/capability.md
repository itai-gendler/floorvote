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
      "target": "api/src/routes/billsApi/detail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/lookupRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/textRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillDetail.tsx"
    }
  ]
}
---

# View bill

A member opens a bill's page to read its legislative data and text, the AI summary, tags and relevance, the team's tally and official position, comments, and their own vote and note. Admins also see how each member voted.
