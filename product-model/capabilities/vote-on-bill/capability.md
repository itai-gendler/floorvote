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
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/Sidebar.tsx"
    }
  ]
}
---

# Vote on bill

A member records how they feel about a bill: support, oppose or neutral. Voting again changes their vote. Members whose voting an admin restricted cannot vote.
