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
      "target": "api/src/lib/calendarBackfill.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/CompactPrioritySelect.tsx"
    }
  ]
}
---

# Change bill priority

An admin sets a bill's priority to high, medium or low, or clears it. A priority is what puts a bill in members' sidebars, its hearings on the calendar and in the week-ahead email, and its activity in the digest. Prioritizing an untracked bill starts tracking it.
