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
      "target": "api/src/routes/billsApi/bulkRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/CompactPositionSelect.tsx"
    }
  ]
}
---

# Change official position

An admin sets the team's official position on a bill — Support, Oppose, Amend, Monitor or No Position — or clears it. It is the position the team might point to publicly or share with a coalition.
