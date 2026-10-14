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
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/bulkRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/NewMatchTriageControl.tsx"
    }
  ]
}
---

# Dismiss new match

An admin resolves a new keyword match as reviewed with no priority. The bill stays tracked and keeps receiving updates; it only leaves the New matches worklist.
