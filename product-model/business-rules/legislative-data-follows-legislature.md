---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "facts": [
        "Status",
        "Stage",
        "Sponsors",
        "Last action",
        "History",
        "Subjects"
      ]
    }
  ],
  "permits": [
    {
      "unattended": true
    },
    {
      "actors": [
        "admin",
        "owner"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# A filed bill's legislative data changes only from the legislature's data

Nobody edits a filed bill's status, sponsors, history or subjects; they arrive from the central service on its schedule, and admins and owners can only ask for a refresh of what the central service holds.
